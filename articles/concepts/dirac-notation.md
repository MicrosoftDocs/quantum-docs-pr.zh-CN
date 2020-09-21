---
title： Dirac 表示法说明：了解如何使用 Dirac 表示法来表示量程状态并模拟量程运算。
author： QuantumWriter uid： dirac： benbra： v-ms. 日期： 12/11/2017 ms. 主题：文章不是：
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

# <a name="dirac-notation"></a>Dirac 表示法

虽然列矢量表示法在线性代数中无处不在，但在处理多个 qubits 时，量程计算通常会很繁琐。  例如，将定义为矢量时，并 $ \psi $ 不显式清楚 $ \psi $ 是行向量还是列向量。  因此 $ \phi $ ，如果和是向量，则即使定义了，也 $ \psi $ 不清楚 $ \phi \psi $ ，因为和的形状 $ \phi $ $ \psi $ 在上下文中可能不清楚。  除了矢量形状的歧义外，使用前面引入的线性代数表示法来表示更简单的矢量会非常麻烦。 例如，如果想要说明 $ n $ qubit 状态，其中每个 qubit 都采用值0， $ $ 则我们会将状态正式表示为 

$$\begin{bmatrix}1 \\\\ 0 \end{bmatrix} \otimes \cdots \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} 。 $$  

当然，评估此 tensor 的产品是不切实际的，因为矢量位于呈指数量大的空间，因此此表示法实际上是可使用上一个表示法提供的状态的最佳说明。  

[*Dirac 表示法*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) 解决了这些问题的方法是，通过提供一种新语言来满足量程机制的精确需求。  出于此原因，我们建议读者不要查看本部分中的示例，作为如何描述量程状态的严格处方，而是鼓励读者查看这些示例，这是可用于简洁表达量子创意的建议。

Dirac 表示法中有两种类型的向量： *寄存器* 向量和 *票证* 向量，因此命名为，因为当将它们组合在一起构成 *braket* 或内部产品。  如果 $ \psi $ 是列向量，则可以将 Dirac 表示法编写为 $ \ket { \psi } $ ，其中 $ \ket { \cdot } $ 表示它是 unit 列向量，即*票证*向量。  同样，行向量 $ \psi ^ \dagger $ 表示为 $ \bra { \psi } $ 。 换句话说，通过将 $ \psi ^ \dagger $ 按输入的复杂语态应用于转置的元素来获得 $ \psi $ 。 寄存器-票证表示法直接表示，它 $ \braket { \psi | \psi } $ 是向量的内部积 $ \psi $ ，后者是定义 $ 1 $ 。  

一般来说，如果 $ \psi $ 和 $ \phi $ 是量子状态向量，则其内部产品是 $ \braket { \phi | \psi } $ 指将状态测量为 $ \ket { \psi } $ $ \ket { \phi } $ $ | \braket { \phi | \psi } | ^ 2 $ 的概率。  

以下约定用于描述将零值和一 (单 qubit 计算基础状态编码的量程状态) ：

$$
\begin{bmatrix}1 \\\\ 0 \end{bmatrix} = \ket { 0 } ，\qquad
\begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \ket { 1 } 。
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a>示例：表示具有 Dirac 表示法的 Hadamard 操作

以下表示法通常用于描述从将 Hadamard 入口应用于 $ \ket { 0 和 (而产生的状态， } $ $ \ket { } $ 这与 $ $ $ $ Bloch 球) 上 + x 和-x 方向上的单位矢量相对应：

$$
\frac{1 } { \sqrt { 2 } } \begin{bmatrix} 1 \\\\ 1 \end{bmatrix} = H \ket { 0 } = \ket { + } ，\qquad
\frac{1 } { \sqrt { 2 } } \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} = H \ket { 1 } = \ket { - } 。
$$

还可以使用 Dirac 表示法将这些状态扩展为 $ \ket { 0 } $ 和 $ \ket { 1 } $ 的总和：

$$
\ket{+}= \frac{1 } { \sqrt { 2 } } (\ket { 0 }  +  \ket { 1 }) ， \qquad \ket { - } = \frac { 1 } { \sqrt { 2 } } (\ket { 0 }  -  \ket { 1 }) 。
$$

### <a name="computational-basis-vectors"></a>计算基础向量
这说明了这些状态通常称为 *计算基础*：每个量程状态始终可以表示为计算基础向量的总和，此类 sum 可以使用 Dirac 表示法来表示。  相反，在状态中也是如此， $ \ket { + } $ 并且 $ \ket { - } $ 还构成量程状态的基础。  你可以看到这样的事实：

$$
\ket{0 } = \frac { 1 } { \sqrt { 2 } } (\ket { + }  +  \ket { - }) ， \qquad \ket { 1 } = \frac { 1 } { \sqrt { 2 } } (\ket { + }  -  \ket { - }) 。
$$

作为 Dirac 表示法的示例，请考虑 braket $ \braket { 0 | 1 } $ ，这是 $ 0 到1之间的内部产品 $ $ $ 。  它可以编写为 

$$\braket{0 | 1 } = \begin{bmatrix} 1 & 0 \end{bmatrix} \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} = 0。$$

这表明 $ \ket { 0 } $ 和 $ \ket { 1 } $ 是正交向量，这意味着 $ \braket { 0 | 1 } = \braket { 1 | 0 } = 0 $ 。  还按定义 0 0 1 1 1 $ \braket { | } = \braket { | } = $ ，这意味着两个计算基础向量也可以*orthonormal*。
在下面的示例中，这些 orthonormal 属性将非常有用。 如果状态为 $ \ket { \psi } = { \frac { 3 } { 5 } } \ket { 1 }  +  { \frac { 4 } { 5 0， } } \ket { } $ 则为 $ \braket { 1 | 0 } = 0 $ ， $ $ 这是度量1的概率  

$$\big|\braket{1 | \psi } \big | ^ 2 = \left | \frac { 3 } { 5 } \braket { 1 | 1 }  + \frac { 4 } { 5 } \braket { 1 | 0 } \right | ^ 2 = \frac { 9 } { 25 } 。$$ 

### <a name="tensor-product-notation"></a>Tensor 产品表示法
Dirac 表示法还包括其中的隐式 tensor 产品结构。  这一点很重要，因为在量程计算中，两个不相关的量程寄存器描述的状态向量是两个状态向量的 tensor 产品。  如果您想要解释量程计算，则很重要的是，如果您想要说明量程计算，则非常重要的是 tensor 产品结构或缺少  Tensor 产品结构意味着我们可以编写 $ \psi \otimes \phi $ 任意两个量程状态向量，并将其 $ \phi $ $ \psi $ $ \ket { \psi } \ket { \phi } $ 显式编写为 $ \ket { \psi } \otimes \ket { \phi } $ ，但 $ \otimes $ 不需要在矢量之间进行约定编写。  例如，将两个 qubits 初始化为零状态的状态由指定

$$
\begin{bmatrix}1 \\\\ 0 0 0 \\\\ \\\\ \end{bmatrix} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} = \ket { } \otimes \ket { } = \ket { } \ket { } 0 0 0 0。
$$

同样， $ \ket { integer p 的状态 p } $ $ 表示在 $ 二进制表示法 p 的情况下进行编码的量程状态 $ $ 。  例如，如果想要 $ 使用无符号二进制编码来表示数字5，则 $ 可以将其视为

$$
\ket{1 } \ket { 0 } \ket { 1 } = \ket { 101 } = \ket { 5 } 。
$$

在此表示法中， $ \ket { 0 } $ 不需要引用单一 qubit 状态，而是使用*qubit 寄存器*存储二进制编码 $ 0 $ 。  这两个表示法之间的差异通常来自上下文。  此约定可用于简化第一个示例，该示例可通过以下任何一种方式编写：

$$
\begin{bmatrix}1 \\\\ 0 1 0 0 0 0 0 0 \end{bmatrix} \otimes \cdots \otimes \begin{bmatrix} \\\\ \end{bmatrix} = \ket { } \otimes \cdots \otimes \ket { } = | \cdots \rangle = \ket { } ^ { \otimes n } = \ket { 0 } 。
$$

### <a name="example-describing-superposition-with-dirac-notation"></a>示例：用 Dirac 表示法描述 superposition
作为另一个示例，说明如何使用 Dirac 表示法来描述量程状态，请考虑以下等效方法：写入一个量程状态，该状态对于长度为 n 的每个可能位字符串都是相等的 superposition $$

$$
H ^ { \otimes n } \ket { 0 } = \frac { 1 } { 2 ^ { n/2 } } \sum _ { j = 0 } ^ { 2 ^ n-1 } \ket { j } = \ket { + } ^ { \otimes n } 。
$$

在这里，你可能会想知道， $ 对于 n 位，总和从 0 $ 到 $ 2 ^ { n } -1 $ 的原因 $ $ 。  首先请注意，有 $ 2 ^ { n 个 } $ 不同的配置， $ n $ 位可采用这种配置。  您可以看到，这是因为有一个位可能需要 $ 2 $ 个值，但两个位可能需要 $ 4 个 $ 值，等等。 通常，这意味着有 $ 2 ^ n 个不同的 $ 可能的位字符串，但最大值是在 $ 1 \cdots 1 = 2 ^ n-1 中编码的， $ 因此它是 sum 的上限。
为此，在此示例中，我们没有使用 n （与 $ \ket { + } ^ { \otimes } = \ket { + } $ 0 n 0 的对比）， $ \ket { } ^ { \otimes } = \ket { } $ 因为此符号约定通常是为计算基础状态而保留的，每个 qubit 都初始化为零。  虽然这种约定在这种情况下非常合理，但不会在量程计算宣传资料中使用。

### <a name="expressing-linearity-with-dirac-notation"></a>用 Dirac 表示法表示线性
Dirac 表示法的另一个不错的功能是线性的。  如果我们想要为任何四个量程状态向量编写， 

$$ (\alpha \ket { \psi }  + \beta \ket { \phi }) \otimes (\gamma \ket { \chi }  +  \delta \ket { \omega }) = \alpha \gamma \ket { \psi } \ket { \chi }  +  \alpha \delta \ket { \psi } \ket { \omega } + \beta \gamma \ket { \phi } \ket { \chi } + \beta \delta \ket { \phi } \ket { \omega } 。$$

也就是说，可以在 Dirac 表示法中分发 tensor 产品表示法，使在州向量间的 tensor 产品最终看起来就像普通的乘法。

寄存器向量遵循类似的约定来票证矢量。  例如，向量 $ \bra { \psi } \bra { \phi } $ 等效于状态向量 $ \psi ^ \dagger \otimes \phi ^ \dagger = (\psi \otimes \phi) ^ \dagger $ 。 如果票证向量 $ \ket { \psi } $ 是 $ \alpha \ket { 0 1，则 }  +  \beta \ket { } $ 向量的寄存器矢量版本是 $ \bra { \psi } = \ket { \psi } ^ \dagger = (\bra { 0 } \alpha ^ * + \bra { 1 } \beta ^ * ) $ 。

例如，假设我们想要 $ \ket { \psi } = \frac { } { 使用量程计划计算状态 3 5 } \ket { 1 4 5 0 的概率，将 }  +  \frac { } { } \ket { } $ 状态测量为 $ \ket { + } $ 或 $ \ket { - } $ 。 然后，设备将输出 $ 状态为 \ket { - } $ 

$$|\braket{- |\psi}|^ 2 = \left | \frac { 1 } { \sqrt { 2 } } (\bra { 0 }  -  \bra { 1 }) # B2 \frac { 3 } { 5 } \ket { 1 }  +  \frac { 4 } { 5 } \ket { 0 }) \right | ^ 2 = \left | - \frac { 3 } { 5 \sqrt { 2 } }  +  \frac { 4 } { 5 \sqrt { 2 } } \right | ^ 2 = \frac { 1 } { 50 } 。$$

负号在概率计算中出现的事实是量程干扰的表现形式，这是量程计算与传统计算相比的优点之一。

## <a name="ketbra-or-outer-product"></a>ketbra 或外部产品
Dirac 表示法中值得讨论的最后一项是 *ketbra* 或 outer 积。  外部产品在 Dirac 表示法中表示为 $ \ket { \psi } \bra { \phi } $ ，有时称为 ketbras，因为 bras 和 kets 的顺序与 brakets 相反。  外部产品通过矩阵乘法定义，与 $ \ket { \psi } \bra { \phi } = \psi \phi ^ \dagger $ 量程状态向量和相同 $ \psi $ $ \phi $ 。  最简单且最常见的是此表示法的示例是

$$
\ket{0 } \bra { 0 } = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \begin{bmatrix} 1 & 0 \end{bmatrix} = \begin{bmatrix} 1 & 0 0 0 \\\\ & \end{bmatrix} \qquad \ket { 1 } \bra { } = \begin{bmatrix} 0 1 \\\\ \end{bmatrix} \begin{bmatrix} 0 & 1 0 0 0 \end{bmatrix} = \begin{bmatrix} & \\\\ & 1 \end{bmatrix} 。
$$

Ketbras 通常称为投影机，因为它们将量程状态投影到一个固定值。  由于这些操作并不是单一 (并且甚至不会保留矢量) 的标准，因此，量子计算机不能准确地应用投影仪。  但是，投影仪可以通过一项漂亮的工作来描述度量值对量程状态的操作。  例如，如果将状态度量值 $ \ket { \psi } $ 为0， $ 则 $ 结果转换为度量结果的状态体验是

  $$\ket{\psi}\right \frac 箭头 { (\ket { 0 } \bra { 0 }) \ket { \psi } } { | \braket { 0 | \psi } | } = \ket { 0 } ，$$

如果要测量状态并将其查找为0，则应为 $ \ket { } $ 。  重申一重申，此类投影机无法应用于量程计算机上的状态。  相反，它们最适用于随机应用，结果0会 $ \ket { } $ 出现，出现一定的固定概率。  此类测量结果的概率可以作为 "量程" 投影仪的预期值写入状态

$$
\bra{\psi} (\ket { 0 } \bra { 0 }) \ket { \psi } = | \braket { \psi | 0 } | ^ 2，$$

这说明了投影仪只是为了表达度量过程的一种新方法。

如果我们考虑将 qubit 状态的第一个 qubit 测量为 $ 1， $ 则还可以使用投影仪和 Dirac 表示法来更方便地描述此过程：

$$
P (\text { first qubit = 1 }) = \bra { \psi } \left (\ket { 1 } \bra { 1 } \otimes \boldone ^ { \otimes n-1 } \right) \ket { \psi } 。
$$

这里，可以方便地用 Dirac 表示法编写标识矩阵

$$
\boldone= \ket{0 } \bra { 0 } + \ket { 1 1 } \bra { } = \begin{bmatrix} 1 & 0 \\\\ 0 & 1 \end{bmatrix} 。
$$

如果有两个 qubits，投影仪可以扩展为 

$$
\ket{1 1 1 1 } \bra { } \otimes \id = \ket { } \bra { } \otimes (\ket { 0 } \bra { 0 } + \ket { 1 } \bra { 1 }) = \ket { 10 } \bra { 10 }  +  \ket { 11 } \bra { 11 } 。
$$

接下来，我们可以看到，这与使用列矢量表示法的 multiqubit 状态的 likelihoods 的讨论一致：

$$
P (\text { first qubit = 1 }) = \psi ^ \dagger (e \_ { 10 } e \_ { 10 } ^ \dagger + e \_ { 11 } e \_ { 11 } ^ \dagger) \psi = | e \_ { 10 } ^ \dagger \psi | ^ 2 + | e \_ { 11 } ^ \dagger \psi | ^ 2，$$

它与多 qubit 度量讨论相匹配。  不过，将此结果通用化为多 qubit 用例，使用 Dirac 表示法比使用列矢量表示法更简单，并且完全等同于先前处理。

## <a name="density-operators"></a>密度运算符

使用 Dirac 表示法表示的另一个有用的运算符是 *密度运算符*，有时也称为 *状态运算符*。
量程状态向量的密度运算符采用 $ \rho 形式 = \ket { \psi } \bra { \psi } $ 。
将状态表示为矩阵而不是向量的这一概念通常非常方便，因为它提供了一种表示概率计算的便利方法，还允许同时描述统计不确定性以及同一形式内的量程不确定性。
一般的量程状态运算符（而不是向量）在量程计算的某些方面无处不在，但并不需要了解字段的基础知识。
对于感兴趣的读者，建议阅读中提供的参考书籍之一 [以获取详细信息](xref:microsoft.quantum.more-information)。

## <a name="no-locq-gate-sequences-equivalent-to-quantum-states"></a>Q# 等效于量程状态的入口序列
最后一点值得一提的是量程表示法和 Q# 编程语言：在本文档的开始中，该量程状态是量程计算中信息的基础对象。  这可能会导致意外，因为没有 Q# 量程状态的概念。  相反，所有状态仅由用于准备它们的操作描述。  上面的示例是对此的一个很好的说明。  我们可以将结果表示为 $ H ^ { \otimes n } \ket { 0 } $ ，而不是在寄存器中的每个量程位字符串上都表示统一的 superposition。  这种状态的更短的简短说明不仅可以经典原因，而且还可以简明地定义要在软件堆栈中传播以实现算法所需的操作。  出于此原因， Q# 设计为发出入口序列而不是量程状态; 但是，在理论级别上，这两个透视是等效的。
