---
标题：量程计算说明中的矢量和矩阵：了解有关如何使用向量和矩阵的基本知识。
author： QuantumWriter uid：： nawiebe@microsoft.com ms. 日期：12/11/2017 毫秒。主题：项目不相关：
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

# <a name="vectors-and-matrices"></a>向量和矩阵

熟悉矢量和矩阵对于了解量程计算至关重要。 我们提供了以下简短简介，并建议读者阅读有关线性代数（如*Strang、 (1993) 的标准引用。线性代数简介 () 。Wellesley、MA： Wellesley-剑桥按下*或联机引用，如[线性代数](http://joshua.smcvt.edu/linearalgebra/)。

列向量 (或只是[*矢量*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $ v of $ dimension (或 size) $ n $ 为 $ n 复数的集合 $ (v_1 $ 、v_2、\ldots、v_n) $ 排列为一列：

$$v =\begin{bmatrix}
v_1\\\\
v_2\\\\
\vdots\\\\
v_n\end{bmatrix}$$

向量 v 的标准 $ $ 定义为 $ \sqrt { \sum \_ i i | \_ i i | ^ 2 } $ 。 矢量称为单位规范 (或如果其标准为1，则称为[*单位矢量*](https://en.wikipedia.org/wiki/Unit_vector)) $ $ 。 向量 v 的[*adjoint*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ $ 表示 $ v ^ \dagger $ ，并定义为以下行向量 $ \* $ ，其中表示复数共轭。

$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix} ^ \dagger = \begin{bmatrix} v_1 ^ * & \cdots & v_n ^ *\end{bmatrix}$$

将两个矢量相乘的最常见方法是通过[*内部产品*](https://en.wikipedia.org/wiki/Inner_product_space)（也称为点积）。  内部产品提供了一个向量的投影到另一个向量，这在描述如何将一个向量表达为其他更简单的向量的总和方面非常有用。  U 和 v 之间的内部积 $ $ $ $ ，表示 $ \left \langle u，v \right \rangle $ 定义为

$$
\langleu，v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } v_1 + \cdots + u \_ n ^ { \* } v \_ n。
$$

此表示法还允许将 vector v 的 $ 标准 $ 编写为 $ \sqrt { \langle v，v \rangle } $ 。

我们可以将一个向量与数字 $ c 相乘 $ ，以形成一个新向量，其项乘以 $ c $ 。 我们还可以添加两个向量 $ u $ 和 v， $ $ 以形成新的向量，其项是 $ u $ 和 v 项的 $ 总和 $ 。 这些操作如下所示：

$$\mathrm{如果为 } ~ u=\begin{bmatrix}
u_1\\\\
u_2\\\\
\vdots\\\\
u_n \end{bmatrix} ~ \mathrm { 和}~
向量=\begin{bmatrix}
    v_1\\\\
    v_2\\\\
    \vdots\\\\
    v_n \end{bmatrix} ， ~ \mathrm { 然后}~
au + bv=\begin{bmatrix}
au_1 + bv_1\\\\
au_2 + bv_2\\\\
\vdots\\\\
au_n + bv_n \end{bmatrix} 。
$$

大小[*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics))为 $ m n 的 \times 矩阵 $ 是 $ $ 按 $ m 行和 n 列排列的 mn 复数的集合，如下 $ $ $ 所示：

$$年= 
\begin{bmatrix}
M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1n}\\\\
M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2n}\\\\
\ddots\\\\
M_ { m1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { mn}\\\\
\end{bmatrix}.$$

请注意，维度 n 的 $ 矢量 $ 只是大小为 $ n 1 的 \times 矩阵 $ 。 对于向量，我们可以将矩阵与数字 c 相乘， $ $ 以获取一个新矩阵，其中每个条目都与 $ c 相乘 $ ，并且我们可以添加两个相同大小的矩阵，以生成一个新矩阵，其项是两个矩阵的相应项的总和。 

## <a name="matrix-multiplication-and-tensor-products"></a>Matrix 乘法 and Tensor Products

我们还可以将 dimension m n 和 n 维度 n p 的两个矩阵相乘， $ $ $ \times $ $ $ $ \times $ 以获取 $ $ dimension m p 的新 matrix p， $ \times $ 如下所示：

\begin{align}
&\begin{bmatrix}
    M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1n}\\\\
    M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2n}\\\\
    \ddots\\\\
    M_ { m1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { mn}
\end{bmatrix}
\begin{bmatrix}
N_ { 11 } ~~ N_ { 12 } ~~ \cdots ~~ N_ { 1 p}\\\\
N_ { 21 } ~~ N_ { 22 } ~~ \cdots ~~ N_ { 2 p}\\\\
\ddots\\\\
N_ { n1 } ~~ N_ { n2 } ~~ \cdots ~~ N_ { np}
\end{bmatrix}=\begin{bmatrix}
P_ { 11 } ~~ P_ { 12 } ~~ \cdots ~~ P_ { 1 p}\\\\
P_ { 21 } ~~ P_ { 22 } ~~ \cdots ~~ P_ { 2 p}\\\\
\ddots\\\\
P_ { m1 } ~~ P_ { m2 } ~~ \cdots ~~ P_ { mp}
\end{bmatrix}
\end{align}

其中，P 条目 $ $ $ P_ { ik } = \sum _j M_ { ij } N_ { jk } $ 。 例如，条目 $ P_ { 11 } $ 是 M 第一行的第一行的第一 $ 列， $ 第一列是 $ N $ 。请注意，由于矢量只是矩阵的一种特殊情况，因此此定义延伸到矩阵向量乘法。 

我们考虑的所有矩阵均为方形矩阵，其中的行数和列数相等，或向量仅对应于 $ 1 $ 列。 一个特殊的正方形矩阵是表示的[*标识矩阵*](https://en.wikipedia.org/wiki/Identity_matrix)， $ \boldone $ 它的所有对角线元素都等于 $ 1， $ 剩余元素等于 $ 0 $ ：

$$\boldone=\begin{bmatrix}
1 ~~ 0 ~~ \cdots ~~ 0\\\\
0 ~~ 1 ~~ \cdots ~~ 0\\\\
~~ \ddots\\\\
0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix} 。$$

对于正方形矩阵 $ a $ ，我们说， $ $ 如果 AB BA，矩阵 B 是[*相反*](https://en.wikipedia.org/wiki/Invertible_matrix)的 $ = = \boldone $ 。 矩阵的逆矩阵不需要存在，但如果它存在，则它是唯一的，并 $ 将其表示为 ^ { -1 } $ 。 

对于任何矩阵 $ m $ ，m 的 adjoint 或共轭转 $ 置 $ 为 matrix $ N， $ 以便 $ N_ { ij } = M_ { ji } ^ \* $ 。 M 的 adjoint $ $ 通常表示为 $ m ^ \dagger $ 。 $ $ 如果为[*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) $ UU ^ \dagger = u ^ \dagger u = \boldone $ 或等效 $ 项 u ^ { -1 } = u ^ \dagger $ ，则假设矩阵 U 为单一矩阵。  单一矩阵的最重要的属性可能是它们保留向量的标准。  出现这种情况的原因是 

$$\langlev、v \rangle = v ^ \dagger v = v ^ \dagger u ^ { -1 } U v = v ^ \dagger u ^ \dagger u v = \langle u v、u v \rangle 。$$  

$ $ 如果[*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) $ m m ^，则认为矩阵 M 是 Hermitian 的 = \dagger $ 。

最后， [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (或 Kronecker product) 2 个2个矩阵，大小为 $ p q 的2个矩阵 $ $ \times $ ，第 n 个大小 $ $ 为 p q，为大小为 $ \times $ $ = \otimes $ 的 $ mp \times nq $ ， $ 并 $ $ 按如下所示从 M 和 n 获取 $ ：

\begin{align}
    M \otimes N&=
    \begin{bmatrix}
        M_ { 11 } ~~ \cdots ~~ M_ { 1n }\\\\
        \ddots\\\\
        M_ { m1 } ~~ \cdots ~~ M_ { mn  }
    \end{bmatrix}
    \otimes
    \begin{bmatrix}
        N_ { 11 } ~~ \cdots ~~ N_ { 1q  }\\\\
        \ddots\\\\
        N_ { p1 } ~~ \cdots ~~ N_ { pq}
    \end{bmatrix}\\\\
    &=
    \begin{bmatrix}
        M_ { 11 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq } \end{bmatrix} ~~ \cdots  ~~ 
        M_ { 1n } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq }  \end{bmatrix}\\\\
        \ddots\\\\
        M_ { m1 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq } \end{bmatrix} ~~ \cdots  ~~ 
        M_ { mn } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq }  \end{bmatrix}
    \end{bmatrix}.
\end{align}

下面的示例对此进行了更好的演示：

$$
    \begin{bmatrix}
        a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}=
    \begin{bmatrix}
        \begin{bmatrix}c \\\\ d \\\\ e\end{bmatrix}
        \\\\[1.5 em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}
    \end{bmatrix}
    =\begin{bmatrix}a c a \\\\ d \\\\ a e \\\\ b c \\\\ b d \\\\\end{bmatrix}
$$

和

$$
    \begin{bmatrix}
        a b \\\\ c d\end{bmatrix}
    \otimes 
    \begin{bmatrix}
        e \ f \\\\ g \ h\end{bmatrix}
     =
    \begin{bmatrix}
    的\begin{bmatrix}
    e \ f \\\\ g \ h\end{bmatrix}
    b\begin{bmatrix}
    e \ f \\\\ g \ h\end{bmatrix}
    \\\\[1em] c\begin{bmatrix}
    e \ f \\\\ g \ h\end{bmatrix}
    2-d\begin{bmatrix}
    e \ f \\\\ g \ h\end{bmatrix}
    \end{bmatrix}
    =
    \begin{bmatrix}
    ae \ af \ \ bf\\\\
    ag \ ah \ bg \ bh\\\\
    ce \ cf \ de \ df\\\\
    cg \ ch \ dg \ dh \end{bmatrix} 。
$$

围绕 tensor 产品的最终有用的符号约定是：对于任何 vector $ v $ 或 matrix $ m $ ， $ v ^ { \otimes n } $ 或 $ M ^ { \otimes n } $ 对于 $ n $ 折重复 tensor 产品而言是短期的。  例如：

\begin{align}
&\begin{bmatrix}1 \\\\ 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ， \qquad \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ 0 0 0 \\\\ \\\\ 0 \end{bmatrix} ， \qquad \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ -1 \\\\ -1 \\\\ 1 \end{bmatrix} ，\\\\
  &\begin{bmatrix}0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ， \qquad \begin{bmatrix} 0 & 1 \\\\ 1 & 0 2 0 0 0 0 \end{bmatrix} ^ { \otimes } = \begin{bmatrix} & & & \\\\ & 0 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 1 & 0 & & \end{bmatrix} 0 0。
\end{align}
