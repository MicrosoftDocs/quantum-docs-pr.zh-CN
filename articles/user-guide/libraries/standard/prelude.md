---
title: QDK 中的内部操作和函数
description: 了解 QDK 中的内部操作和函数，包括传统函数和单一、旋转和度量运算。
author: QuantumWriter
uid: microsoft.quantum.libraries.standard.prelude
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 19674620475e68b41c855023807a5fd1f7945ec9
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274406"
---
# <a name="the-prelude"></a>Prelude #

"问答" 开发工具包附带的 Q # 编译器和目标计算机提供了一组内部函数和操作，可在 Q # 中编写量程程序时使用。

## <a name="intrinsic-operations-and-functions"></a>内部操作和函数 ##

标准库中定义的内部操作大致分为以下几个类别之一：

- 命名空间中收集的基本传统函数 <xref:microsoft.quantum.core> 。
- 表示由[Clifford 和 $T $ 关口](xref:microsoft.quantum.concepts.qubit)组成的 unitaries 的操作。
- 表示各种运算符旋转的操作。
- 实现度量的操作。

由于 Clifford + $T $ 入口集[通用](xref:microsoft.quantum.concepts.multiple-qubits)于量程计算，因此这些操作足以满足 negligibly 小错误中的任何量程算法的要求。
通过同时提供旋转，Q # 允许程序员在单个 qubit 单一和 CNOT-CONTAINS 入口库中工作。 此库更容易考虑，因为它不需要程序员直接学习 Clifford + $T $ 分解，而是因为存在用于将单个 qubit unitaries 编译到 Clifford 和 $T $ 入口的高效方法（有关详细信息，请参阅[此处](xref:microsoft.quantum.more-information)）。

在可能的情况下，在 prelude 中定义的操作（作用于 qubits）允许应用 `Controlled` 变量，以使目标计算机执行适当的分解。

在 prelude 的此部分中定义的许多函数和操作都位于 @"microsoft.quantum.intrinsic" 命名空间中，因此，大多数 Q # 源文件会在 `open Microsoft.Quantum.Intrinsic;` 初始命名空间声明后面紧跟一个指令。
<xref:microsoft.quantum.core>命名空间是自动打开的，因此 <xref:microsoft.quantum.core.length> 可以使用等函数而无需使用 `open` 语句。

### <a name="common-single-qubit-unitary-operations"></a>常见的单一 Qubit 单一操作 ###

Prelude 还定义了很多常见[的 qubit 操作](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)。
所有这些操作都允许 `Controlled` 和 `Adjoint` 函子。

#### <a name="pauli-operators"></a>Pauli 运算符 ####

<xref:microsoft.quantum.intrinsic.x>操作实现 Pauli $X $ operator。
这有时也称为 `NOT` 入口。
签名 `(Qubit => Unit is Adj + Ctl)` 。
它对应于 qubit 单一：

\begin{equation} \begin{bmatrix} 0 & 1 \\ \\ % FIXME：目前使用 quadwhack 黑客。
1 & 0 \end{bmatrix} \end{equation}

<xref:microsoft.quantum.intrinsic.y>操作实现 Pauli $Y $ operator。
签名 `(Qubit => Unit is Adj + Ctl)` 。
它对应于 qubit 单一：

\begin{equation} \begin{bmatrix} 0 &-i \\ \\ % FIXME：目前使用 quadwhack 黑客。
我 & 0 \end{bmatrix} \end{equation}

<xref:microsoft.quantum.intrinsic.z>操作实现 Pauli $Z $ operator。
签名 `(Qubit => Unit is Adj + Ctl)` 。
它对应于 qubit 单一：

\begin{equation} \begin{bmatrix} 1 & 0 \\ \\ % FIXME：目前使用 quadwhack 黑客。
0 &-1 \end{bmatrix} \end{equation}

下面我们看到映射到[Bloch 球体](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere)的这些转换（每种情况下的旋转轴突出显示为红色）：

![映射到 Bloch 球体的 Pauli 操作](~/media/prelude_pauliBloch.png)

需要注意的是，将相同的 Pauli 入口两次应用到同一个 qubit 会取消操作（因为现在已在表面上执行2π（360°）到 Bloch 球的完全旋转，因而回到了起始点）。 接下来，我们将提供以下标识：

$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \boldone $ $

这可以在 Bloch 球体上 visualised：

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a>其他 Qubit Cliffords ####

<xref:microsoft.quantum.intrinsic.h>操作实现 Hadamard 入口。
这将交换目标 qubit 的 Pauli $X $ 和 $Z $ 轴，从而 $H \ket {0} = \ket{+} \mathrel{： =} （\ket {0} + \ket {1} ）/\sqrt {2} $ 和 $H \ket{+} = \ket {0} $。
它具有签名 `(Qubit => Unit is Adj + Ctl)` ，并对应于 qubit 单一：

\begin{equation} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ % FIXME：目前使用的是 quadwhack 黑客。
1 &-1 \end{bmatrix} \end{equation}

Hadamard 入口特别重要，因为它可用于创建 $ \ket {0} $ 和 $ \ket {1} $ 状态的 superposition。 在 Bloch 球表示中，最简单的方法是将这种方式视为绕 x 轴旋转 $ \pi $ 弧度（$ 180 ^ \circ $），后跟围绕 y 轴的（顺时针）旋转，按 $ \ pi/2 $ 弧度（$ 90 ^ \circ $）：

![映射到 Bloch 球体的 Hadamard 操作](~/media/prelude_hadamardBloch.png)

<xref:microsoft.quantum.intrinsic.s>操作实现 $S $ 的阶段入口。
这是 $Z Pauli $ operation 的 matrix 平方根。
也就是说，$S ^ 2 = Z $。
它具有签名 `(Qubit => Unit is Adj + Ctl)` ，并对应于 qubit 单一：

\begin{equation} \begin{bmatrix} 1 & 0 \\ \\ % FIXME：目前使用 quadwhack 黑客。
0 & i \end{bmatrix} \end{equation}

#### <a name="rotations"></a>旋转 ####

除了上面的 Pauli 和 Clifford 操作，Q # prelude 还提供了多种表达旋转方式的方法。
如[qubit 操作](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)中所述，旋转能力对于量子算法至关重要。

首先，我们可以通过使用 $H $ 和 $T $ 入口（其中 $H $ 是 Hadamard 操作，其中 \begin{equation} T \mathrel{： =} \begin{bmatrix} 1 & 0 \\ \\ % FIXME：此操作当前使用故障回复 whack 黑客来表达任何 qubit 操作。
0 & e ^ {i \pi/4} \end{bmatrix} \end{equation} 这是操作的平方根 <xref:microsoft.quantum.intrinsic.s> ，因此 $T ^ 2 = S $。
操作将实现 $ 门 <xref:microsoft.quantum.intrinsic.t> ，并具有签名 `(Qubit => Unit is Adj + Ctl)` ，这表示它是 qubit 上的单一操作。 $T

尽管这是足以描述任意单 qubit 操作的原则，但不同的目标计算机可能具有更有效的方法来旋转 Pauli 运算符，因此 prelude 包括多种方法来 convienently 表达此类旋转。
其中最基本的 <xref:microsoft.quantum.intrinsic.r> 操作是操作，该操作实现围绕指定的 Pauli 轴、\Begin{equation} R （\sigma、\phi） \mathrel{： =} \exp （-i \phi \sigma/2）、\end{equation} （其中 $ \sigma $ 为 Pauli 运算符，$ \phi $ 为角度，其中 $ \exp $ 表示矩阵指数）的旋转。
它有签名 `((Pauli, Double, Qubit) => Unit is Adj + Ctl)` ，其中的前两个部分表示指定单一运算符所需的传统参数 $ \sigma $ 和 $ \phi $ $R （\sigma，\phi） $。
可以部分应用 $ \sigma $ 和 $ \phi $，以获取其类型为单一 qubit 单一的操作。
例如， `R(PauliZ, PI() / 4, _)` 具有类型 `(Qubit => Unit is Adj + Ctl)` 。

> [!NOTE]
> <xref:microsoft.quantum.intrinsic.r>操作将输入角度除以2并将其与-1 相乘。
> 对于 $Z $ 旋转，这意味着 $ \ket {0} $ eigenstate 通过 $-\phi/$2 进行旋转，$ \ket {1} $ eigenstate 旋转了 $ \phi/$2，以便 $ \ket {1} $ eigenstate 相对于 $ \phi $ \ket 旋转 $ eigenstate $ {0} 。
>
> 具体而言，这意味着 `T` 和 `R(PauliZ, PI() / 8, _)` 仅因无关的[全局阶段](xref:microsoft.quantum.glossary#global-phase)而异。
> 出于此原因，$T $ 有时称为 $ \frac{\pi} {8} $-入口。
>
> 另请注意，绕过的 `PauliI` 只是应用了 $ \phi/$2 的全局阶段。 尽管此类阶段与[概念文档](xref:microsoft.quantum.concepts.qubit)中的观点无关，但它们与受控旋转相关 `PauliI` 。

在量程算法中，将循环表达为 dyadic 分式通常非常有用，例如，对于某些 $k \in \mathbb{Z} $ 和 $n \in $，$ \phi = \pi k/2 ^ n $。
<xref:microsoft.quantum.intrinsic.rfrac>操作使用此约定实现围绕指定 Pauli 轴的旋转。
它与的不同之处在于， <xref:microsoft.quantum.intrinsic.r> 旋转角度指定为类型的两个输入 `Int` ，解释为 dyadic 分数。
因此， `RFrac` 具有签名 `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)` 。
它实现 qubit single $ \exp （i \pi k \sigma/2 ^ n） $，其中 $ \sigma $ 是与第一个参数对应的 Pauli 矩阵，$k $ 是第二个参数，$n $ 是第三个参数。
`RFrac(_,k,n,_)`与相同 `R(_,-πk/2^n,_)` ; 请注意，角度是分数的*负值*。

<xref:microsoft.quantum.intrinsic.rx>操作实现绕 $X Pauli $ axis 的旋转。
签名 `((Double, Qubit) => Unit is Adj + Ctl)` 。
`Rx(_, _)` 与 `R(PauliX, _, _)` 相同。

<xref:microsoft.quantum.intrinsic.ry>操作实现绕 $Y Pauli $ axis 的旋转。
签名 `((Double, Qubit) => Unit is Adj + Ctl)` 。
`Ry(_, _)` 与 `R(PauliY,_ , _)` 相同。

<xref:microsoft.quantum.intrinsic.rz>操作实现绕 $Z Pauli $ axis 的旋转。
签名 `((Double, Qubit) => Unit is Adj + Ctl)` 。
`Rz(_, _)` 与 `R(PauliZ, _, _)` 相同。

<xref:microsoft.quantum.intrinsic.r1>操作按给定的量实现对 $ \ket {1} $ $Z $ 的 $-$1 eigenstate 的旋转。
签名 `((Double, Qubit) => Unit is Adj + Ctl)` 。
`R1(phi,_)`与后面的相同 `R(PauliZ,phi,_)` `R(PauliI,-phi,_)` 。

<xref:microsoft.quantum.intrinsic.r1frac>操作按照 Z = 1 eigenstate 的给定量实现小数旋转。
签名 `((Int,Int, Qubit) => Unit is Adj + Ctl)` 。
`R1Frac(k,n,_)`与后面的相同 `RFrac(PauliZ,-k.n+1,_)` `RFrac(PauliI,k,n+1,_)` 。

下面显示了一个旋转操作示例（围绕此实例中的 Pauli $Z $ axis），如下所示：

![映射到 Bloch 球体的旋转操作](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a>多 Qubit 操作 ####

除了上面的单一 qubit 操作外，prelude 还定义了多个多 qubit 操作。

首先，此 <xref:microsoft.quantum.intrinsic.cnot> 操作执行标准受控 `NOT` 入口，\begin{equation} \operatorname{CNOT} \mathrel{： =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}。
\end{equation} 它具有签名 `((Qubit, Qubit) => Unit is Adj + Ctl)` ，表示在两个单个 qubits 上的 $ \operatorname{CNOT} $ act unitarily。
`CNOT(q1, q2)` 与 `(Controlled X)([q1], q2)` 相同。
由于 `Controlled` 函子允许对寄存器进行控制，因此我们使用数组文本 `[q1]` 指示只需要一个控件。

<xref:microsoft.quantum.intrinsic.ccnot>操作执行双向控制的非入口，有时也称为 Toffoli 入口。
签名 `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)` 。
`CCNOT(q1, q2, q3)` 与 `(Controlled X)([q1, q2], q3)` 相同。

<xref:microsoft.quantum.intrinsic.swap>操作交换两个 qubits 的量程状态。
也就是说，它实现了单一矩阵 \begin{equation} \operatorname{SWAP} \mathrel{： =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 1 \end{bmatrix}。
\end{equation} 的签名 `((Qubit, Qubit) => Unit is Adj + Ctl)` 。
`SWAP(q1,q2)`等效于 `CNOT(q1, q2)` 后跟 `CNOT(q2, q1)` 和 then `CNOT(q1, q2)` 。

> [!NOTE]
> 交换门不同于*将变量*的元素与类型重新排列 `Qubit[]` 。
> 应用 `SWAP(q1, q2)` 会导致对和所引用的 qubits 的状态进行更改 `q1` `q2` ，而 `let swappedRegister = [q2, q1];` 只会影响我们引用这些 qubits 的方式。
> 此外， `(Controlled SWAP)([q0], (q1, q2))` 还允许 `SWAP` 在第三个 qubit 的状态下进行条件，我们无法通过重新排列元素来表示。
> 受控交换门（也称为 Fredkin 入口）的强大功能足以包含所有传统计算。

最后，prelude 提供两个用于表示多 qubit Pauli 运算符的指数的操作。
<xref:microsoft.quantum.intrinsic.exp>操作基于 Pauli 矩阵的 tensor 产品执行旋转，由多 qubit 单一 \Begin{equation} \operatorname{Exp} （\vec{\sigma}，\phi） \mathrel{： =} \exp\left （i \phi \ sigma_0 \otimes \ sigma_1 \otimes \cdots \otimes \ sigma_n \right）、\end{equation} （其中 $ \vec{\sigma} = （\ sigma_0，\ sigma_1，\dots ..，\ sigma_n） $ 为一系列单 Qubit Pauli 运算符，其中 $ \phi $ 为角度。
`Exp`旋转将 $ \vec{\sigma} $ 表示为 `Pauli` 元素数组，以使其具有签名 `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` 。

<xref:microsoft.quantum.intrinsic.expfrac>操作使用上述 dyadic 分数表示法执行相同的旋转。
签名 `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)` 。

> [!WARNING]
> Pauli 运算符的 tensor 产品的指数与指数运算符 Pauli 的 tensor 产品不同。
> 也就是说，$e ^ {i （Z \otimes Z） \phi} \ne e ^ {i Z \phi} \otimes e ^ {i Z \phi} $。

### <a name="measurements"></a>度量 ###

度量时，所测量的运算符的 + 1 eigenvalue 对应于 `Zero` 结果，-1 eigenvalue 为 `One` 结果。

> [!NOTE]
> 虽然这种约定看起来很奇怪，但它具有两种非常好的优点。
> 首先，观察结果 $ \ket {0} $ 由 `Result` 值表示 `Zero` ，而观察 $ \ket {1} $ 对应于 `One` 。
> 其次，我们可以写出 eigenvalue $ \lambda $ 对应于结果 $r $ 是 $ \lambda = （-1） ^ r $。

度量运算既不支持 `Adjoint` 也不支持 `Controlled` 函子。

<xref:microsoft.quantum.intrinsic.measure>操作对指定的 Pauli 运算符产品中的一个或多个 qubits 执行联合度量。
如果 Pauli 数组和 qubit 数组的长度不同，则操作将失败。
`Measure`具有签名 `((Pauli[], Qubit[]) => Result)` 。

请注意，联合度量不同于分别测量每个 qubit。
例如，考虑状态 $ \ket {11} = \ket {1} \otimes \Ket {1} = X\otimes X \ket {00} $。
$Z 每个 _0 $ 和分别 _1 $ $Z，得到 $r _0 = $1 和 $r _1 = $1 的结果。
$Z 度量 Z_1 $，则会得到一个结果 $r _ {\textrm{joint}} = $0，表示 $ \ket $ 的 pairity {11} 为正值。
以不同的方式，$ （-1） ^ {r_0 + r_1} = （-1） ^ r_ {\textrm{joint}}） $。
严重的是，由于我们*只*会从此度量值中了解奇偶校验，因此将保留在 superposition 的 2 2-qubit 状态之间的任何量程信息 {00} {11} 。
此属性将在以后介绍错误更正。

为方便起见，prelude 还提供了两个其他操作来测量 qubits。
首先，由于执行 qubit 度量值非常常见，因此 prelude 定义了这种情况的简写形式。
<xref:microsoft.quantum.intrinsic.m>操作对单个 qubit 上的 Pauli $Z $ 运算符进行度量，并具有签名 `(Qubit => Result)` 。
`M(q)` 等效于 `Measure([PauliZ], [q])`。

<xref:microsoft.quantum.measurement.multim>*分别*对每个 Qubits 数组的 Pauli $Z $ operator 进行度量，返回*array* `Result` 为每个 qubit 获取的值的数组。
在某些情况下，这可以进行优化。 它具有签名（ `Qubit[] => Result[])` 。
`MultiM(qs)`等效于：

```qsharp
mutable rs = new Result[Length(qs)];
for (index in 0..Length(qs)-1)
{
    set rs[index] = M(qs[index]);
}
return rs;
```

## <a name="extension-functions-and-operations"></a>扩展函数和操作 ##

此外，prelude 在 .NET 级别定义一组丰富的数学和类型转换函数，以便在 Q # 代码中使用。
例如， <xref:microsoft.quantum.math> 命名空间定义有用的操作，例如 <xref:microsoft.quantum.math.sin> 和 <xref:microsoft.quantum.math.log> 。
量程开发工具包提供的实现使用传统的 .NET 基类库，因此可能需要在量程程序与其传统驱动程序之间进行额外的通信往返。
虽然这对于本地模拟器不存在问题，但在将远程模拟器或实际硬件用作目标计算机时，这可能是一个性能问题。
也就是说，单个目标计算机可以通过使用对该特定系统更有效的版本替代这些操作来缓解此性能影响。

### <a name="math"></a>数学 ###

<xref:microsoft.quantum.math>命名空间提供 .net 基类库的[ `System.Math` 类](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1)中许多有用的函数。
这些函数的使用方式与任何其他 Q # 函数的使用方式相同：

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

如果已基于其参数的类型重载了某个 .NET 静态方法，则相应的 Q # 函数将使用一个后缀（表示其输入的类型）进行批注：

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a>按位运算 ###

最后， <xref:microsoft.quantum.bitwise> 命名空间提供了若干用于通过按位运算符来操作整数的有用函数。
例如， <xref:microsoft.quantum.bitwise.parity> 将整数的按位奇偶校验作为另一个整数返回。