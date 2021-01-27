---
标题：多个 qubits 说明：了解如何对两个或更多个 qubits 执行操作。
author： bradben uid： qubits： benbra： v-ms. 日期： 12/11/2017 ms. 主题：概念非 loc：
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

# <a name="multiple-qubits"></a>多个 Qubits

尽管单 qubit 入口具有一些典型的典型功能（例如，在给定时间内处于多个状态的功能），但如果在一段给定时间内拥有多个状态，则我们会有一个具有计算能力的设备，该设备的计算能力甚至会受到微不足道，即使计算器仅允许使用传统的 cray。
仅当我们增加 qubits 的数量时，量程计算的真正功能才会变得明显。
此功能在某种程度上导致，因为量程状态向量的矢量空间的尺寸随 qubits 的数量呈指数增长。
这意味着，虽然可以对单个 qubit 进行完全建模，但模拟 50 qubit 的量程计算会导致推送现有超级计算机的限制。
增加计算的大小只需一个额外的 qubit 就会使存储状态所需的内存 *翻倍* ，并大致使计算时间 *加倍* 。
这种快速计算能力翻倍的原因是，具有相对较小 qubits 数的量程计算机可能远远超过今天、明天和其他计算任务的最强大超级计算机。

为什么要为量程状态向量增加指数级增长？  本部分的目的是查看用于从单 qubit 状态中构建多 qubit 状态的规则，并讨论我们需要包括在设置为构成通用多 qubit 量程计算机的入口中的操作。
这些工具绝对是了解代码中通常使用的入口集的必要 Q# ，还可以获得直觉，例如牵连或干扰的量程效果如何表现出比传统计算更强大的量程计算。

## <a name="representing-two-qubits"></a>表示两个 Qubits
Qubit 状态之间的主要区别在于两 qubit 状态为四维，而不是二维。
这是因为，qubit 状态的计算基础由一 qubit 状态的 tensor 产品构成。  例如，我们有 \begin{align}
00 \equiv \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} & = \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix} ， \qquad 01 \equiv \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} = \begin{bmatrix} 0 \\\\ 1 \\\\ 0 \\\\ 0 \end{bmatrix} ，\\\\
10 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 0 0 \end{bmatrix} & = \begin{bmatrix} \\\\ \\\\ 1 \\\\ 0 \end{bmatrix} ， \qquad 11 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 0 0 0 \end{bmatrix} = \begin{bmatrix} \\\\ \\\\ \\\\ 1 \end{bmatrix} 。
\end{align}

这种情况很容易看出，n qubits 的量程状态 $ $ $ 使用此构造由维度 2 ^ n 的单位向量表示 $ 。  矢量

$$
\begin{bmatrix}\alpha _{ 00 } 01 \\\\ 10 \alpha_ { } \\\\ \alpha _{ 11 } \\\\ \alpha_ { }  \end{bmatrix}
$$

表示两个 qubits 的量程状态（如果 $ | \alpha _{ 00 } | ^ 2 | \alpha +_ { 01 } | ^ 2 + | \alpha _{ 10 } | ^ 2 | \alpha +_ { 11 } | ^ 2 = 1） $ 。 与单个 qubits 一样，多个 qubits 的量程状态向量包含描述系统行为所需的所有信息。

如果提供两个单独的 qubits，其中一个处于状态， $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ 另一个 qubit 处于状态 $ \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $ ，则对应的双 qubit 状态为    

$$
\begin{bmatrix} \alpha \\\\  \beta \end{bmatrix} \otimes \begin{bmatrix} \gamma \\\\  \delta \end{bmatrix} 
=\begin{bmatrix} \alpha \begin{bmatrix} \gamma \\\\  \delta \end{bmatrix} \\\\ \beta \begin{bmatrix}\gamma \\\\  \delta \end{bmatrix} \end{bmatrix}
= \begin{bmatrix} \alpha\gamma \\\\  \alpha\delta \\\\  \beta\gamma \\\\  \beta\delta \end{bmatrix}, $$

其中，操作 $ \otimes $ 称为 tensor product (或 Kronecker product) 的矢量。 请注意，尽管我们始终可以采用两个 qubit 状态的 tensor 产品来形成两 qubit 状态，但并不是所有的 qubit 量程状态都可以作为两个单 tensor 状态的 qubit 产品来编写。
例如，没有状态，因此 $ \psi = \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ 它们的 $ \phi = \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $ tensor 产品是     

$$\psi\otimes\phi = \begin{bmatrix}1/ \sqrt { 2 } \\\\ 0 \\\\ 0 \\\\ 1/ \sqrt { 2 } \end{bmatrix} 。$$ 

这种 qubit 状态（不能编写为单 qubit 状态的 tensor 产品）称为 "放大状态";这两个 qubits 称为 [*放大*](https://en.wikipedia.org/wiki/Quantum_entanglement)。  由于不能将量程状态视为单一 qubit 状态的 tensor 产品，因此，状态保存的信息并不局限于每个 qubits。  相反，该信息在两个状态之间的关联中以非本地方式存储。  此非区域信息是针对传统计算的量程计算的主要区别功能之一，并且对于大量的量程协议（包括 [量程 teleportation](https://github.com/microsoft/Quantum/tree/main/samples/getting-started/teleportation) 和 [量程错误更正](xref:microsoft.quantum.libraries.error-correction)）非常重要。

## <a name="measuring-two-qubit-states"></a>度量 Two-Qubit 状态 ##
测量 qubit 状态与 qubit 度量非常类似。 测量状态

$$
    \begin{bmatrix}
        \alpha_{ 00 } 01 \\\\ \alpha_ { }\\\\ 
        \alpha_{ 10 } 11 \\\\ \alpha_ {}
    \end{bmatrix}
$$

生成 $ 00 $ ，概率为 $ | \alpha _{ 00 } | ^ 2 $ ， $ 01， $ $ 概率 | 为 \alpha_ { 01 } | ^ 2 $ ， $ 10 $ 的概率为 $ | \alpha _{ 10 } | ^ 2 $ ， $ 11 $ 的 $ 概率 | 为 \alpha_ { 11 } | ^ 2 $ 。 变量 $ \alpha _{ 00 } 、 \alpha_ { 01 } 、 \alpha _{ 10 } $ 和 $ 11 \alpha_ { } $ 特意进行了命名，使此连接清晰明了。 完成度量后，如果结果为00，则 $ $ qubit 系统的量程状态已折叠，现在为

$$
    – \equiv
    \begin{bmatrix}
        1 \\\\ 
        0 \\\\ 
        0 \\\\ 
        0 \end{bmatrix} 。
$$

还可以只测量一个 qubit 为两 qubit 的量程状态。 在仅测量其中一个 qubits 的情况下，度量值的影响将稍有不同，因为整个状态不会折叠为计算基础状态，而只是折叠为一个子系统。  换句话说，在这种情况下，只测量一个 qubit 只会折叠其中一个子系统，而不是全部。  

若要查看这一点，请考虑测量以下状态的第一个 qubit，这是通过 $ 在两个 qubits 上将 Hadamard 转换 H 应用于 $ 初始设置为 "0" 状态而形成的： $$
H ^ 2 ( 1 0 1 0) 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1-1 1 1 1 1 1 1 1 { \otimes } \left \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \right = \frac { } { } \begin{bmatrix} & & & \\\\ & & & \\\\ 0 0 & & & \\\\ & & & \end{bmatrix} \begin{bmatrix} \\\\ \\\\ \\\\ 0 \end{bmatrix} = \frac { 1 } { 2 1 1 1 } \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} \mapsto \begin{cases} \text { 结果 } = 0 & \frac { 1 } { \sqrt { 2 } } \begin{bmatrix} 1 \\\\ 1 \\\\ 0 \\\\ 0 \end{bmatrix} \\\\ \text { 结果 } = 1 & \frac { 1 } { \sqrt { 2 } } \begin{bmatrix} 0 \\\\ 0 \\\\ 1 \\\\ \end{bmatrix} \\\\ \end{cases} 。  
$$
这两个结果的发生率均为50%。  这两者的结果50% 的概率可以 intuited，这是因为初始量程状态向量在 $ $ $ $ 第一个 qubit 上的 "交换 0" 下是固定的。

用于度量第一个或第二个 qubit 的数学规则非常简单。  如果我们让 $ e_k $ 成为 $ k ^ { \rm 的第 i } $ 个计算基准向量，并使 $ S $ 成为所有 e_k 的集合， $ 以使 $ 所涉及的 qubit 获取该值 k 的值 $ 1 $ $ $ 。  例如，如果对度量第一个 qubit 感兴趣，则 $ $ 会包含 $ e_1 \equiv 10 $ 和 $ e_3 \equiv 11 $ 。  同样，如果对第二个 qubit 感兴趣，则 $ $ 会包含 $ e_2 \equiv 01 $ 和 $ e_3 \equiv 11 $ 。  那么，将所选 qubit 测量为1的概率表示 $ $ 状态向量 $\psi$

$$
P (\text { 结果 } = 1) = \sum _ { \text { } e_k e_k } \psi ^ \dagger e_k ^ \dagger \psi 。
$$

> [!NOTE]
> 在本文档中，我们使用的是小字节序格式来标记计算基础。 在 little endian 格式中，最小的有效位数首先是。 例如，以小字节序格式表示的四个数字由 bits 001 的字符串表示。

由于每个 qubit 度量值只能产生 $ 0 $ 或 $ 1，因此度量值0的 $ 概率 $ $ 只是 $ 1-P (\text { 结果 } = 1) $ 。  这就是我们只为测量1的概率显式提供公式的 $ 原因 $ 。

此类测量对状态的操作可以数学表示为

$$
\psi\mapsto \frac{\sum_ { e_k \text { 设置 } } e_k e_k ^ \dagger \psi } { \sqrt { P (\text { 结果 } = 1) } } 。
$$

如果度量值为零，则谨慎读者可能会担心发生了什么情况。  尽管在此情况下，结果状态在技术上是未定义的，但我们永远不需要担心此类不测，因为概率为零！


如果我们 $ \psi $ 将作为前面给出的统一状态向量，并对度量第一个 qubit 感兴趣，则 

$$
P (\text { 度量第一个 qubit } = 1) = (\psi ^ \dagger e_1) # B4 e_1 ^ \dagger \psi) + (e_3) \psi ^ \dagger # B8 e_3 ^ \dagger \psi) = | e_1 ^ \dagger \psi | ^ 2 + | e_3 ^ \dagger \psi | ^ 2。
$$

请注意，这只是测量结果10和11所需的两个概率的总和，就是 $ $ $ $ 所有 qubits。
对于我们的示例，此值的计算结果为

$$
\frac{1 } { 4 } \left | \begin{bmatrix} 0 & 0 & 1 & 0 1 1 1 1 \end{bmatrix} \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} \right | ^ 2 + \frac { 1 } { 4 0 0 0 1 1 1 1 } \left | \begin{bmatrix} & & & \end{bmatrix} \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} \right | ^ 2 = \frac { 1 } { 2 } 。
$$

这完全匹配了我们的直觉告诉我们的概率。  同样，可以将状态编写为

$$
\frac{\frac{e_1 } { 2 } + \frac { e_3 } { 2 } } { \sqrt { \frac { 1 } { 2 } } } = \frac { 1 } { \sqrt { 2 } } \begin{bmatrix} 0 \\\\ 0 \\\\ 1 \\\\ 1\end{bmatrix}
$$

再次遵循我们的直觉。

## <a name="two-qubit-operations"></a>Two-Qubit 操作
与 qubit 情况一样，任何单一转换都是对 qubits 的有效操作。 通常，n qubits 上的单一 $ 转换 $ 是 $ $ 大小为 $ 2 ^ n \times 2 ^ n (的矩阵 U， $ 因此它作用于大小为 $ 2 ^ n) 的向量 $ ，如 $ u ^ { -1 } = U ^ \dagger $ 。
例如，CNOT-CONTAINS (控制-NOT) 门是一种常用的 qubit 门，由以下单一矩阵表示：

$$
\operatorname{CNOT-CONTAINS } = \begin{bmatrix} 1 \ 0 \ 0 \ 0  \\\\  0 \ 1 \ 0 \ 0 \\\\  0 \ 0 \ 0 \ 1 \\\\  0 \ 0 \ 1 \ 0 \end{bmatrix}
$$

我们还可以通过在两个 qubits 上应用 qubit 入口来形成两 qubit 入口。 例如，如果我们应用入口 

$$
\begin{bmatrix}
a b \\\\ c d \end{bmatrix}
$$

和

$$\begin{bmatrix}
e \ f \\\\ g \ h \end{bmatrix}
$$

对于第一个和第二个 qubits，这相当于应用其 tensor 产品指定的 qubit 单一项： $$\begin{bmatrix}
a b \\\\ c d \end{bmatrix}
\otimes 
\begin{bmatrix}
e \ f \\\\ g \ h \end{bmatrix}=
    \begin{bmatrix}
    ae \ af \ \ bf \\\\
    ag \ ah \ bg \ bh \\\\
    ce \ cf \ de \ df \\\\
    cg \ ch \ dg \ dh \end{bmatrix} 。$$
这样，我们就可以通过 tensor 的产品来构建一些已知 qubit 入口的 qubit 入口。 Qubit 入口的一些示例包括 $ h \otimes h $ 、 $ x \otimes \boldone $ 和 $ x \otimes Z $ 。

请注意，尽管任意两个 qubit 入口通过 tensor 产品来定义两 qubit 入口，但反之并不成立。 并非所有 qubit 入口都可以编写为 qubit 入口的 tensor 产品。  此类入口称为 *entangling* 入口。 Entangling 入口的一个示例是 CNOT-CONTAINS 入口。

受控-not 入口后面的直觉可以通用化为任意入口。  通常，受控制的入口是一个入口，它充当标识 (ie 没有操作) ，除非特定 qubit 为 $ 1 $ 。  在此示例中，在标记为 x 的 qubit 上， $ $ 使用 $ \Lambda \_ x (U) $ 来表示受控单一。  例如， $ \Lambda _0 (u) e \_ { 1 } \otimes { \psi } = e \_ { 1 } \otimes u { \psi } $ 和 $ \Lambda \_ 0 (u) e \_ { 0 } \otimes { \psi } = e \_ { 0 } \otimes { \psi } $ ，其中 $ e \_ 0 $ 和 $ e \_ 1 $ 是对应于值 $ 0 $ 和1的单个 qubit 的计算基础向量 $ $ 。  例如，请考虑以下受控- $ Z $ 门，然后我们可以将此表示为 $$
\Lambda\_0 (Z) 1 0 0 0 0 1 0 0 0 0 0 = \begin{bmatrix} & & & \\\\ & & & \\\\ & & 1 & 0 \\\\ 0 0 & & & -1 \end{bmatrix} = (\boldone \otimes H) \operatorname { cnot-contains } (\boldone \otimes h) 。
$$

有效地构建受控 unitaries 是一项重大挑战。  实现此操作的最简单方法就是构建一个受控版本的基本入口数据库，并将原始单一操作中的每个基本入口替换为其受控对应项。  这通常是一种浪费的浪费，通常可用于将几个入口替换为受控版本来实现同样的效果。  出于此原因，我们提供了一种简单的方法来执行控制或允许用户定义单一受控版本（如果已知优化的手动优化版本）的功能。

还可以使用传统信息控制入口。  例如，经典控制的不是一个典型的非入口，但仅当传统位为 $ 1 而不是一个量程位时，它才适用 $ 。  从这种意义上讲，可以将经典控制的入口看作是量程代码中的 if 语句，其中的门仅应用于代码的一个分支。


就像在 qubit 情况下，如果有4个 qubit 的入口 $ \times $ 矩阵可通过此集的产品/服务的任意精度来逼近，则这是通用的。
通用入口集的一个示例是 Hadamard 门、T 门和 CNOT-CONTAINS 入口。 通过采用这些入口的产品，我们可以将两个 qubits 上的任何单一矩阵近似。

## <a name="many-qubit-systems"></a>Many-Qubit 系统
我们按照两个 qubit 案例中所述的完全相同的模式，从较小的系统生成 qubit 的量程状态。  此类状态是通过构建较小状态的 tensor 产品生成的。  例如，请考虑 $ $ 对量程计算机中的位字符串1011001进行编码。  我们可以将此编码为

$$
1011001 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 0 0 1 \\\\ \end{bmatrix} \otimes \begin{bmatrix} 0 1 \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} 。
$$

量程入口的工作方式完全相同。  例如，如果想要将 $ X 门应用于 $ 第一个 qubit，然后在第二个和第三个 qubits 之间执行 cnot-contains，则可以将此转换表示为

\begin{align}
& (X \otimes \operatorname { cnot-contains } _ { 12 } \otimes \boldone \otimes \boldone \otimes \boldone \otimes \boldone) \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1\end{bmatrix}\\\\
&\qquad\qquad\equiv 0011001。 \end{align}

在许多 qubit 的系统中，通常需要分配和解除分配用作量程计算机的临时内存的 qubits。  此类 qubit 称为 ancilla。  默认情况下，我们假定 qubit 状态初始化为 $ $ 在分配时 e_0。  接下来，我们会进一步假定在 $ 释放之前再次返回 e_0 $ 。  这一假设非常重要，因为如果 ancilla qubit 在被解除分配后会与另一个 qubit 注册放大，则解除分配的过程将损坏 ancilla。  出于此原因，我们总是会假设此类 qubits 在发布之前会恢复到其初始状态。

最后，尽管需要将新入口添加到设置为实现两个 qubit 量程计算机的通用量程计算的入口，但在多 qubit 情况下，不需要引入新的入口。  入口 $ H $ 、 $ T $ 和 cnot-contains 构成了许多 qubits 上的通用门集，因为任何常规的单一转换都可以分解为一系列的两 qubit 旋转。  接下来，我们可以利用针对双 qubit 案例开发的理论，并在有许多 qubits 时再次使用。

虽然我们一直在使用的线性代数表示法可以用来描述多 qubit 状态，但随着状态的增加，这会变得越来越繁琐。  对于长度为7位的字符串，生成的列向量为 $ 128 $ 维，这使得使用前面所述的表示法来表示它非常繁琐。  出于此原因，我们接下来在量程计算中显示一个常见的表示法，使我们能够简明地描述这些三维向量。
