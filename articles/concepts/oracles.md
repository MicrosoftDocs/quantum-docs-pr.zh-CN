---
title：量程 oracles 说明：了解如何使用和定义量程 oracles、用于作为其他算法的输入的黑色框操作。
author： cgranade uid： oracles。作者： Christopher.Granade@microsoft.com ms. 日期： 07/11/2018 ms. 主题：项目不相关：
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
# <a name="quantum-oracles"></a>量程 Oracles

Oracle $ O $ 是一个 "黑色框" 操作，用于作为其他算法的输入。
通常，此类操作使用传统函数 $ f： \\ { 0、1 \\ } ^ n \to \\ { 0、1 ^ m 进行定义， \\ } $ 该函数采用 $ n $ 位二进制输入并生成一个 $ m $ 位二进制输出。
为此，请考虑使用特定的二进制输入 $ x = (x_ { 0 } ，x_ { 1 } ，\dots ..，x_ { n-1 }) $ 。
我们可以将 qubit 状态标记为 $ \ket { \vec { x } } = \ket { x_ { 0 } } \otimes \ket { x_ { 1 } } \otimes \cdots \otimes \ket { x_ { n-1 } } $ 。

我们可能首先尝试定义 $ o， $ 使 $ o \ket { x } = \ket { f (x) } $ ，但这有一些问题。
首先， $ f 的 $ 输入和输出大小可能不同 ($ n \ne m $) ，因此，应用 $ O $ 将更改寄存器中的 qubits 数目。
其次，即使 $ n = m $ ，函数也不能可逆：如果 $ f (x) = f (y) $ 对于某些 $ x \ne y $ ，则为 $ o \ket { x } = o \ket { y } $ 但 $ o ^ \dagger O \ket { x o x o x o x o x o x o x o x o x o } \ne \dagger \ket { y } $ 。
这意味着我们无法构造 adjoint 操作 $ O ^ \dagger $ ，oracles 必须为其定义 adjoint。

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a>通过其对计算基础状态的影响来定义 oracle
我们可以通过引入另一个 $ m qubits 注册来解决这两个问题 $ 。
然后，将为所有计算基础状态定义 oracle 的效果：对于所有 $ x \in \\ { 0、1 \\ } ^ n $ 和 $ y \in \\ { 0，1 \\ } ^ m $ ，

$$
\begin{align}
    O (\ket { x } \otimes \ket { y }) = \ket { x } \otimes \ket { y \oplus f (x) } 。
\end{align}
$$

现在 $ = \dagger $ ，我们已解决了这两个以前的问题。

> [!TIP]
>若要查看 $ o = o ^ { \dagger } $ ，请注意 $ o ^ 2， = \boldone $ 因为 $ \oplus b \oplus b = a $ for all $ a，b \in \: ：： no-loc ( {) ：：：0，1 \: ：： no loc (} ) ：：： $ 。
>因此， $ O \ket { x } \ket { y \oplus f (x) } = \ket { x } \ket { y \oplus f (x) \oplus f (x) x } = \ket { } \ket { y } $ 。

重要的是，以这种方式为每个计算基础状态 $ \ket { x y 定义 oracle } \ket { } $ 也定义了 O 如何处理 $ $ 任何其他状态。
这 $ 是因为 O $ （与所有量程操作一样）在其作用于的状态下是线性的。
例如，假设 Hadamard 操作由 $ h \ket { 0 } = \ket { + } $ 和 $ h \ket { 1 定义 } = \ket { - } $ 。
如果我们想要了解 $ h 如何 $ $ \ket { + } $ 操作，可以使用 $ h 作为 $ 线性，

$$
\begin{align}
H \ket { + } & = \frac { 1 } { \sqrt { 2 } } H (\ket { 0 }  +  \ket { 1 }) = \frac { 1 } { \sqrt { 2 } } (h \ket { 0 } + h \ket { 1 }) \\\\
           &= \frac{1 } { \sqrt { 2 } } (\ket { + }  +  \ket { - }) = \frac 12 (\ket { 0 }  +  \ket { 1 }  +  \ket { 0 }  -  \ket { 1 }) = \ket { 0 } 。
\end{align}
$$

在定义 oracle O 的情况下 $ $ ，我们可以同样使用 $ \ket { \psi } $ $ n + m qubits 上的任何状态都 $ 可以编写为

$$
\begin{align}
\ket{\psi}& = \sum_ { x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha (x、y) \ket { x } \ket { y}
\end{align}
$$

其中 $ \alpha ： \\ { 0，1 \\ } ^ n \times \\ { 0，1 \\ } ^ m \to \mathbb { C } $ 表示状态的系数 $ \ket { \psi } $ 。 因此，

$$
\begin{align}
O \ket { \psi } & = o \sum _ { x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha (x、y) \ket { x } \ket { y } x \\\\ 0 & 、 = 1 ^ n、y 0、1 ^ m (x、y) O \sum _ { \in \\ { \\ } \in \\ { \\ } } \alpha \ket { x } \ket { y }\\\\
             &= \sum _ { x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha (x、y) \ket { x } \ket { y \oplus f (x) } 。
\end{align}
$$

## <a name="phase-oracles"></a>阶段 oracles
此外，我们还可以 $ $ $ $ 通过基于到 O 的输入应用_阶段_，将 f 编码为 oracle $ O $ 。例如，我们可以定义 $ O $ ，使$$
\begin{align}
    O \ket { x } = (-1) ^ { f (x) } \ket { x } 。
\end{align}
$$
如果 oracle 最初在计算基础状态 x 中对寄存器 $ \ket { } $ 进行操作，则此阶段为全局阶段，因此无法观察。
但如果应用于 superposition 或作为受控操作，此类 oracle 可能是非常强大的资源。
例如，请考虑一个阶段 $ $ 为 qubit 函数 $ f O_f $ 。
接着$$
\begin{align}
    O_f\ket{+}
        &=O_f (\ket {0 }  +  \ket { 1 }) / \sqrt { 2 }\\\\
        &= ( # A1-1) ^ { f (0) } \ket { 0 } + () ^ { f (1) } \ket { 1 }) / \sqrt { 2 }\\\\
        &= (-1) ^ { f (0) } (\ket { 0 } + () ^ { f (1)  (} \ket { } \sqrt { } 1) \\\\
        &= (-1) ^ { f (0) } Z ^ { f (0)  (1) } \ket { + } 。
\end{align}
$$

更常见的情况是，oracles 的两个视图都可以扩大了，以表示返回实数而不只是一位的传统函数。

选择实现 oracle 的最佳方式很大程度上取决于 oracle 在给定算法中的使用方式。
例如， [Deutsch-Jozsa 算法](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm)依赖于第一种方式实现的 oracle，而[Grover 的算法](https://en.wikipedia.org/wiki/Grover's_algorithm)依赖于第二个方法实现的 oracle。


有关更多详细信息，我们建议在[Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465)中进行讨论。
