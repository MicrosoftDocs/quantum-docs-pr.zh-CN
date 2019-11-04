---
title: 'Q # 标准库-prelude |Microsoft Docs'
description: 'Q # 标准库-prelude'
author: QuantumWriter
uid: microsoft.quantum.libraries.standard.prelude
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: dddb3d4a5ebcdca16da41a5ae5520d98ea900a7f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73183227"
---
# <a name="the-prelude"></a>Prelude #

"问答" 开发工具包附带的 Q # 编译器和目标计算机提供了一组内部函数和操作，可在 Q # 中编写量程程序时使用。

## <a name="intrinsic-operations-and-functions"></a>内部操作和函数 ##

标准库中定义的内部操作大致分为以下几个类别之一：

- <xref:microsoft.quantum.core> 命名空间中收集的基本传统函数。
- 表示由[Clifford 和 $T $ 关口](xref:microsoft.quantum.concepts.qubit)组成的 unitaries 的操作。
- 表示各种运算符旋转的操作。
- 实现度量的操作。

由于 Clifford + $T $ 入口集[通用](xref:microsoft.quantum.concepts.multiple-qubits)于量程计算，因此这些操作足以满足 negligibly 小错误中的任何量程算法的要求。
通过同时提供旋转，Q # 允许程序员在单个 qubit 单一和 CNOT-CONTAINS 入口库中工作。 此库更容易考虑，因为它不需要程序员直接学习 Clifford + $T $ 分解，而是因为存在用于将单个 qubit unitaries 编译到 Clifford 和 $T $ 入口的高效方法（请参阅[此处](xref:microsoft.quantum.more-information)）有关详细信息）。

在可能的情况下，在 prelude 中定义的操作（作用于 qubits）允许应用 `Controlled` 变体，以便目标计算机将执行相应的分解。

在 prelude 的此部分中定义的许多函数和操作都位于 @"microsoft.quantum.intrinsic" 命名空间中，因此，大多数 Q # 源文件会在初始命名空间声明之后立即具有 `open Microsoft.Quantum.Intrinsic;` 指令。
将自动打开 <xref:microsoft.quantum.core> 命名空间，这样就可以在没有 `open` 语句的情况下使用 <xref:microsoft.quantum.core.length> 等函数。

### <a name="common-single-qubit-unitary-operations"></a>常见的单一 Qubit 单一操作 ###

Prelude 还定义了很多常见[的 qubit 操作](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)。
所有这些操作都允许 `Controlled` 和 `Adjoint` 函子。

#### <a name="pauli-operators"></a>Pauli 运算符 ####

<xref:microsoft.quantum.intrinsic.x> 运算实现 Pauli $X $ operator。
这有时也称为 `NOT` 入口。
它 `(Qubit => Unit is Adj + Ctl)`签名。
它对应于 qubit 单一：

\begin{equation} \begin{bmatrix} 0 & 1 \\\\% FIXME：目前使用 quadwhack 黑客。
1 & 0 \end{bmatrix} \end{equation}

<xref:microsoft.quantum.intrinsic.y> 运算实现 Pauli $Y $ operator。
它 `(Qubit => Unit is Adj + Ctl)`签名。
它对应于 qubit 单一：

\begin{equation} \begin{bmatrix} 0 &-i \\\\% FIXME：这目前使用 quadwhack 黑客。
我 & 0 \end{bmatrix} \end{equation}

<xref:microsoft.quantum.intrinsic.z> 运算实现 Pauli $Z $ operator。
它 `(Qubit => Unit is Adj + Ctl)`签名。
它对应于 qubit 单一：

\begin{equation} \begin{bmatrix} 1 & 0 \\\\% FIXME：此操作当前使用 quadwhack 黑客。
0 &-1 \end{bmatrix} \end{equation}

下面我们看到映射到[Bloch 球体](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere)的这些转换（每种情况下的旋转轴突出显示为红色）：

![映射到 Bloch 球体的 Pauli 操作](~/media/prelude_pauliBloch.png)

需要注意的是，将相同的 Pauli 入口两次应用到同一个 qubit 会取消操作（因为现在已在表面上执行2π（360°）到 Bloch 球的完全旋转，因而回到了起始点）。 接下来，我们将提供以下标识：

$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \boldone $ $

这可以在 Bloch 球体上 visualised：

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a>其他 Qubit Cliffords ####

<xref:microsoft.quantum.intrinsic.h> 操作实现 Hadamard 入口。
这将交换目标 qubit 的 Pauli $X $ 和 $Z $ 轴，从而 $H \ket{0} = \ket{+} \mathrel{： =} （\ket{0} + \ket{1}）/\sqrt{2}$ 和 $H \ket{+} = \ket{0}$。
它 `(Qubit => Unit is Adj + Ctl)`签名，并对应于 qubit 单一：

\begin{equation} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\% FIXME：这目前使用 quadwhack 黑客。
1 &-1 \end{bmatrix} \end{equation}

Hadamard 入口特别重要，因为它可用于创建 $ \ket{0}$ 和 $ \ket{1}$ 状态的 superposition。 在 Bloch 球表示中，最简单的方法是将这种方式视为绕 x 轴旋转 $ \pi $ 弧度（$ 180 ^ \circ $），后跟围绕 y 轴的（顺时针）旋转，按 $ \ pi/2 $ 弧度（$ 90 ^ \circ $）：

![映射到 Bloch 球体的 Hadamard 操作](~/media/prelude_hadamardBloch.png)

<xref:microsoft.quantum.intrinsic.s> 操作实现 $S $ 的阶段入口。
这是 $Z Pauli $ operation 的 matrix 平方根。
也就是说，$S ^ 2 = Z $。
它 `(Qubit => Unit is Adj + Ctl)`签名，并对应于 qubit 单一：

\begin{equation} \begin{bmatrix} 1 & 0 \\\\% FIXME：此操作当前使用 quadwhack 黑客。
0 & i \end{bmatrix} \end{equation}

#### <a name="rotations"></a>旋转 ####

除了上面的 Pauli 和 Clifford 操作，Q # prelude 还提供了多种表达旋转方式的方法。
如[qubit 操作](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)中所述，旋转能力对于量子算法至关重要。

首先，我们可以使用 $H $ 和 $T $ 入口（其中 $H $ 是 Hadamard 操作，其中 \begin{equation} T \mathrel{： =} \begin{bmatrix} 1 & 0 \\\\% FIXME：这当前使用四whack 黑客。
0 & e ^ {i \pi/4} \end{bmatrix} \end{equation} 这是 <xref:microsoft.quantum.intrinsic.s> 操作的平方根，$T ^ 2 = S $。
$T $ 入口反过来又由 <xref:microsoft.quantum.intrinsic.t> 操作实现，并具有签名 `(Qubit => Unit is Adj + Ctl)`，这表示它是对 qubit 的单一操作。

尽管这是足以描述任意单一 qubit 操作的原则，但不同的目标计算机可能具有更有效的方法来旋转 Pauli 运算符，因此 prelude 包括多种方法来 convienently表达此类旋转。
其中最基本的方法是 <xref:microsoft.quantum.intrinsic.r> 操作，该操作实现绕指定的 Pauli 轴、\begin{equation} R （\sigma、\phi） \mathrel{： =} \exp （-i \phi \sigma/2）、\end{equation} （其中 $ \sigma $ 为 Pauli 运算符，$ \phi $ 为角度，其中 $\exp $ 表示矩阵指数。
它具有签名 `((Pauli, Double, Qubit) => Unit is Adj + Ctl)`，其中，输入的前两个部分表示 $R （\sigma，\phi） $ 指定单一运算符所需的传统参数 $ \sigma $ 和 $ \phi $。
可以部分应用 $ \sigma $ 和 $ \phi $，以获取其类型为单一 qubit 单一的操作。
例如，`R(PauliZ, PI() / 4, _)` 的类型 `(Qubit => Unit is Adj + Ctl)`。

> [!NOTE]
> <xref:microsoft.quantum.intrinsic.r> 运算将输入角度除以2并将其与-1 相乘。
> 对于 $Z $ 旋转，这意味着 $ eigenstate{0}$ 通过 $-\phi/$2 旋转，$ \ket{1}$ eigenstate 将旋转 $ \phi/$2，以便 $ \ket{1}$ eigenstate 相对于 $ \phi{0}$ \ket 旋转 $ eigenstate $。
>
> 具体而言，这意味着 `T` 和 `R(PauliZ, PI() / 8, _)` 只会因无关的[全局阶段](xref:microsoft.quantum.glossary#global-phase)而异。
> 出于此原因，$T $ 有时称为 $ \frac{\pi}{8}$-入口。
>
> 另请注意，围绕 `PauliI` 进行旋转仅适用于 $ \phi/$2 的全局阶段。 尽管此类阶段与[概念文档](xref:microsoft.quantum.concepts.qubit)中的观点无关，但它们与受控 `PauliI` 旋转相关。

在量程算法中，将循环表达为 dyadic 分式通常非常有用，例如，对于某些 $k \in \mathbb{Z} $ 和 $n \in $，$ \phi = \pi k/2 ^ n $。
<xref:microsoft.quantum.intrinsic.rfrac> 操作使用此约定实现围绕指定 Pauli 轴的旋转。
它与 <xref:microsoft.quantum.intrinsic.r> 的不同之处在于，旋转角度指定为 `Int`类型的两个输入，解释为 dyadic 分数。
因此，`RFrac` 具有 `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)`签名。
它实现 qubit single $ \exp （i \pi k \sigma/2 ^ n） $，其中 $ \sigma $ 是与第一个参数对应的 Pauli 矩阵，$k $ 是第二个参数，$n $ 是第三个参数。
`RFrac(_,k,n,_)` 与 `R(_,-πk/2^n,_)`相同;请注意，角度是分数的*负值*。

<xref:microsoft.quantum.intrinsic.rx> 运算实现绕 Pauli $X $ 轴的旋转。
它 `((Double, Qubit) => Unit is Adj + Ctl)`签名。
`Rx(_, _)` 与 `R(PauliX, _, _)`相同。

<xref:microsoft.quantum.intrinsic.ry> 运算实现绕 Pauli $Y $ 轴的旋转。
它 `((Double, Qubit) => Unit is Adj + Ctl)`签名。
`Ry(_, _)` 与 `R(PauliY,_ , _)`相同。

<xref:microsoft.quantum.intrinsic.rz> 运算实现绕 Pauli $Z $ 轴的旋转。
它 `((Double, Qubit) => Unit is Adj + Ctl)`签名。
`Rz(_, _)` 与 `R(PauliZ, _, _)`相同。

<xref:microsoft.quantum.intrinsic.r1> 操作按给定的量实现对 $ \ket{1}$ $ $Z $ 的 $-$1 eigenstate 的旋转。
它 `((Double, Qubit) => Unit is Adj + Ctl)`签名。
`R1(phi,_)` 与 `R(PauliZ,phi,_)` 后跟 `R(PauliI,-phi,_)`相同。

<xref:microsoft.quantum.intrinsic.r1frac> 运算按照 Z = 1 eigenstate 的给定量实现小数旋转。
它 `((Int,Int, Qubit) => Unit is Adj + Ctl)`签名。
`R1Frac(k,n,_)` 与 `RFrac(PauliZ,-k.n+1,_)` 后跟 `RFrac(PauliI,k,n+1,_)`相同。

下面显示了一个旋转操作示例（围绕此实例中的 Pauli $Z $ axis），如下所示：

![映射到 Bloch 球体的旋转操作](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a>多 Qubit 操作 ####

除了上面的单一 qubit 操作外，prelude 还定义了多个多 qubit 操作。

首先，<xref:microsoft.quantum.intrinsic.cnot> 操作执行标准受控`NOT` 门，\begin{equation} \operatorname{CNOT} \mathrel{： =} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1\\\\ 0 & 0 & 1 & 0 \end{bmatrix}。
\end{equation} 它具有 `((Qubit, Qubit) => Unit is Adj + Ctl)`的签名，表示 $ \operatorname{CNOT} $ act unitarily 两个单独的 qubits。
`CNOT(q1, q2)` 与 `(Controlled X)([q1], q2)`相同。
由于 `Controlled` 函子允许对寄存器进行控制，因此，我们使用数组文本 `[q1]` 指示只需要一个控件。

<xref:microsoft.quantum.intrinsic.ccnot> 操作执行双向控制的非入口，有时也称为 Toffoli 入口。
它 `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)`签名。
`CCNOT(q1, q2, q3)` 与 `(Controlled X)([q1, q2], q3)`相同。

<xref:microsoft.quantum.intrinsic.swap> 操作将交换两个 qubits 的量程状态。
也就是说，它实现了单一矩阵 \begin{equation} \operatorname{SWAP} \mathrel{： =} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & \\\\ &0 & 0 & 1 \end{bmatrix}。
\end{equation} 签名 `((Qubit, Qubit) => Unit is Adj + Ctl)`。
`SWAP(q1,q2)` 等效于 `CNOT(q1, q2)` 后跟 `CNOT(q2, q1)`，然后 `CNOT(q1, q2)`。

> [!NOTE]
> 交换*门与使用*类型 `Qubit[]`重新排列变量的元素不同。
> 应用 `SWAP(q1, q2)` 会导致 `q1` 和 `q2`所引用的 qubits 的状态发生更改，而 `let swappedRegister = [q2, q1];` 只影响我们引用这些 qubits 的方式。
> 此外，`(Controlled SWAP)([q0], (q1, q2))` 允许 `SWAP` 在第三个 qubit 的状态下进行条件，我们无法通过重新排列元素来表示。
> 受控交换门（也称为 Fredkin 入口）的强大功能足以包含所有传统计算。

最后，prelude 提供两个用于表示多 qubit Pauli 运算符的指数的操作。
<xref:microsoft.quantum.intrinsic.exp> 操作基于 Pauli 矩阵的 tensor 产品执行旋转，如多 qubit 单一 \begin{equation} \operatorname{Exp} （\vec{\sigma}，\phi） \mathrel{： =} \exp\left （i \phi \sigma_0 \otimes \sigma_1 \otimes \cdots \otimes \sigma_n \right）、\end{equation} （其中 $ \vec{\sigma} = （\sigma_0，\sigma_1，\dots ..，\sigma_n） $ 是一系列单 qubit Pauli 运算符，其中 $ \phi $ 为角度。
`Exp` 旋转将 $ \vec{\sigma} $ 表示为 `Pauli` 元素的数组，使其具有签名 `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`。

<xref:microsoft.quantum.intrinsic.expfrac> 操作使用上述 dyadic 分数表示法执行相同的旋转。
它 `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)`签名。

> [!WARNING]
> Pauli 运算符的 tensor 产品的指数与指数运算符 Pauli 的 tensor 产品不同。
> 也就是说，$e ^ {i （Z \otimes Z） \phi} \ne e ^ {i Z \phi} \otimes e ^ {i Z \phi} $。

### <a name="measurements"></a>度量 ###

度量时，所测量的运算符的 + 1 eigenvalue 对应于 `Zero` 结果，并将-1 eigenvalue 到 `One` 结果。

> [!NOTE]
> 虽然这种约定看起来很奇怪，但它具有两种非常好的优点。
> 首先，观察结果 $ \ket{0}$ 由 `Result` 值 `Zero`表示，同时观察 $ \ket{1}$ 对应于 `One`。
> 其次，我们可以写出 eigenvalue $ \lambda $ 对应于结果 $r $ 是 $ \lambda = （-1） ^ r $。

度量运算既不支持 `Adjoint` 也不支持 `Controlled` 函子。

<xref:microsoft.quantum.intrinsic.measure> 操作在 Pauli 运算符的指定产品中执行一个或多个 qubits 的联合度量。
如果 Pauli 数组和 qubit 数组的长度不同，则操作将失败。
`Measure` 具有 `((Pauli[], Qubit[]) => Result)`签名。

请注意，联合度量不同于分别测量每个 qubit。
例如，请考虑状态 $ \ket{11} = \ket{1} \otimes \ket{1} = X\otimes X \ket{00}$。
$Z 每个 _0 $ 和分别 _1 $ $Z，得到 $r _0 = $1 和 $r _1 = $1 的结果。
$Z 度量 Z_1 $，但我们得到了单一结果 $r _ {\textrm{joint}} = $0，表示 $ \ket{11}$ 的 pairity 为正值。
采用不同的方式： $ （-1） ^ {r_0 + r_1} = （-1） ^ r_ {\textrm{joint}}） $。
严重的是，由于我们*只*会从此度量值中了解奇偶校验，因此将保留在 superposition 的 2 2-qubit 状态之间、$ \ket{00}$ 和 $ \ket{11}$ 之间显示的任何量程信息。
此属性将在以后介绍错误更正。

为方便起见，prelude 还提供了两个其他操作来测量 qubits。
首先，由于执行 qubit 度量值非常常见，因此 prelude 定义了这种情况的简写形式。
<xref:microsoft.quantum.intrinsic.m> 操作对单个 qubit 上的 Pauli $Z $ 运算符进行度量，并具有签名 `(Qubit => Result)`。
`M(q)` 等效于 `Measure([PauliZ], [q])`。

<xref:microsoft.quantum.measurement.multim>*分别*对每个 qubits 数组的每个数组 $Z $ 运算符进行度量，返回为每个 qubit 获取的 `Result` 值的*数组*。
在某些情况下，这可以进行优化。 它有签名（`Qubit[] => Result[])`。
`MultiM(qs)` 等效于：

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
例如，<xref:microsoft.quantum.extensions.math> 命名空间定义有用的操作，如 <xref:microsoft.quantum.extensions.math.sin> 和 <xref:microsoft.quantum.extensions.math.log>。
量程开发工具包提供的实现使用传统的 .NET 基类库，因此可能需要在量程程序与其传统驱动程序之间进行额外的通信往返。
虽然这对于本地模拟器不存在问题，但在将远程模拟器或实际硬件用作目标计算机时，这可能是一个性能问题。
也就是说，单个目标计算机可以通过使用对该特定系统更有效的版本替代这些操作来缓解此性能影响。

### <a name="math"></a>符号 ###

<xref:microsoft.quantum.extensions.math> 命名空间提供 .NET 基类库[`System.Math` 类](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1)中许多有用的函数。
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

最后，<xref:microsoft.quantum.extensions.bitwise> 命名空间提供了几个有用的函数，用于通过按位运算符来处理整数。
例如，<xref:microsoft.quantum.extensions.bitwise.parity> 将整数的按位奇偶校验作为另一个整数返回。
