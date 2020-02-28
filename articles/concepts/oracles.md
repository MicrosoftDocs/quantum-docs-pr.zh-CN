---
title: 量子预言机
description: 了解如何使用和定义量程 oracles、用于作为其他算法的输入的黑色框操作。
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
ms.topic: article
ms.openlocfilehash: 1d1d0b0903db8e994166c3e8a5798f70742a1c7e
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904921"
---
# <a name="quantum-oracles"></a>量程 Oracles

Oracle $O $ 是一个 "黑色框" 操作，用于作为其他算法的输入。
通常，此类操作使用传统函数定义 $f： \\{0，1\\} ^ n \to \\{0，1\\} ^ m $，这将采用 $n $ 位二进制输入，并生成 $m $ 位二进制输出。
为此，请考虑使用特定的二进制输入 $x = （x_{0}，x_{1}，\dots ..，x_ {n-1}） $。
我们可以将 qubit 状态标记为 $ \ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_ {n-1}} $。

我们可能首先尝试定义 $O $，$O \ket{x} = \ket{f （x）} $，但这会有几个问题。
首先，$f $ 可能会有不同的输入和输出大小（$n \ne m $），因此应用 $O $ 将更改寄存器中的 qubits 数。
其次，即使 $n = m $，函数也可能不可逆：如果 $f （x） = f （y） $ （对于某些 $x \ne y $），则 $O \ket{x} = O\ket {y} $ 但 $O ^ \dagger O\ket {x} \ne O ^ \dagger O\ket {y} $。
这意味着我们无法构造 adjoint 操作 $O ^ \dagger $，oracles 必须为其定义 adjoint。

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a>通过其对计算基础状态的影响来定义 oracle
我们可以通过引入 $m $ qubits 的第二个寄存器来处理这两个问题。
然后，我们将定义 oracle 对所有计算基础状态的影响：对于所有 $x \in \\{0，1\\} ^ n $ 和 $y \in \\{0，1\\} ^ m $，

$ $ \begin{align} O （\ket{x} \otimes \ket{y}） = \ket{x} \otimes \ket{y \oplus f （x）}。
\end{align} $ $

现在，按构造 $O = O ^ \dagger $，因此我们解决了上述两个问题。

> [!TIP]
> 若要查看 $O = O ^ {\dagger} $，请注意 $O ^ 2 = \boldone $，因为 $a \oplus b \oplus b = a 表示所有 $a，b \in \{0，1\}$。
> 因此，$O \ket{x} \ket{y \oplus f （x）} = \ket{x} \ket{y \oplus f （x） \oplus f （x）} = \ket{x} \ket{y} $。

重要的是，以这种方式为每个计算基础状态 $ \ket{x}\ket{y} $ 定义 oracle 时，还会定义 $O $ 如何处理任何其他状态。
这是因为 $O $ （与所有量程操作一样）都是线性处于其作用的状态。
例如，假设 Hadamard 操作由 $H \ket{0} = \ket{+} $ 和 $H \ket{1} = \ket{-}$ 定义。
如果希望了解 $H $ 如何处理 $ \ket{+} $，可以使用 $H $ 是线性的，

$ $ \begin{align} H\ket {+} & = \frac{1}{\sqrt{2}} H （\ket{0} + \ket{1}） = \frac{1}{\sqrt{2}} （H\ket{0} + H\ket{1}） \\\\ & = \frac{1}{\sqrt{2}} （\ket{{-}+ \ket{0} + \frac12{1}-\ket{0}） = \ket{1}。{0}
\end{align} $ $

如果定义 oracle $O $，则可以同样使用 $n + m $ qubits 上的任何状态 $ \ket{\psi} $ 都可以编写为

$ $ \begin{align} \ket{\psi} & = \ sum_ {x \in \\{0，1\\} ^ n，y \in \\{0，1\\} ^ m} \alpha （x，y） \ket{x} \ket{y} \end{align} $ $

其中 $ \alpha： \\{0，1\\} ^ n \times \\{0，1\\} ^ m \to \mathbb{C} $ 表示状态 $ \ket{\psi} $ 的系数。 因此

$ $ \begin{align} O \ket{\psi} & = O \ sum_ {x \in \\{0，1\\} ^ n，y \in \\{0，1\\} ^ m} \alpha （x，y） \ket{x} \ket{y} \\\\ & = \ sum_ {x \in \\{0，1\\} ^ n，y \in \\{0，1\\} ^ m} \alpha （x，y） O \ket{x} \ket{y} \\\\ & = \ sum_ {x \in \\{0，1\\} ^ n，y \in \\{0，1\\} ^ m} \alpha （x，y） \ket{x} \ket{y \oplus f （x）}。
\end{align} $ $

## <a name="phase-oracles"></a>阶段 oracles
此外，我们还可以通过应用基于输入 $O $ 的_阶段_，将 $f $ 编码为 oracle $O $。
例如，我们可能会定义 $O $，$ $ \begin{align} O \ket{x} = （-1） ^ {f （x）} \ket{x}。
\end{align} $ $ 如果某阶段 oracle 最初在计算基础状态 $ \ket{x} $ 中操作，则此阶段是全局阶段，因此不能观察到。
但如果应用于 superposition 或作为受控操作，此类 oracle 可能是非常强大的资源。
例如，假设有一个阶段 orcale $O _f $ 用于 qubit 函数 $f $。
然后，$ $ \begin{align} O_f \ket{+} & = O_f （\ket{0} + \ket{1}）/\sqrt{2} \\\\ & = （（-1） ^ {f （0）} \ket{0} + （-1） ^ {f （1）} \ket{1}）/\sqrt{2} \\\\ & = （-1） ^ {f （0）} （\ket{0} + （-1） ^ {f （1）-f （0）} \ket{1}）/\sqrt{2} \\\\ & = （-1） ^ {f （0）} Z ^ {f （0）-f （1）} \ket{+}。
\end{align} $ $

更常见的情况是，oracles 的两个视图都可以扩大了，以表示返回实数而不只是一位的传统函数。

选择实现 oracle 的最佳方式很大程度上取决于 oracle 在给定算法中的使用方式。
例如， [Deutsch-Jozsa 算法](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm)依赖于第一种方式实现的 oracle，而[Grover 的算法](https://en.wikipedia.org/wiki/Grover's_algorithm)依赖于第二个方法实现的 oracle。


有关更多详细信息，我们建议在[Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465)中进行讨论。
