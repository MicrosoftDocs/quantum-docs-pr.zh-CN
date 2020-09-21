---
标题：高级矩阵概念说明：了解本征向量、本征值和 matrix 指数，这是用于描述和模拟量程算法的基本工具。
author： QuantumWriter uid： benbra-advanced： v-ms。 date： 12/11/2017 ms. 主题：项目不是：
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "$$$"
- "$$$"
- "$$$"
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
# <a name="advanced-matrix-concepts"></a>高级矩阵概念 #

现在，我们将矩阵操作扩展到 [*本征值、本征向量*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) 和 [*指数*](https://en.wikipedia.org/wiki/Matrix_exponential) ，这构成了我们需要描述和实现量程算法的一组基本工具。

## <a name="eigenvalues-and-eigenvectors"></a>本征值和本征向量 ##

假设 $ M 是 $ 正方形矩阵， $ v 是 $ 不是全零向量的向量 (即，其所有条目都等于 $ 0) 的矢量 $ 。

假设 $ v $ 是 M 的 [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) ，  $ 如果 $ 将 $ Mv = cv $ 用于某个数字 $ c $ 。 我们说 $ c $ 是对应[*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors)于 eigenvector v 的 eigenvalue $ $ 。 通常 $ ，矩阵 M $ 可以将矢量转换为任何其他向量，但 eigenvector 是特殊的，因为它会保持不变，但会乘以数字。 请注意，如果 $ v $ 是带有 eigenvalue c 的 eigenvector $ $ ，则 $ av $ 也是 $ $ 具有相同 eigenvalue 的任何非零) 的 eigenvector (。

例如，对于恒等矩阵，每个向量 $ v $ 均为 eigenvalue 1 的 $ eigenvector $ 。

作为另一个示例，请考虑这样一种 [*对角矩阵*](https://en.wikipedia.org/wiki/Diagonal_matrix) $ D $ ：

$$
\begin{bmatrix}
d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix} 。
$$

矢量

$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix} ， \begin{bmatrix} 0 \\\\ 1 \\\\ 0 \end{bmatrix} ， \begin{bmatrix} 0 \\\\ 0 \\\\ 1\end{bmatrix}$$

是此矩阵的本征向量，分别为本征值  $ d_1 $ 、 $ d_2 $ 和 $ d_3 $ 。 如果 $ d_1 $ 、 $ d_2 $ 和 $ d_3 $ 都是不同的数字，则这些向量 (，它们的序列号) 是 matrix d 的唯一本征向量 $ $ 。通常，对于对角矩阵，可以轻松地将本征值和本征向量读取。 本征值是显示在对角线上的所有数字，其各自的本征向量是单位矢量，其中一项等于 $ 1 $ ，剩余项等于 $ 0 $ 。

请注意，在上面的示例中，本征向量的 $ D $ 构成三维 $ 向量的基础 $ 。 基础是一组矢量，以便可以将任何矢量编写为它们的线性组合。 更明确、 $ v_1 $ 、 $ v_2 $ 和 $ v_3， $ 如果任何向量 $ v $ 可以编写为 $ v a_1 v_1 + a_2 + v_2 a_3 = $ $ $ 、 $ v_3 $ 和 $ a_1 $ a_2 + a_3 +。

回忆一下，Hermitian 矩阵 (也称为 ") adjoint"，这是一个复杂的正方形矩阵，它相当于其自己的复杂共轭转置，而 "单一矩阵" 是一种复杂的正方形矩阵，其反转等于其 adjoint 或复数共轭转置。
对于 Hermitian 和单一矩阵，它们实质上是在量程计算中遇到的唯一矩阵，一般的结果称为 [*spectral 定理*](https://en.wikipedia.org/wiki/Spectral_theorem)，这会断言以下内容：对于任何 Hermitian 或单一矩阵 $ m $ ，都存在一个单一 U，以便 $ $ $ = \dagger $ 对某些对角线矩阵 d 使用 M u ^ d $ U $ 。而且，D 的对角线条目 $ $ 将是本征值的 $ M $ 。

我们已经知道如何计算对角矩阵的本征值和本征向量 $ $ 。使用此定理，我们知道，如果 $ v $ 是 $ $ 带有 eigenvalue $ c $ （即，Dv cv）的 D 的 eigenvector， $ = $ 则 $ U ^ \dagger v $ 将是 eigenvector $ M $ with eigenvalue $ c $ 。 这是因为

$$M (U ^ \dagger v) = u ^ \dagger d u (u ^ \dagger v) = U ^ \dagger d (u u ^ \dagger) v = u ^ \dagger d v = c u ^ \dagger v。$$

## <a name="matrix-exponentials"></a>Matrix 指数
[*矩阵指数*](https://en.wikipedia.org/wiki/Matrix_exponential)还可以精确地定义为指数函数。  矩阵 a 的矩阵指数 $ $ 可表示为

$$
e ^ A = \boldone + a + \frac { a ^ 2 } { 2！ } + \frac {^ 3 } { 3！}+\cdots
$$

这一点很重要，因为 $ { } $ Hermitian matrix $ B 形式的单一矩阵（形式为 e ^ iB）描述了量子机械时间演变 $ 。 出于此原因，执行 matrix 指数是量程计算的基本组成部分，因此 Q# 提供了用于描述这些操作的内部例程。
有很多方法可用于计算传统计算机上的矩阵指数，一般为数值逼近，这类指数为充满 with 担风险。  请参阅 [*Cleve Moler 和 Charles Van 贷款。"用于计算矩阵指数的可疑方法。"SIAM 评审 20.4 (1978) ： 801-836*](https://doi.org/10.1137/S00361445024180) ，详细了解涉及的挑战。

了解如何计算矩阵指数的最简单方法是通过该矩阵的本征值和本征向量。  具体而言，以上所述的 spectral 定理说明对于每个 Hermitian 或单一矩阵，都 $ $ 存在一个单一的矩阵 $ u $ 和一个对角矩阵 $ D $ ，这 $ 是 = u ^ \dagger d u $ 。 由于 unitarity 的属性，我们有 $ ^ 2 = u ^ \dagger D ^ 2 u $ ，同样适用于任何 power $ p $ $ A ^ p = u ^ \dagger D ^ p u $ 。 如果将此替换为我们获得的运算符指数的运算符定义：

$$
e ^ A = U ^ \dagger \left (\boldone + d + \frac { d ^ 2 } { 2！ } + \cdots \right) U = u ^ \dagger \begin{bmatrix} \exp (D_ { 11 }) & 0 & \cdots & 0 \\\\ 0 & \exp (D_ { 22 }) & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0 & 0 & \cdots & \exp (D_ { NN }) \end{bmatrix} U。$$

换而言之，如果转换为矩阵 A 的 eigenbasis， $ $ 则矩阵指数等效于计算矩阵本征值的普通指数。  由于量程计算中的许多操作都涉及到执行矩阵指数，因此，转换为矩阵的 eigenbasis 以简化执行运算符指数的这一技巧会经常出现，并且是本指南后面部分中讨论的 Trotter – Suzuki 样式的量程模拟方法的基础。

另一种有用的属性是： $ b $ 既是单一的又是 Hermitian 的，即 $ b = b ^ { -1 } = b ^ \dagger $ then $ b ^ 2 = \boldone $ 。 通过将此规则应用于矩阵指数的以上扩展，并将 $ \boldone $ 和 $ B 项组合在 $ 一起，可以看到，对于任何实际值 $ x $ 标识

$$e ^ { iBx } = \boldone \cos (x) + iB\sin (x) $$


保留. 这一技巧特别有用，因为它允许有关操作矩阵指数的原因，即使 b 的维度的 $ $ 大小呈指数大，在 $ b 既是单一的还是 Hermitian 的情况下，也是如此 $ 。
