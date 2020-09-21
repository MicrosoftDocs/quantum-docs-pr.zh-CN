---
title: 量程 Dynamics
description: 了解量程动态与经典 dynamics 之间的相似性和差异。
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.quantumdynamics
no-loc:
- Q#
- $$v
ms.openlocfilehash: fb54416ecdc38ea90999f33cb673c2c9e4c5f8d7
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833867"
---
# <a name="quantum-dynamics"></a>量程 Dynamics

量程机制在很大程度上是对量程动态的调查，它设法理解初始量程状态 $ \ket{\psi (0) } $ 随时间而变化 ([查看有关 Dirac](xref:microsoft.quantum.concepts.dirac) 表示法) 的详细信息。
具体来说，假设此初始条件为量程状态、dynamical 系统的演变时间和规范、量程状态 $ \ket{\psi (t) } $。
在继续解释量子 dynamics 之前，采取一步操作并考虑传统 dynamics 会很有用，因为它可让你深入了解量程机制与传统动态的不同之处。

在传统 dynamics 中，我们从牛顿的第二个定律中了解，微粒的位置根据 $F (x，t) = ma = m\frac {\ dd ^ 2} {\dd t ^ 2} {x} (t) $，其中 $F (x，t) $ 为强制，$m $ 为大容量，$a $ 为加速。
然后，假设初始位置 $x (0) $、演化时间 $t $，以及对该粒子执行操作的强制说明，我们可以通过对由 $x () $ 的牛顿方程指定的差异公式，找到 $x ($) $。
以这种方式指定力就是一个难题。
因此，我们经常会根据系统的潜在能量来表达力，这为我们的 $-\ partial_x V (x，t) = m \frac{\dd ^ 2} {\dd t ^ 2} {x} (t) $。
因此，对于粒子，系统的 dynamics 只能由潜在能源函数、粒子质量和演化时间来指定。

对于超出 $F = ma $ 的传统 dynamics，通常会引入更广泛的语言。
一种表述（特别适用于量子机制）是 Hamiltonian 的机制。
在 Hamiltonian 机制中，系统和 (一般化) 位置和 momenta 的总能量为说明任意传统对象的运动所需的所有信息。
具体而言，让 $f (x，p，t) $ 是系统 $x $ 和 momenta $p $ 的某个通用化位置函数，并允许 $H x，p，t ($ 为 Hamiltonian 函数。
例如，如果采用 $f (x，p，t) = x (t) $ and $H (x，p，t) = p ^ 2 ()  ($，则会恢复上述 Newtonian dynamics 情况。
在通用性下，我们将 \begin{align} \frac{d}{dt} f &= \ partial_t f- ( \ partial_x H \ partial_p f + \ partial_p H \ partial_x f) \\ \\ & \defeq \ partial_t f + \\ {f，H \\ }。
此处的 \end{align} $ \\ {f，H \\ } $ 称为 [泊松形括号](https://en.wikipedia.org/wiki/Poisson_bracket) ，由于它在定义 dynamics 中扮演的中心角色，它在经典 dynamics 中显示为普遍。

可以使用完全相同的语言描述量程 dynamics。
Hamiltonian 或总能量会完全指定任何闭合的量程系统的动态。
但是，这两个理论之间的差别很大。
在传统的机制中 $x $ 和 $p $ 只是数字，而在量程结构中则不是这样。
的确，它们甚至不是在上下班： $xp \ne px $。

描述这些非上下班途中对象的正确的数学概念是一个运算符，在这种情况下，$x $ 和 $p $ 只能采用一组离散的值，这两个值与矩阵的概念相符。
因此，为了简单起见，我们假定量程系统是有限的，因此可以使用 [向量和矩阵](xref:microsoft.quantum.concepts.vectors)进行描述。
我们进一步要求这些矩阵是 Hermitian 的 (意味着矩阵的共轭换位与原始矩阵) 相同。
这可以确保这些矩阵的本征值是真实值;我们要做的一个条件是，当我们测量的数量类似于无法返回虚数的位置时。

正如物中的位置和势头势头需要用运算符替换的一样，Hamiltonian 函数需要替换为运算符。
例如，对于可用空间中的粒子，$H (x，p) = p ^ 2/2m $，而在量程机制中，Hamiltonian 运算符 $ \hat{H} $ 是 $ \hat{H} = \hat{p} ^ 2/2m $，其中 $ \hat{p} $ 是动力运算符。
从这一角度来看，从经典到量子 dynamics，只涉及到用运算符替换普通 dynamics 中使用的变量。
一旦我们通过将普通的古典 Hamiltonian 转换为量子语言来构造 Hamiltonian 运算符，我们就可以通过 \begin{align} \frac{d}{dt} \hat{f} = \ partial_t \hat{f} + [\hat{f}，\hat{H}]，\end{align} （其中 $ [f，H] = fH-Hf $ 称为 commutator，来表示任意量子机械 (数量的动态)  () 。
此表达式与上面给出的传统表达式的不同之处在于，泊松括号 $ \\ {f，H \\ } $ 替换为 $f $ 和 $H $ 之间的 commutator。
这一过程采用传统的 Hamiltonian，并使用它来查找量程 Hamiltonian，在量程术语中称为规范量化。

哪些操作员 $f $ 是最感兴趣的？  此问题的答案取决于要解决的问题。
最有用的要查找的数量或许是量程状态运算符，如前面的概念文档中所讨论的那样，可以使用它来提取想要了解 dynamics 的所有内容。
执行此操作后 (并将结果简化为一个具有纯状态) 的情况，将发现量程状态的 Schrödinger 公式 \begin{align} i \ partial_t \ket{\psi (t) } = \hat{H} (t) \ket{\psi (t) }。
\end{align}

尽管此公式可能不如上面给出的直观，但它可能是了解如何模拟量程或传统计算机上的量子 dynamics 的最简单的表达式。
这是因为，对于差异公式的解决方案，如果 Hamiltonian 是 $t $) \begin{align} \ket{\psi (t) } = e ^ {-iHt} \ket{\psi (0) } 中的常量，则可以采用以下形式 (。
\end{align} 此处 $e ^ {-iHt} $ 是单一矩阵。
这意味着，存在可用于执行它的量程线路，因为量程计算机可以非常接近任何单一矩阵。
这是一种查找量程线路来实现量程时间演化运算符的行为，$e ^ {-iHt} $ 就是所谓的量程模拟，或特别 dynamical 的量程模拟。
