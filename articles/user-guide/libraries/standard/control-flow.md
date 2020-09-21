---
title: 标准 libararies 中的流控制 Q#
description: 了解 Microsoft 标准库中的流控制操作和函数 Q# 。
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1cfef50cf2bbecd2043972a662edd8120c5570ec
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835615"
---
# <a name="higher-order-control-flow"></a>高阶控制流 #

标准库的主要角色之一是，更轻松地将高级算法想法作为 [量程程序](https://en.wikipedia.org/wiki/Quantum_programming)进行表达。
因此， Q# canon 提供了各种不同的流控制构造，每个构造使用函数和操作的部分应用程序实现。
立即跳转到一个示例，请考虑要在收银机上构造 "CNOT-CONTAINS 阶梯" 的情况：

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

可以通过使用迭代和循环来表示此模式 `for` ：

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

以 <xref:microsoft.quantum.canon.applytoeachca> 和数组操作函数（如）表示， <xref:microsoft.quantum.arrays.zip> 但这更简短且更易于阅读：

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

在本部分的其余部分，我们将提供一些示例，说明如何使用 canon 提供的各种流控制操作和功能简洁地 express 量程程序。

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a>对数组和范围应用操作和函数 ##

Canon 提供的一项主要抽象是迭代的一部分。
例如，对于单 qubit 单一 $U $，请考虑窗体的单一窗体 $U \otimes U \otimes \cdots \otimes U $。
在中 Q# ，我们可能会使用 <xref:microsoft.quantum.arrays.indexrange> 将此表示为 `for` 对寄存器的循环：

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

然后，可以使用此新操作作为 `HAll(register)` 应用 $H \Otimes H \otimes \cdots \Otimes h $。

但这样做很麻烦，尤其是在较大的算法中。
此外，此方法专用于要应用于每个 qubit 的特定操作。
我们可以使用这一事实，即，操作是第一类来更明确地表达此算法概念：

```qsharp
ApplyToEachCA(H, register);
```

此处的后缀 `CA` 指示对的调用 `ApplyToEach` 本身 adjointable 并可控制。
因此，如果 `U` 支持 `Adjoint` 和 `Controlled` ，则以下行是等效的：

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

具体而言，这意味着对的调用 `ApplyToEachCA` 可以出现在自动生成 adjoint 专用化的操作中。
同样， <xref:microsoft.quantum.canon.applytoeachindex> 可用于表示窗体的模式 `U(0, targets[0]); U(1, targets[1]); ...` ，并为其输入支持的函子的每个组合提供版本。

> [!TIP]
> `ApplyToEach` 已参数化，因此它可以与接受除以外的输入的操作一起使用 `Qubit` 。
> 例如，假设 `codeBlocks` 是 <xref:microsoft.quantum.errorcorrection.logicalregister> 需要恢复的值数组。
> 然后， `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` 将错误更正代码 `code` 和恢复函数独立应用于 `recoveryFn` 每个块。
> 即使对于传统输入，此操作也是如此： `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` 将应用 $ \pi/$2 的旋转约 $X $，后跟 $pi/$3 的旋转 $Y $。

Q#Canon 还支持对函数编程熟悉的传统枚举模式。
例如， <xref:microsoft.quantum.arrays.fold> 实现模式 $f (f (f (s \_ {\text{initial}}，x \_ 0) ，x \_ 1) ，\dots ..) $，以在列表中减少函数。
此模式可用于实现 sum、products、最小值、最大值和其他此类函数：

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

同样，类似于 <xref:microsoft.quantum.arrays.mapped> 和的函数 <xref:microsoft.quantum.arrays.mappedbyindex> 可用于在中表达函数编程概念 Q# 。

## <a name="composing-operations-and-functions"></a>编写操作和函数 ##

由 canon 提供的控制流构造作为其输入，以便能够将多个操作或函数组合到一个可调用中。
例如，模式 $UVU ^ {\dagger} $ 在量程编程中非常常见，因此 canon 将操作 <xref:microsoft.quantum.canon.applywith> 作为此模式的抽象提供。
此抽象还允许更有效地 compliation 线路，因为 `Controlled` 在序列上的 `U(qubit); V(qubit); Adjoint U(qubit);` 操作无需对每个线路执行操作 `U` 。
若要查看此项，请让 $c (U) $ 是表示的单一 `Controlled U([control], target)` 项，并允许 $c 以相同方式定义 (V) $。
然后针对任意状态 $ \ket{\psi} $、\begin{align} c (U) c (V) c (U) ^ \dagger \ket {1} \otimes \ket{\psi} & = \ket {1} \otimes (UVU ^ {\dagger} \ket{\psi} ) & \\ \\ = ( \boldone \otimes u)  (c (V) # A13 ( \boldone \otimes u ^ \dagger) {1}
\end{align} 的定义 `Controlled` 。
另一方面，\begin{align} c (U) c (V) c (U) ^ \dagger \ket {0} \otimes \ket{\psi} & = \ket {0} \otimes \ket{\psi} \\ \\ & = \ket {0} \otimes (UU ^ \dagger \ket{\psi} ) & \\ \\ = ( \boldone \otimes u)  ({0} ()  () A13 \boldone \otimes
通过线性 \end{align}，我们可以通过这种方式将对所有输入状态 $U $ out。
也就是说，$c (UVU ^ \dagger) = U c (V) U ^ \dagger $。
由于控制操作的总体开销可能很高，因此使用受控变体（如 `WithC` 和） `WithCA` 可帮助减少需要应用的控件函子的数量。

> [!NOTE]
> 分解 $U $ 的另一个结果是，我们甚至不必知道如何将函子应用于 `Controlled` `U` 。
> `ApplyWithCA` 因此，签名比预期的更弱：
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

同样，会 <xref:microsoft.quantum.canon.bound> 生成应用其他操作序列的操作。
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
这种类比是通过识别来精确进行的，即，单一运算符与调用操作的副作用完全一致，以便在其他单一运算符方面对单一运算符进行的任何分解都对应于为传统子例程构造特定调用序列，这将发出说明作为特定单一运算符。
在此视图下， `Bound` 是矩阵产品的精确表示形式，因为 `Bound([A, B])(target)` 等效于 `A(target); B(target);` ，后者又是对应于 $BA $ 的调用序列。

更复杂的示例是 [Trotter – Suzuki 扩展](https://arxiv.org/abs/math-ph/0506007v1)。
如 [数据结构](xref:microsoft.quantum.libraries.data-structures)的 "Dynamical 生成器表示" 部分所述，Trotter – Suzuki 扩展提供了一种表示矩阵指数的特别有用的方式。
例如，以最低顺序应用扩展时，会生成任何运算符 $A $ 和 $B $，$A = A ^ \dagger $ 和 $B = B ^ \dagger $，\begin{align} \tag{★} \label{eq： trotter-suzuki-0} \exp (i [A + B] t) = \ lim_ {n\to\infty} \left ( \exp () \exp () \right) ^ n。
\end{align} 俗称，这意味着我们可以通过在 $A $ 和 $B $ 单独的情况下进行发展，在 $A + B $ 下提高状态。
如果我们在 `A : (Double, Qubit[]) => Unit` 应用 $e ^ {i t A} $ 的操作下，通过 $A $ 来表示进化，则在重新排列调用序列方面，Trotter – Suzuki 扩展的表示形式就变得清晰。
具体而言，在给定操作 `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` 的情况下， `A = U(0, _, _)` `B = U(1, _, _)` 我们可以 `U` 通过生成窗体的序列来定义一个新的操作，该操作表示一次 $t $ 的整数

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

此时，我们现在可以了解 Trotter – Suzuki 扩展， *根本不需引用量程机制*。
此扩展实际上是一个由 $ \eqref{eq： trotter-suzuki-0} $ 使用的特殊迭代模式。
此迭代模式的实现方式 <xref:microsoft.quantum.canon.decomposeintotimestepsca> 如下：

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

的签名 `DecomposeIntoTimeStepsCA` 遵循中的一种常用模式 Q# ，其中的集合可以由数组或动态计算元素所支持的元素来表示，这些集合的第一个元素是 `Int` 指示它们的长度的值。

## <a name="putting-it-together-controlling-operations"></a>将其放在一起：控制操作 ##

最后，canon 将 `Controlled` 通过提供额外的条件量程运算方法，在函子上构建。
对于除 $ \ket{0\cdots 0} $ 之外的计算基础状态，通常情况下，尤其是在量程算法中。
使用上述控制操作和函数，我们可以在单个语句中使用更常见的量程情况。
接下来，我们将介绍如何 <xref:microsoft.quantum.canon.controlledonbitstring>)  (sans 类型参数，然后逐个细分各个部分。
我们需要做的第一件事就是定义一个操作，该操作实际上会在任意计算基础状态上实现控件的负载大幅提升。
但我们不会直接调用此操作，因此我们将添加 `_` 到名称的开头，以指示它是其他地方构造的实现。

```qsharp
operation _ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl),
    controlRegister : Qubit[],
    targetRegister: Qubit[])
: Unit is Adj + Ctl
```

请注意，我们采用一个表示为数组的位字符串 `Bool` ，用于指定要应用于我们所提供的操作的调节 `oracle` 。
由于此操作实际上是直接执行应用程序，因此我们还需要获取控件和目标寄存器，这两者都在此处表示为 `Qubit[]` 。

接下来，我们注意到，通过将 $ \ket{\vec{s}} $ 转换为 $ \ket{0\cdots 0} $，在计算基础状态 $ \ket{\vec{s}} = \ket{s \_ 0 s \_ 1 \dots .. s \_ {n-1}} $ 上控制可实现位字符串 $ \vec{s} $。
具体而言，$ \ket{\vec{s}} = X ^ {s \_ 0} \Otimes x ^ {s \_ 1} \otimes \Cdots \otimes x ^ {s \_ {n-1}} \ket{0\cdots 0} $。
由于 $X ^ {\dagger} = X $，这意味着 $ \ket{0\dots 0} = X ^ {s \_ 0} \Otimes X ^ {s \_ } \otimes \Cdots \otimes x ^ {s \_ {n-1}} \ket{\vec{s}} $。
因此，我们可以应用 $P = X ^ {s \_ 0} \Otimes x ^ {s \_ 1} \otimes \Cdots \otimes x ^ {s \_ {n-1}} $，应用 `Controlled oracle` 并转换回 $ \vec{s} $。
此构造是准确的 `ApplyWith` ，因此，我们会相应地编写新操作的正文：

```qsharp
{
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

在这里，我们已使用 <xref:microsoft.quantum.canon.applypaulifrombitstring> 应用 $P $，在其目标上进行部分应用，以便与一起使用 `ApplyWith` 。
但请注意，我们需要将 *控制* 寄存器转换为所需的格式，因此我们 `(Controlled oracle)` 在 *目标*上部分应用内部操作。
这会使 `ApplyWith` 控制寄存器与 $P $ 的方括号完全相同。

此时，我们可以这样做，但我们的新操作并不像应用函子，unsatisfying `Controlled` 。
因此，我们通过编写一个函数来控制新的控制流概念，该函数将 oracle 控制在一起并返回一个新的操作。
通过这种方式，我们的新函数的外观和感觉非常类似 `Controlled` ，说明我们可以使用和 canon 来轻松定义功能强大的新控制流构造 Q# ：

```qsharp
function ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl))
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
