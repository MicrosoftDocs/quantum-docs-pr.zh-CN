---
title: 量程计算中的 qubit
description: 了解 qubits，这是量程计算中信息的基本单位。
author: QuantumWriter
uid: microsoft.quantum.concepts.qubit
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- $
- $
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: 0b768190137aa4effe0fbac9c764dff60ec00e16
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269569"
---
# <a name="the-qubit"></a>Qubit

就像在传统计算中信息的基础对象一样， [*qubits*](https://en.wikipedia.org/wiki/Qubit) （量程位）是量程计算中信息的基础对象。  为了理解这一函件，让我们看看一个简单的示例：单个 qubit。

## <a name="representing-a-qubit"></a>表示 Qubit

如果位或二进制数字的值可以 $ 是 $0 或 $1 $ ，则 qubit 的值可以是这些值或 superposition 的值，也可以是 $0 $ 和 $1 的量程 $ 。

单个 qubit 的状态可由单元规范的二维列向量描述，也就是说，其条目的大小平方值必须为 $1 $ 。 此向量（称为 "量程状态向量"）保存描述 qubit 的量程系统所需的所有信息，只是单个位包含描述二进制变量状态所需的所有信息。

使用标准 $1 的实或复数的任意二维列向量 $ 表示 qubit 持有的可能的量程状态。 因此 bmatrix } \\ \\ bmatrix } ，如果 $ qubit $ 和 $ \alpha $ 是满足 $ | \beta | ^ 2 + | \alpha | ^ 2 = 1 的复数，$ \begin{\alpha \beta \end{$ 表示 \beta 状态 $ 。 表示 qubits 的有效量程状态向量的一些示例包括

$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } ，\begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } ，\begin{ bmatrix } \frac{1 } {\sqrt{2 } } \\ \\ \frac{1 } {\sqrt{2 } } \end{ bmatrix } ，\begin{ bmatrix } \frac{1 } {\sqrt{2 } } \\ \\ \frac { -1 } {\sqrt{2 } } \end{ bmatrix } ，\text { and} \begin{ bmatrix } \frac{1 } {\sqrt{2 } } \\ \\ \frac{i } {\sqrt{2 } } \end{ bmatrix } . $ $

量程状态向量 $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $ 和 $ \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $ 采用特殊角色。 这两个向量构成了用于说明 qubit 状态的矢量空间的基础。 这意味着，可以将任何量程状态向量编写为这些基础向量的总和。 具体而言，矢量 $ \begin{ bmatrix } x \\ \\ y \end{ bmatrix } $ 可以编写为 $x \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } + y \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $。 尽管这些矢量的任何旋转都将作为 qubit 的完全有效基础，但我们选择使用*计算*来处理此类矢量。

我们将这两个量程状态与传统位（即 $0 和 $1）的两种状态相对应 $ $ 。 标准约定是选择

$ $0 \equiv \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } ，\qquad 1 \equiv \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } ，$ $

尽管相反的选择也可以更好地执行。 因此，在可能的单 qubit 量程状态向量外，只有两个对应于传统位的状态;所有其他量程状态都不是。

## <a name="measuring-a-qubit"></a>测量 Qubit

现在，我们知道了如何表示 qubit，我们可以通过讨论[*度量*](https://en.wikipedia.org/wiki/Measurement_in_quantum_mechanics)概念来获取这些状态所表示内容的一些直觉。 度量值对应于 "查找" qubit 的非正式构想，这会立即将量程状态折叠为两个经典状态 $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $ 或 $ \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $ 中的一个。 当计量状态向量 $ \begin{ bmatrix } \alpha \beta \end{$ 指定的 qubit 时 \\ \\ bmatrix } ，我们将获取结果 $0， $ 其中概率为 $ | \alpha | ^ 2 $ ，结果 $1 的 $ 概率为 $ | \beta | ^ 2 $ 。 在结果 $0 上 $ ，qubit 的新状态为 $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $; 在结果 $1 上， $ 其状态为 $ \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $。 请注意， $ 由于规范化条件 $ | \alpha | ^ 2 + | \beta | ^ 2 = 1，这些概率的总和最高为 $1 $ 。

度量值的属性也表示量程状态向量的整体符号是不相关的。 取消矢量等效于 $ \alpha \rightarrow-\alpha $ 和 $ \beta \rightarrow-\beta $ 。 由于测量 $0 $ 和 $1 的概率 $ 取决于术语的大小平方，因此插入此类符号不会改变概率。 此类阶段通常称为[ `` *全局阶段*""](https://en.wikipedia.org/wiki/Phase_factor) ，更常见的形式为 $e ^ {i \phi $， } 而不只是 $ \pm 1 $ 。

度量值的最后一个重要属性是它不一定损坏所有的量程状态向量。 如果我们以状态 $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $ （对应于古典状态 $0）开头的 qubit $ ，则测量此状态将始终产生结果 $0 $ 并使量程状态保持不变。 在这种情况下，如果我们只有传统位（即，qubits 是 $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $ 或 $ \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $），则测量不会损坏系统。 这意味着，我们可以复制传统数据并在量程计算机上对其进行操作，就像在传统计算机上操作一样。 不过，同时将信息同时存储在这两个状态中的能力，就是将量程计算作为可能的经典以及进一步剥夺的量程计算能力，从而无法以无顺序复制量程数据，另请参阅[无克隆定理](https://en.wikipedia.org/wiki/No-cloning_theorem)。

## <a name="visualizing-qubits-and-transformations-using-the-bloch-sphere"></a>使用 Bloch 球可视化 Qubits 和转换

Qubits 还可以使用[*Bloch 球*](https://en.wikipedia.org/wiki/Bloch_sphere)表示形式在 $ 3 $ D 中进行图片。  Bloch 球体提供一种方法，用于将 qubit 量程状态（这是一种二维复杂向量）描述为三维实值矢量。  这一点很重要，因为它使我们能够直观显示单 qubit 状态，从而提高了了解多 qubit 状态（不幸的 Bloch 球表示法中断）的。  可按如下所示可视化 Bloch 球：

<!--- ![](.\media\bloch.svg){ width=50% } --->
![Bloch 球体](~/media/concepts_bloch.png)

此图中的箭头显示了量程状态向量指向的方向，每次箭头转换都可以被视为一种基数轴的旋转。
尽管将一系列循环计算视为一系列强大的直觉，但使用此直觉来设计和描述算法非常困难。 问：通过提供一种用于描述此类旋转的语言来缓解此问题。

## <a name="single-qubit-operations"></a>单 Qubit 操作

量程计算机通过应用一组可以模拟量子状态向量旋转的通用量子入口来处理数据。
这种通用性的概念类似于传统（即传统）计算的通用性概念，如果输入位的每个转换都可以使用有限长度线路执行，则将门集视为通用。
在量程计算中，允许在 qubit 上执行的有效转换是单一转换和度量。
*Adjoint 操作*或复杂的共轭转置对量程计算至关重要，因为需要对量程转换进行反转。
Q # 通过提供自动将入口序列编译到 adjoint 的方法来反映这一点，这使程序员在许多情况下都必须 adjoints 代码。 下面显示了一个示例：

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Adj { // Auto-generate the adjoint of the operation
    H(qubit);
}
```

尽管这是一个简单的示例（如 <xref:microsoft.quantum.intrinsic.h[!OP.NO-LOC(> ），但它也是自我 adjoint 的，但您可以看到这种方式对于更复杂的 qubit 操作来说是非常重要的。
有关详细信息，请参阅[操作和函数](xref:microsoft.quantum.guide.operationsfunctions)。

传统计算机上只有四个可将一个位映射到一位的函数。 与此相反，在一个量程计算机上的单个 qubit 上存在无限数量的单一转换。 因此，一组有限的基元量程操作（称为[*入口*](https://en.wikipedia.org/wiki/Quantum_logic_gate)）可以精确地复制量子计算中允许的无限单一转换集。 这意味着，与传统计算不同，量程计算机可能会完全使用有限数量的入口来实现每个可能的量程计划。 因此，在传统计算机上，量程计算机不能是通用的。 因此，当我们说一组入口对量程计算是*通用*的时，我们实际上意味着比传统计算略有不同。
对于通用性，我们要求量程计算机仅在使用有限长度入口序列的有限错误内*估算*每个单一矩阵。
换句话说，如果任何单一转换都可以大致作为此集的入口产品写入，则可以使用一组入口。 对于任何规定的错误，我们都需要，入口集中存在 $G _ {1 } G_ {2 } ，\ldots，G_N $

$ $ G_N G_ {N-1 } \cdots G_2 G_1 \Approx U. $ $

请注意，由于矩阵乘法的约定是从右到左进行相乘，因此 $G _N $ ，实际上是最后一个应用于量程状态向量的操作。 更正式地说，如果每个容错 $ \epsilon>0 都存在 $G _1、\ldots G_N，则此类入口集是通用的， $ ，使 $ $G _N \ldots G_1 和 $U 之间的距离 $ $ 最多可为 $ \epsilon $ 。 理想情况下， $ 若要达到 \epsilon $ 所需的 $N 值， $ 应在 poly-对数和 $ 1/\ epsilon 之间进行缩放 $ 。

这种通用的入口集在实践中是什么样子？  Qubit 入口的最简单的此类通用门集仅包含两个入口： Hadamard 入口 $H $ 和所谓的 $T $ 入口（也称为 $ \ pi/8 $ 门）：

$ $ H = \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 & 1 \\ \\ 1 &-1 \end{ bmatrix } ，\qquad T = \begin{ bmatrix } 1 & 0 \\ \\ 0 & e ^ {i \ pi/4 } \end{ bmatrix } 。
$$

但是，对于与量程错误更正相关的实际原因，更方便的方法是考虑更大的门集，即可以使用 $H 和 $T 生成的门集 $ $ 。
我们可以将量程入口分为两类： Clifford 入口和 $T $ 门。
这种划分非常有用，因为在许多量程错误更正方案中，所谓的 Clifford 入口非常易于实现，这就是在操作和 qubits 实现故障 tolerantly 时，它们只需要很少的资源，而非 Clifford 的入口在需要容错时非常昂贵。 Qubit Clifford 入口的标准集，[默认情况下包含在 Q # 中](xref:microsoft.quantum.libraries.standard.prelude)，包括

$ $ H = \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 & 1 \\ \\ 1 &-1 \end{ bmatrix } ，\qquad S = \begin{ bmatrix } 1 & 0 \\ \\ 0 & i \end{ bmatrix } = T ^ 2，\qquad X = \begin{ bmatrix } 0 &1 \\ \\ 1 & 0 \end{ bmatrix } = HT ^ 4H，$ $

$ $ Y = \begin{ bmatrix } 0 &-i \\ \\ & 0 \END{ bmatrix } = T ^ 2HT ^ 4 HT ^ 6，\qquad Z = \begin{ bmatrix } 1&0 \\\\ 0 & -1 \end{ bmatrix } = T ^ 4。
$$

此处的操作 $X $ 、$Y $ 和 $Z $ 特别频繁使用，并在其 creator Wolfgang Pauli 后命名为[*Pauli 运算符*](https://en.wikipedia.org/wiki/Pauli_matrices)。
与非 Clifford 入口（$T）结合使用时 $ ，可以编写这些操作来估算单个 qubit 上的任何单一转换。

有关这些操作的详细信息，请参阅其 Bloch 球表示和 Q # 实现，请参阅[内部操作和函数](xref:microsoft.quantum.libraries.standard.prelude#intrinsic-operations-and-functions)。

作为从这些基元构建单一转换的示例，上面的 Bloch 球体中所示的三个转换对应于门序列 $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \mapsto HZH \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $。

虽然上一个构成了用于描述堆栈的逻辑级别上的操作的最常用的基元入口（将逻辑级别视为量程算法的级别），但在算法级别更少的基本操作（例如，操作更接近函数说明级别）通常是很方便的。 幸运的是，Q # 还提供了可用于实现更高级别的 unitaries 的方法，这进而允许实现高级算法，而无需将所有内容明确分解到 Clifford 和 $T $ 入口。

最简单的此类基元是单个 qubit 旋转。 通常会考虑三种单 qubit 旋转： $R _x $ 、$R _y $ 和 $R _z $ 。 例如，若要可视化旋转 $R _x （\theta） $ 的操作，请在 Bloch 球的 $x 轴方向上按下向右 $ 的拇指，并使用一角度 $ \ theta/2 弧度旋转矢量 $ 。 这是 $2 的令人困惑的因素，这是 $ 因为在 Bloch 球上绘制正交矢量时，正 \circ 的矢量是 $ 180 ^ $ ，但实际上是 $ 90 ^ \circ $ 度。 对应的单一矩阵包括：

\begin{align *} &R_z （\theta） = e ^ {-i\theta z/2 } = \begin{ bmatrix } e ^ {-i \ theta/2 } & 0 \\\\ 0 & e ^ {i \ theta/2 } \end{ bmatrix } ， \\ \\ &R_x （\theta） = e ^ {i\theta x/2 } = HR_z （\theta） H = \begin{ bmatrix } \cos （\ theta/2） &-i\sin （\ theta/2） \\ \\ -i\sin （\ theta/2） & \cos （\ theta/2） \end{ bmatrix } \\ \\ &R_y （\theta） = e ^ {-i\theta y/2 } = SHR_z （\theta） HS ^ \dagger = \begin{ bmatrix } \cos （\ theta/2） &-\sin （\ theta/2） \sin （\ theta/2） \\ \\ & \cos （\ theta/2） \end{ bmatrix } *}

正如可以将任何三个旋转组合在一起以在三个维度中执行任意旋转一样，可以从 Bloch 的球表示来看，可以将任何单一的矩阵作为三个旋转序列来编写。 具体而言，对于每个单一矩阵 $U $ 存在 $ \alpha、\beta、\gamma、\delta， $ $U = e ^ {i \alpha } R_x （\beta） R_z （\gamma） R_x （\delta） $。 因此 $R _z （\theta） $ 和 $H $ 也构成通用的入口集，尽管 $ \theta $ 可以采用任何值，但它不是离散集。 出于此原因，和由于量程模拟中的应用程序，此类连续入口对量程计算至关重要，尤其是在量程算法设计级别。 为了实现容错硬件实现，最终将其编译为与这些旋转紧密相关的离散入口序列。
