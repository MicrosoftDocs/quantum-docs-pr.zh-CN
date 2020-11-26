---
title： Pauli 度量说明：了解如何使用单 qubit Pauli 度量值操作。
author： bradben uid： pauli： benbra： v-ms. 日期： 12/11/2017 ms. 主题：文章不是：
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "\cdots"
- "bmatrix"
- "\ddots"
- "\equiv"
- "\sum"
- "\begin"
- "\end"
- "\sqrt"
- "\otimes"
- "{"
- "}"
- "\text"
- "\phi"
- "\kappa"
- "\psi"
- "\alpha"
- "\beta"
- "\gamma"
- "\delta"
- "\omega"
- "\bra"
- "\ket"
- "\boldone"
- "\\\\"
- "\\"
- "="
- "\frac"
- "\text"
- "\mapsto"
- "\dagger"
- "\to"
- "\begin{cases}"
- "\end{cases}"
- "\operatorname"
- "\braket"
- "\id"
- "\expect"
- "\defeq"
- "\variance"
- "\dd"
- "&"
- "\begin{align}"
- "\end{align}"
- "\Lambda"
- "\lambda"
- "\Omega"
- "\mathrm"
- "\left"
- "\right"
- "\qquad"
- "\times"
- "\big"
- "\langle"
- "\rangle"
- "\bigg"
- "\Big"
- "|"
- "\mathbb"
- "\vec"
- "\in"
- "\texttt"
- "\ne"
- "<"
- ">"
- "\leq"
- "\geq"
- "~~"
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- "\_"

---

# <a name="pauli-measurements"></a>Pauli 度量值

在前面的讨论中，我们重点介绍计算基础度量值。
事实上，从符号的角度来看，量子计算会出现其他常见的度量，这在计算基础度量方面非常方便。
当你使用时 Q# ，你将遇到的最常见的度量值可能是 *Pauli 的度量值*，它将计算基础度量值纳入其他基准，并在不同 qubits 之间进行奇偶校验。
在这种情况下，通常会讨论度量 Pauli 运算符，通常是运算符（例如 $ x、Y、z $ 或 $ z \otimes z、x \otimes x、x \otimes Y $ 等）。 

> [!TIP]
> 在中 Q# ，多 Qubit Pauli 运算符通常由类型的数组表示 `Pauli[]` 。
> 例如，若要表示 $ X \otimes Z \otimes Y $ ，可以使用数组 `[PauliX, PauliZ, PauliY]` 。

在量程错误纠正的子字段中，讨论 Pauli 运算符的度量值尤其常见。
在中 Q# ，我们遵循类似的约定; 现在我们介绍了此替代方法视图。

在深入了解有关如何思考 Pauli 度量的详细信息之前，请考虑测量量程内单个 qubit 对量程状态的作用。
假设我们有一个 $ qubit 的 $ 量程状态，然后将一个 qubit 立即测量为 $ 2 ^ n 的一半 $ ，这可能是状态的一半。
换言之，该度量值将量程状态投影到两个半个空格。
我们可以通用化我们对量化指标的看法，以反映这种直觉。

为了简洁地识别这些 subspaces，我们需要一种用于描述这些的语言。
描述这两个 subspaces 的一种方法是通过一个矩阵来指定它们，该矩阵只包含两个唯一的本征值，约定为 $ \pm 1 $ 。
有关以这种方式描述 subspaces 的简单示例，请考虑使用 $ Z $ ：

$$
\begin{align}
  Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix} 。
\end{align}
$$

通过读取 Pauli 矩阵的对角线元素 $ $ ，我们可以看到 $ Z $ 有两个本征向量， $ \ket { 0 } $ 和 $ \ket { 1 } $ ，其中包含相应的本征值 $ \pm 1 $ 。
因此，如果我们测量 qubit 并获取与 `Zero` 状态 0) 对应的 ($ \ket { } $ ，则我们知道 qubit 的状态是 $ Z 运算符的 + 1 $ eigenstate $ $ 。
同样，如果我们获得 `One` ，我们知道我们 qubit 的状态是 $ Z 的-1 $ eigenstate $ $ 。此过程被称为 "度量 Pauli Z" 的 Pauli 度量语言 $ $ ，完全等同于执行计算基础度量。

$ \times $ 作为 Z 的单一转换的任意 2 2 矩阵 $ $ 还满足此条件。
也就是说，我们还可以使用矩阵 $ a = u ^ \dagger Z u $ ，其中 $ u $ 是任何其他的单一矩阵，以便为矩阵定义 $ \pm 1 本征向量中度量值的两个结果 $ 。
Pauli 度量值的表示法通过标识 X、Y、Z 度量值来引用这种单一等效性，该度量 $ $ 值可以从 qubit 获取信息。
为方便起见，下面提供了这些度量值。


|Pauli 度量  | 单一转换  |
|-------------------|------------------------|
|$ $ Z |               $\boldone$             |
|$ $ X |$H               $                    |
|$ $ Y |$HS ^               {\dagger}$         |

也就是说，使用这种语言时，"度量值 $ Y $ " 等效于应用 $ HS ^， \dagger $ 然后以计算为基础，其中 [`S`](xref:Microsoft.Quantum.Intrinsic.S) 是一个内部量程操作，有时称为 "阶段入口"，可由单一矩阵模拟

$$
\begin{align}
    S =\begin{bmatrix}
        1 & 0 \\\\ 0 & i \end{bmatrix} 。
\end{align}
$$

它还等效于将 $ HS ^ 应用于 \dagger $ 量程状态向量，然后再测量 $ Z，以使 $ 以下操作等效于 `Measure([PauliY], [q])` ：

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        Adjoint S(q);
        H(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

然后，将转换回计算基础，并将其应用于量程状态向量，从而找到正确的状态 $ $ ; 在上面的代码段中，转换回计算基础会通过使用块自动进行处理 `within … apply` 。

在中 Q# ，我们说结果---也就是说，从状态---交互中提取的传统信息由 `Result` 值 $ j \in \\ { \texttt { 零提供 } ， \texttt { 一个 } \\ } $ 指示结果是否处于 $ Pauli 运算符度量的 (-1) ^ j $ eigenspace 中。


## <a name="multiple-qubit-measurements"></a>多 qubit 度量

多 qubit Pauli 运算符的度量值的定义类似，如下所示：

$$
Z \otimes z = \begin{bmatrix} 1 & 0 & 0 0 0 & \\\\  0 & -1 0 0 0 0 & & \\\\ & & -1 & 0 \\\\ & & & \end{bmatrix} 0 0 0 1。
$$

因此，两个 Pauli 运算符的 tensor 产品构成一个矩阵，其中包含 $ $ 两个由 $ + 1 $ 和 $ -1 本征值 $ 组成的空格。
与单一 qubit 的情况一样，两者都构成一半空间，这意味着可访问的矢量空间的一半属于 $ + 1 $ eigenspace，另一半是 $ -1 $ eigenspace。
通常，可以很容易地从 tensor 产品的定义中看出 Pauli 运算符的任何 tensor 产品 $ $ 和标识也服从这一点。
例如，

$$
\begin{align}
    \otimes \boldone Z =\begin{bmatrix}
        1 & 0 & 0 0 &\\\\
        0 &  1 &  0 &  0 \\\\
        0 &  0 & -1 &  0 \\\\
        0 &  0 &  0 & -1 \end{bmatrix} 。
\end{align}
$$

与之前一样，此类矩阵的任何单一转换还将描述 \pm 1 本征值标记的两个半角空格 $ $ 。
例如， $ x \otimes x = h \otimes h (z \otimes z) h \otimes h $  与 z HXH 的标识 $ 相同 = $ 。
与 qubit 情况类似，所有 qubit Pauli 度量值都可以作为 $ u ^ \dagger (Z \otimes \id) u 写入 $ 4 个 $ \times $ 单一矩阵 $ u $ 。枚举下表中的转换。

> [!NOTE]
>在下表中，我们使用 $ \operatorname { SWAP } $ 指示矩阵 >$$
> \begin{align}
>     \operatorname{交换 } &=
>     \left (\begin { 矩阵}
>1 & 0 & 0 0 &\\\\
>         0 & 0 & 1 & 0 \\\\
>         0 & 1 & 0 & 0 \\\\
>0 & 0 & 0 & 1 > \end { 矩阵 } \right) >     \end{align}
> $$
> 用于模拟内部操作 [`SWAP`](xref:Microsoft.Quantum.Intrinsic) 。

|Pauli 度量     | 单一转换  |
|----------------------|------------------------|
|$ \otimes \boldone Z $| $\boldone\otimes\boldone$|
|$ \otimes \boldone X $| $\otimes \boldone H $|
|$ \otimes \boldone Y $| $HS \dagger \otimes \boldone ^ $|
|$\boldone \otimesZ $ | $ \operatorname { 交换 } $|
|$\boldone \otimesX $ | $ (H \otimes \boldone) \operatorname { 交换 } $|
|$\boldone \otimesY $ | $ (HS ^ \dagger \otimes \boldone) \operatorname { 交换 } $|
|$Z \otimesZ $ | $ \operatorname { cnot-contains } \_ { 10 } $|
|$X \otimesZ $ | $ \operatorname { cnot-contains } \_ { 10 } (H \otimes \boldone) $|
|$Y \otimesZ $ | $ \operatorname { cnot-contains } \_ { 10 } (HS ^ \dagger \otimes \boldone) $|
|$Z \otimesX $ | $ \operatorname { cnot-contains } \_ { 10 } (\boldone \otimes H) $|
|$X \otimesX $ | $ \operatorname { cnot-contains } \_ { 10 } (h \otimes h) $|
|$Y \otimesX $ | $ \operatorname { cnot-contains } \_ { 10 } (HS ^ \dagger \otimes H) $|
|$Z \otimesY $ | $ \operatorname { cnot-contains } \_ { 10 } (\boldone \otimes HS ^ \dagger) $|
|$X \otimesY $ | $ \operatorname { cnot-contains } \_ { 10 } (H \otimes HS ^ \dagger) $|
|$Y \otimesY $ | $ \operatorname { cnot-contains } \_ { 10 } (HS ^ \dagger \otimes HS \dagger) $|

[`CNOT`](xref:Microsoft.Quantum.Intrinsic.CNOT)此时，操作出现的原因如下。
不包含矩阵的每个 Pauli 度量 $ \boldone $ 都等效于以上推理的单一到 $ z \otimes z $ 。
$Z z 的本征值 \otimes $ 仅依赖于构成每个计算基础向量的 qubits 的奇偶校验，并且用于计算此奇偶校验并将其存储在第一位的受控非运算。
然后，在度量第一位后，可以恢复生成的半角空格的标识，这相当于测量 Pauli 运算符。

另外一个注意事项：尽管度量 $ z \otimes z 与 $ 按顺序测量 $ z \otimes \mathbb { 1 } $ 和 1 z 的顺序相同 $ \mathbb { ，但这种 } \otimes $ 假定是 false。
原因是度量 $ z \otimes z $ 将量程状态投影到了 $ 这些运算符的 + 1 $ 或 $ -1 $ eigenstate 中。
$先度量 z \otimes \mathbb { 1 } $ ，然后再 $ \mathbb { } \otimes $ 将量程状态向量投影到 Z 1 的半个空格上 $ \otimes \mathbb { } $ ，然后计算为 $ \mathbb { 1 } \otimes z $ 的半个空格。由于有四个计算基准向量，同时执行这两个度量会将状态降到一个四分之一空间，因此将其减少为单个计算基础向量。

## <a name="correlations-between-qubits"></a>量子位之间的关联
另一种方法是查看度量标准（例如 $ x x 或 z z）的 tensor 产品， \otimes $ $ \otimes $ 这些度量值使你可以查看在这两个 qubits 间的关联中存储的信息。
度量 $ X \otimes \id $ 使你可以查看在第一个 qubit 中本地存储的信息。
尽管这两种类型的度量在量程计算中都同样很有价值，但前者会导致量程计算的强大功能。
它在量程计算中表现出这一点，通常情况下，您想要学习的信息并不存储在任何单个 qubit 中，而是一次只存储在所有 qubits 中，因此，这种情况下，只能通过联合 (度量来查看 $ 此信息，例如 z \otimes z $) 会将此信息变为清单。

例如，在 "纠错" 中，我们经常想要了解在学习有关我们尝试保护的状态时所发生的错误。
"[位翻转" 代码示例](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code)显示了如何使用 $ Z \otimes z \otimes \id $ 和 $ \id \otimes z \otimes z $ < 等度量来执行此操作的示例。--TODO：在载入的情况下，将其更改为指向示例浏览器的链接。 -->

$ \otimes \otimes \otimes \boldone $ 也可以测量 X Y Z 等任意 Pauli 运算符。
Pauli 运算符的所有此类 tensor 产品仅具有两个本征值 $ \pm 1 $ ，两个 eigenspaces 构成整个矢量空间的半个空格。
因此，它们符合上面所述的要求。

在中 Q# ， $ $ 如果度量值生成的结果为 eigenspace ( 的 $) ^ j，则此类度量值将返回 j $ 。
将 Pauli 度量作为内置功能 Q# 非常有用，因为测量此类运算符需要使用受控-NOT 入口和基础转换的长链来描述将 $ $ 操作表达为 Z 和的 tensor 产品所需的 diagonalizing U 门 $ $ $ \id $ 。
通过能够指定想要执行其中一项预定义度量，无需担心如何转换基础，以使计算基础度量提供必要的信息。
Q# 自动为你处理所有必要的基础转换。
有关详细信息，请参阅 [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) 和 [`MeasurePaulis`](xref:Microsoft.Quantum.Measurement.MeasurePaulis) 操作。

## <a name="the-no-cloning-theorem"></a>No-Cloning 定理

量程信息非常强大。
它使我们能够以指数形式比最佳已知传统算法更快地执行令人惊叹的东西，或高效模拟经典需要指数成本来准确模拟的相关 electron 系统。
但对量程计算的强大功能有一些限制。
这种限制是由 *无克隆定理* 提供的。

No-Cloning 定理为名称正好。
它不允许量程计算机克隆通用量程状态。
定理的证明非常简单。
虽然在这里我们的讨论中，无克隆定理的完整证明是一项很少的技术，但在我们的范围内没有其他辅助 qubits 的证明。

对于此类量程计算机，克隆操作必须由单一矩阵进行描述。
我们不允许进行度量，因为它会损坏我们尝试克隆的量程状态。
要模拟克隆操作，我们希望使用单一矩阵来使 $$
  U \ket { \psi } \ket { 0 } = \ket { \psi }\ket{\psi}
$$
适用于任何状态 $ \ket { \psi } $ 。
矩阵乘法的 "线性" 属性意味着，对于任何第二个量程状态 $ \ket { \phi } $ ，

$$
\begin{align}
    U \left [ \frac { 1 } { \sqrt { 2 } } \left (\ket { \phi } + \ket { \psi } \right) \right ] \ket { 0}
    &= \frac{1 } { \sqrt { 2 } } U \ket { \phi } \ket { 0}
      + \frac{1 } { \sqrt { 2 } } U \ket { \psi } \ket { 0 }\\\\
    &= \frac{1 } { \sqrt { 2 } } \left ( \ket { \phi } \ket { \phi }  +  \ket { \psi }\ket{\psi}
        \right) \\\\
    &\ne \left ( \frac { 1 } { \sqrt { 2 } } \left (\ket { \phi } + \ket { \psi } \right) \right) \otimes \left ( \frac { 1 } { \sqrt { 2 } } \left (\ket { \phi } + \ket { \psi } \right \right) ) 。
\end{align}
$$

这提供了 No-Cloning 定理后面的基本直觉：复制未知量程状态的任何设备必须至少在其复制的某些状态下引发错误。
虽然 cloner 在输入状态下线性处理的关键假设可以通过添加和度量辅助 qubits 来突破，此类交互还会通过测量统计信息泄漏有关系统的信息，并在这种情况下防止精确克隆。
有关更完整的 No-Cloning 定理，请参阅 [以获取详细信息](xref:microsoft.quantum.more-information)。

No-Cloning 定理对于定性了解量程计算非常重要，因为如果你可以在较低的情况上克隆量程状态，则会向你授予一项近乎神奇的功能，以便从量程状态中学习。
事实上，您可能违反了海森堡的 vaunted 不确定性原则。
或者，您可以使用最佳的 cloner 从复杂的量程分布中获取一个示例，并从一个示例中了解有关该分布的所有内容。
这就像你翻转硬币和观察打印头，然后在告诉朋友，使其响应 "Ah，这一硬币的分布必须与 $ p = 0.512643 \ ldots $ ！"  这种语句是不 sensical 的，因为有一小部分信息 (磁头结果) 只是不能提供编码分发所需的多个信息，而不是以前的信息。
同样，如果没有以前的信息，我们就不能完全克隆量程状态，因为我们不知道 p 就无法准备系综的 $ $ 。

信息在量程计算中不可用。
每个 qubit 都提供一的信息，而 No-Cloning 定理表明没有后门，可以利用它来解决有关系统所获得的信息与对其调用的干扰之间的基本平衡点。
