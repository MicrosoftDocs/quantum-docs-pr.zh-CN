---
title: 'Q # 标准库-控制和流 |Microsoft Docs'
description: 'Q # 标准库-控制和流'
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: ff73cef12a3b8c2a6559308dc244c7c2e865ba9f
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820447"
---
# <a name="higher-order-control-flow"></a>高阶控制流 #

标准库的主要角色之一是，更轻松地将高级算法想法作为[量程程序](https://en.wikipedia.org/wiki/Quantum_programming)进行表达。
因此，Q # canon 提供各种不同的流控制构造，每个构造使用函数和操作的部分应用程序实现。
立即跳转到一个示例，请考虑要在收银机上构造 "CNOT-CONTAINS 阶梯" 的情况：

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

可以通过使用迭代和 `for` 循环来表示此模式：

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

不过，根据 <xref:microsoft.quantum.canon.applytoeachca> 和数组操作函数（如 <xref:microsoft.quantum.arrays.zip>）进行表达，这要简单得多，更易于阅读：

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

在本部分的其余部分，我们将提供一些示例，说明如何使用 canon 提供的各种流控制操作和功能简洁地 express 量程程序。

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a>对数组和范围应用操作和函数 ##

Canon 提供的一项主要抽象是迭代的一部分。
例如，对于单 qubit 单一 $U $，请考虑窗体的单一窗体 $U \otimes U \otimes \cdots \otimes U $。
在 Q # 中，我们可能会使用 <xref:microsoft.quantum.arrays.indexrange> 将此表示为通过寄存器 `for` 循环：

```qsharp
/// # Summary
/// Applies $H$ to all qubits in a register.
operation ApplyHadamardToAll(
    register : Qubit[])
: Unit is Adj + Ctl {
    for (qubit in register) {
        H(qubit);
    }
}
```

然后，可以使用此新操作作为 `HAll(register)` 应用 $H \otimes H \otimes \cdots \otimes H $。

但这样做很麻烦，尤其是在较大的算法中。
此外，此方法专用于要应用于每个 qubit 的特定操作。
我们可以使用这一事实，即，操作是第一类来更明确地表达此算法概念：

```qsharp
ApplyToEachCA(H, register);
```

此处的后缀 `CA` 指示对 `ApplyToEach` 的调用本身 adjointable 并且可控。
因此，如果 `U` 支持 `Adjoint` 和 `Controlled`，则以下行是等效的：

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

具体而言，这意味着对 `ApplyToEachCA` 的调用可能会出现在自动生成 adjoint 专用化的操作中。
同样，<xref:microsoft.quantum.canon.applytoeachindex> 可用于表示 `U(0, targets[0]); U(1, targets[1]); ...`的窗体模式，并为其输入支持的函子的每个组合提供版本。

> [!TIP]
> `ApplyToEach` 是类型参数化的，因此它可以与接受除 `Qubit`以外的输入的操作一起使用。
> 例如，假设 `codeBlocks` 是需要恢复 <xref:microsoft.quantum.errorcorrection.logicalregister> 值的数组。
> 然后 `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` 会将错误更正代码 `code` 和恢复功能 `recoveryFn` 单独应用于每个块。
> 这也适用于传统的输入： `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` 将应用 $ \pi/$2 的旋转大约 $X $，后跟围绕 $Y $ $pi/$3 的旋转。

Q # canon 还提供对函数编程熟悉的传统枚举模式的支持。
例如，<xref:microsoft.quantum.arrays.fold> 实现模式 $f （f （s\_{\text{initial}}，x\_0）、x\_1）、\dots .） $，以在列表中减少函数。
此模式可用于实现 sum、products、最小值、最大值和其他此类函数：

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

同样，<xref:microsoft.quantum.arrays.mapped> 和 <xref:microsoft.quantum.arrays.mappedbyindex> 之类的函数可用于在 Q # 中表达函数编程概念。

## <a name="composing-operations-and-functions"></a>编写操作和函数 ##

由 canon 提供的控制流构造作为其输入，以便能够将多个操作或函数组合到一个可调用中。
例如，模式 $UVU ^ {\dagger} $ 在量程编程中非常常见，因此 canon 提供操作 <xref:microsoft.quantum.canon.applywith> 作为此模式的抽象。
此抽象还允许更有效地 compliation 线路，因为在序列 `Controlled` 操作时，`U(qubit); V(qubit); Adjoint U(qubit);` 不需要对每个 `U`进行操作。
为此，请将 $c （U） $ 指定为代表 `Controlled U([control], target)` 的单一，并以相同方式定义 $c （V） $。
然后针对任意状态 $ \ket{\psi} $，\begin{align} c （u） c （V） c （U） ^ \dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes （UVU ^ {\dagger} \ket{\psi}） \\\\ & = （\boldone \otimes U）（c （V））（\boldone \otimes U ^ \dagger） \ket{1} \otimes \ket{\psi}。
按 `Controlled`的定义 \end{align}。
另一方面，\begin{align} c （U） c （V） c （U） ^ \dagger \ket{0} \otimes \ket{\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes （UU ^ \dagger \ket{\psi}） \\\\ & = （\boldone \otimes U ^ \boldone） \otimes{0} \dagger \ket
通过线性 \end{align}，我们可以通过这种方式将对所有输入状态 $U $ out。
也就是说，$c （UVU ^ \dagger） = U c （V） U ^ \dagger $。
由于控制操作的总体开销可能很高，因此使用 `WithC` 和 `WithCA` 等受控变体有助于减少需要应用的控制函子的数目。

> [!NOTE]
> 分解 $U $ 的另一个结果是，我们甚至不必知道如何将 `Controlled` 函子应用到 `U`。
> 因此，`ApplyWithCA` 的签名比预期的更弱：
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

同样，<xref:microsoft.quantum.canon.bound> 生成的操作依次应用其他操作序列。
例如，以下项是等效的：

```qsharp
H(qubit); X(qubit);
Bound([H, X], qubit);
```

与迭代模式合并会使此方法特别有用：

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bound([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a>有序组合 ###

我们还可以通过在部分应用程序和传统函数方面考虑 flow 控制来进一步进一步了解，并且还可以根据古典 flow 控制来建模相当复杂的量程概念。
这种类比是通过识别来精确进行的，即，单一运算符完全对应于调用操作的副作用，以便在其他单一运算符方面进行的任何单一运算符分解都与构造特定调用传统子例程的序列，这些子例程发出说明，作为特定的单一运算符。
在此视图中，`Bound` 精确表示矩阵产品，因为 `Bound([A, B])(target)` 等效于 `A(target); B(target);`，而后者又是对应于 $BA $ 的调用序列。

更复杂的示例是[Trotter – Suzuki 扩展](https://arxiv.org/abs/math-ph/0506007v1)。
如[数据结构](xref:microsoft.quantum.libraries.data-structures)的 "Dynamical 生成器表示" 部分所述，Trotter – Suzuki 扩展提供了一种表示矩阵指数的特别有用的方式。
例如，以最低顺序应用扩展时，会生成任何运算符 $A $ 和 $B $，$A = A ^ \dagger $ 和 $B = B ^ \dagger $，\begin{align} \tag{★} \label{eq： trotter-suzuki-0} \exp （i [A + B] t） = \ lim_ {n\to\infty} \left （\exp （i A t/n） \exp （i B t/n） \right） ^ n。
\end{align} 俗称，这意味着我们可以通过在 $A $ 和 $B $ 单独的情况下进行发展，在 $A + B $ 下提高状态。
如果我们在应用 $e ^ {i t A} $ 的操作 `A : (Double, Qubit[]) => Unit` 下，使用 $A $ 来表示进化，则在重新排列调用序列方面，Trotter – Suzuki 扩展的表示形式就变得清晰。
具体而言在给定操作 `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` 以便 `A = U(0, _, _)` 和 `B = U(1, _, _)`，可以通过生成格式的序列来定义一个新操作，该操作表示时间 $t $ `U` 的整数

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

此时，我们现在可以了解 Trotter – Suzuki 扩展，*根本不需引用量程机制*。
此扩展实际上是一个由 $ \eqref{eq： trotter-suzuki-0} $ 使用的特殊迭代模式。
此迭代模式由 <xref:microsoft.quantum.canon.decomposeintotimestepsca>实现：

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

`DecomposeIntoTimeStepsCA` 的签名遵循 Q # 中的一种常见模式，其中，可以通过数组或动态计算元素进行备份的元素由其第一个元素为 `Int` 值的元组表示。

## <a name="putting-it-together-controlling-operations"></a>将其放在一起：控制操作 ##

最后，canon 通过提供额外的条件量程运算方法，在 `Controlled` 函子上构建。
对于除 $ \ket{0\cdots 0} $ 之外的计算基础状态，通常情况下，尤其是在量程算法中。
使用上述控制操作和函数，我们可以在单个语句中使用更常见的量程情况。
接下来，让我们转到 <xref:microsoft.quantum.canon.controlledonbitstring> 如何操作（sans 类型参数），然后逐个细分各个部分。
我们需要做的第一件事就是定义一个操作，该操作实际上会在任意计算基础状态上实现控件的负载大幅提升。
但我们不会直接调用此操作，因此我们将 `_` 添加到名称的开头，以指示它是其他位置的另一个构造的实现。

```qsharp
operation _ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl),
    controlRegister : Qubit[],
    targetRegister: Qubit[])
: Unit is Adj + Ctl
```

请注意，我们采用一个由 `Bool` 数组表示的位字符串，用于指定要应用于 `oracle` 所提供的操作的调节。
由于此操作实际上是直接执行应用程序，因此我们还需要采用控件和目标寄存器，这两者都在此处表示为 `Qubit[]`。

接下来，我们注意到，通过将 $ \ket{\vec{s}} $ 转换为 $ \ket{0\cdots 0} $，在计算基础状态 $ \ket{\vec{s}} = \ket{s\_0 s\_1 \dots . s\_{n-1}} $ 上的控制可实现。
具体而言，$ \ket{\vec{s}} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} \ket{0\cdots 0} $。
由于 $X ^ {\dagger} = X $，这意味着 $ \ket{0\dots 0} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} \ket{\vec{s}} $。
因此，我们可以应用 $P = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} $，应用 `Controlled oracle`，并转换回 $ \vec{s} $。
此构造精确地 `ApplyWith`，因此我们会相应地编写新操作的正文：

```qsharp
{
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

在这里，我们已使用 <xref:microsoft.quantum.canon.applypaulifrombitstring> 应用 $P $，在其目标上进行部分应用，以便用于 `ApplyWith`。
但请注意，我们需要将*控制*寄存器转换为所需的格式，因此我们在*目标*上部分应用内部操作 `(Controlled oracle)`。
这会使 `ApplyWith` 将控制寄存器括在 $P $ 中，就像我们所希望的那样。

此时，我们可以这样做，但我们的新操作并不像应用 `Controlled` 函子那样 "感觉"。
因此，我们通过编写一个函数来控制新的控制流概念，该函数将 oracle 控制在一起并返回一个新的操作。
通过这种方式，我们的新函数看起来非常像 `Controlled`，这说明我们可以使用 Q # 和 canon 来轻松定义功能强大的新控制流构造：

```qsharp
function ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl))
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
