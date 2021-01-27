---
title: 标准库中的应用程序 Q#
description: 了解以下两个基本应用程序：量子计算-Hamiltonian 模拟和选定的搜索算法。
author: QuantumWriter
uid: microsoft.quantum.libraries.applications
ms.author: martinro
ms.date: 12/11/2017
ms.topic: conceptual
no-loc:
- Q#
- $$v
ms.openlocfilehash: 214d584840f235868c66a1fb3ee24d0acab49630
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857242"
---
# <a name="applications"></a>应用程序 #

## <a name="hamiltonian-simulation"></a>哈密顿模拟 ##

量程系统的模拟是最令人兴奋的量程计算应用程序之一。
在传统计算机上，模拟量程机制的难点通常是使用其状态向量表示形式的维度 $N $ 进行缩放。
由于此表示形式与 $n $ qubits $N = 2 ^ n $ 的数量呈指数级增长，因此，埋怨是一种称为 " [维数](xref:microsoft.quantum.concepts.multiple-qubits)" 的特征，而经典硬件上的量程模拟是棘手。

但是，这种情况在量程硬件上可能会有很大的差异。 量程模拟的最常见变化形式称为与时间无关的 Hamiltonian 模拟问题。 其中，提供了系统 Hamiltonian $H $ 的说明，它是一个 Hermitian 矩阵，另一个初始的量程状态 $ \ket{\psi (0) } $，在某些基础上是针对量程计算机上的 $n $ qubits 进行编码的。 由于关闭的系统中的量程状态在 Schrödinger 公式 $ $ \begin{align} i\frac {d \ket{\psi (t) }} {d t} & = H \ket{\psi (t) } 下演化，\end{align} $ $ 这一目标是实现单一的时间演化运算符，$U (t) = e ^ {-iHt} $，在某个固定时间 $t $，其中 $ \ket{\psi (t) } = U (t) \ket{\psi (0) } $ 求解了 Schrödinger 公式。
类似，依赖于时间的 Hamiltonian 模拟问题解决了同一公式，但 $H (t) $ 现在为时间函数。

Hamiltonian 模拟是许多其他量程模拟问题的主要组成部分，而 Hamiltonian 模拟问题的解决方案是一种算法，用于描述综合逼近单一 $ \tilde{U} $ 的一系列基元量子入口， (并 \\ \\ 在 [\tilde{U} 的标准](xref:microsoft.quantum.concepts.matrix-advanced)中) | \le \epsilon $。 这些算法的复杂性非常严格地取决于量程计算机如何访问相关 Hamiltonian 的说明。 例如，在最坏情况下，如果要将 $H $ $n $ qubits 上的 $ 提供为 $ 2 ^ n \times 2 ^ n $ 数字的列表，每个矩阵元素对应一个矩阵元素，只需读取数据就会需要指数时间。 在最佳情况下，可能会假设有权访问 $O \ket{t}\ket{\psi (0) } = \ket{t}U (t) \ket{\psi (0) } $ 完全的黑色框。 这两个输入模型都不是特别感兴趣的，即前者不能比传统方法更好，而后者则隐藏其实现的基元门复杂度，这在 qubits 数中可能是指数的。

### <a name="descriptions-of-hamiltonians"></a>Hamiltonians 的说明 ###

因此需要输入格式的其他假设。 精细平衡在输入模型之间必须是有意义的，这两个输入模型都具有很好的描述性，以包含感兴趣的 Hamiltonians （例如，那些实际的物理系统或相关的计算问题）以及足以在量程计算机上有效实施的输入模型。 在该宣传资料中可以找到各种非常重要的输入模型，范围从量子到古典。 

作为量程输入模型的示例， [基于样本的 Hamiltonian 模拟](http://www.nature.com/articles/s41534-017-0013-7) 假定对生成密度矩阵 $ \rho $ （被视为 Hamiltonian $H $）副本的量程操作具有黑白访问。 在 [单一访问模型](https://arxiv.org/abs/1202.5822) 中，将 Hamiltonian 分解为 unitaries $ $ \begin{align} H & = \sum ^ {d-1} \_ {j = 0} a \_ j \hat{U} \_ j，\end{align} $ $，其中 $a \_ j>$0 是系数，$ \hat{U} \_ j $ 为 unitaries。 然后假设有一个对单一 oracle $V = \sum ^ {d} \_ {j = 0} \Ket{j}\bra{j}\otimes \hat{U} j $ 的访问权限，它可选择所 \_ 需的 $ \hat{U} \_ j $，和 oracle $A \ket {0} = \sum ^ {d-1} \_ {j = 0} \sqrt{a \_ j/\ sum ^ {d-1} \_ {k = 0} \alpha \_ j} \ket{j} $，这将创建量程状态编码这些系数。 对于 [稀疏 Hamiltonian 模拟](https://arxiv.org/abs/quant-ph/0301023)，一种假设 Hamiltonian 是一个稀疏矩阵，其中每一行都只有 $d = \mathcal{O} ( \Text{polylog} (N) # B3 $ 非零元素。 此外，还假定存在有效的量程线路，它们输出了这些非零元素的位置以及它们的值。 [Hamiltonian 模拟算法](xref:microsoft.quantum.more-information)的复杂性是根据对这些黑色框进行查询的数量来计算的，因此，基元入口的复杂性很大程度上取决于实现这些黑框的难度。

> [!NOTE]
> 大 O 表示法通常用于描述算法的复杂性缩放。 假设有两个真正的函数 $f，g $，表达式 $g (x) = \mathcal{O} (f (x) # B6 $ 表示存在一个绝对正值 $x \_ 0，c>$0，$g x ()  ($) $x $ x \_ $0 $。 

在量程计算机上要实现的大多数实际应用程序中，这些黑框必须有效地实施，这是使用 $ \mathcal{O} ( \text{polylog} (N) # B3 $ 基元量子入口。 更强、更有效的 simulable Hamiltonians 必须具有足够的稀疏传统说明。 在这种情况下，假定将 Hamiltonian 分解为 Hermitian part $ $ \begin{align} H 的总和 part $ $ H & = \sum ^ {d-1} _ {j = 0} H_j。
\end{align} $ $ 而且，假设每个部件（Hamiltonian $H \_ j $）都易于模拟。 这意味着 \_ 任何时候 $t $ 的任何时间都可能会完全使用 $ \mathcal{O} (1) $ 基元量程入口实现单一 $e ^ {-iH j t} $。 例如，这在特殊情况下为 true，其中每个 $H \_ j $ 均为本地 Pauli 运算符，这意味着它们属于 $ \mathcal{O} (1) $ 此模型特别适用于具有受限和本地交互的物理系统，因为术语数为 $d = \mathcal{O} ( \text{polylog} (N) # B3 $，并且可能会在多项式时间内清楚地写出经典。

> [!TIP]
> 可以使用 Dynamical 生成器表示库来描述分解到部分的 Hamiltonians。 有关详细信息，请参阅 [数据结构](xref:microsoft.quantum.libraries.data-structures)中的 Dynamical 生成器表示形式部分。

### <a name="simulation-algorithms"></a>模拟算法 ###

量程模拟算法将 Hamiltonian 的给定描述转换为一系列基元量子入口，作为一个整体，这是一项 Hamiltonian 的大致时间演变。

在 Hamiltonian 分解为 Hermitian 部分求和的特殊情况下，Trotter-Suzuki 分解是一个特别简单且直观的算法，用于模拟分解为 Hermitian 组件的总和的 Hamiltonians。 例如，此系列的第一个顺序的集成器约为 $ $ \begin{align} U (t) & = \left ( e ^ {-iH \_ 0 t/r} e ^ {-iH \_ 1 t/r} \cdots e ^ {-iH \_ {d-1} t/r} \right) ^ {r} + \mathcal{O} (d ^ 2 \ max_j \\ |H \_ j \\ | ^ 2 t ^ 2/r) ，\end{align} $ $ 使用 $r d $ 条款的产品。 

> [!TIP]
> 示例中介绍了 Trotter-Suzuki 模拟算法的应用程序。
> 对于 Ising 模型，只使用每个目标计算机提供的内部操作，请参阅 [ **SimpleIsing** 示例](https://github.com/microsoft/Quantum/blob/main/samples/simulation/ising/simple)。
> 有关使用 Trotter-Suzuki 库控件结构的 Ising 模型，请参阅 [ **IsingTrotter** 示例](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/trotter-evolution)。
> 对于使用 Trotter-Suzuki 库控件结构的分子 Hydrogen，请参阅 [ **H2 模拟** 示例](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/command-line)。

在许多情况下，我们想要实现模拟算法，但并不关心其实现的详细信息。 例如，第二顺序集成器接近 $ $ \begin{align} U (t) & = \left ( e ^ {-iH \_ 0 t/2r} e ^ {-iH \_ 1 t/2r} \cdots e ^ {-iH \_ {d-1} t/2r} e ^ {-iH \_ {d-1} t/2r} \cdots e ^ {-iH \_ 1 t/2r} e ^ {-iH \_ 0 t/2r} \right) ^ {r} + \mathcal{O} (d ^ 3 \ max_j \\ |H \_ j \\ | ^ 3 t ^ 3/r ^ 2) ，\end{align} $ $ 使用产品 $ 2rd $ 条款。 更大的订单会涉及更多的术语，而优化后的变量可能需要对指数的高度非常重要的排序。 其他高级算法还可能涉及在中间步骤中使用 ancilla qubits。 因此，我们将 canon 中的模拟算法打包为用户定义的类型

```qsharp
newtype SimulationAlgorithm = ((Double, EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl);
```

第一个参数 `Double` 是模拟时间，第二个参数 `EvolutionGenerator` （在 [数据结构](xref:microsoft.quantum.libraries.data-structures)的 "Dynamical 生成器表示形式" 部分中介绍）是与时间无关的 Hamiltonian 的传统说明，其中说明了如何使用 Hamiltonian 中的每个术语来模拟量程线路。 此形式的类型近似于第三个参数上的单一操作 $e ^ {iHt} $，该参数 `Qubit[]` 是存储模拟系统的量程状态的寄存器。 与时间相关的情况类似，我们使用类型来定义用户定义的类型 `EvolutionSchedule` ，该类型是依赖于时间的 Hamiltonian 的传统说明。

```qsharp
newtype TimeDependentSimulationAlgorithm = ((Double, EvolutionSchedule, Qubit[]) => Unit : Adjoint, Controlled);
```

例如，可以使用以下 canon 函数来调用 Trotter-Suzuki 分解，其中的参数 `trotterStepSize` 修改每个指数的模拟持续时间以及所需的集成器的 `trotterOrder` 顺序。

```qsharp
function TrotterSimulationAlgorithm(
    trotterStepSize : Double, 
    trotterOrder : Int) 
: SimulationAlgorithm {
    ...
}

function TimeDependentTrotterSimulationAlgorithm(
    trotterStepSize : Double, 
    trotterOrder : Int) 
: TimeDependentSimulationAlgorithm {
    ...
}
```

> [!TIP]
> 示例中介绍了模拟库的应用程序。 有关使用的 Ising 模型中的阶段估计 `SimulationAlgorithm` ，请参阅 [ **IsingPhaseEstimation** 示例](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/phase-estimation)。
> 若要使用在 Ising 模型中准备 adiabatic 状态 `TimeDependentSimulationAlgorithm` ，请参阅 [ **AdiabaticIsing** 示例](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/adiabatic)。


### <a name="adiabatic-state-preparation--phase-estimation"></a>Adiabatic 状态准备 & 阶段估计 ###

Hamiltonian 模拟的一个常见应用是 adiabatic 状态准备。 此处提供了两个 Hamiltonians $H \_ {\text{start}} $ 和 $H \_ {\text{end}} $）和一个量程状态 $ \ket{\psi (0) } $，该状态是 start Hamiltonian $H \_ {\text{start}} $ 的地面状态。 通常，会 \_ 选择 $H {\text{start}} $，以便可以从计算基础状态 $ \ket{0\cdots 0} $ 轻松地准备 $ \ket{\psi (0) } $。 通过在依赖于时间的模拟问题中将这些 Hamiltonians 内插到非常缓慢的情况下，最终 Hamiltonian $H {\text{end}} $ 的基本状态下，可能会有很高的概率 \_ 。 尽管准备良好的 Hamiltonian 基本状态可以通过以时间依赖于时间的 Hamiltonian 模拟算法（作为子例程）调用来继续进行，但也可以使用其他概念上不同的方法（例如 variational 量子 eigensolver）。

然而，在量子化学中普遍的另一个应用程序正在估算 Hamiltonians 的地面状态能量，表示化学反应的中间步骤。 例如，这种方案可以依赖 adiabatic 状态准备来创建地面状态，然后将与时间无关的 Hamiltonian 模拟合并为阶段估算特征中的子例程，以利用一些有限的错误和成功的概率来提取此能源。 

将模拟算法抽象为用户定义的类型 `SimulationAlgorithm` ，并 `TimeDependentSimulationAlgorithm` 使我们能够方便地将其功能合并到更复杂的量程算法中。 这激发我们为这些常用的子例程执行相同操作。

因此，我们定义了便捷函数

```qsharp
function InterpolatedEvolution(
        interpolationTime : Double, 
        evolutionGeneratorStart : EvolutionGenerator,
        evolutionGeneratorEnd : EvolutionGenerator,
        timeDependentSimulationAlgorithm : TimeDependentSimulationAlgorithm)
: (Qubit[] => Unit is Adj + Ctl) {
        ...
}
 
```

这会返回单一操作，该操作将实现 adiabatic 状态准备的所有步骤。 第一个参数 `interpolatedTime` 定义了一段时间，在该时间内我们将在第二个参数描述的开始 Hamiltonian `evolutionGeneratorStart` 与第三个参数描述的结束 Hamiltonian 之间进行线性插入 `evolutionGeneratorEnd` 。 第四个参数 `timeDependentSimulationAlgorithm` 是选择模拟算法的位置。 请注意 `interpolatedTime` ，如果足够长，则在整个时间依赖模拟的整个持续时间内，最初的状态将保持 Hamiltonian 的瞬时地面状态，从而结束于结束 Hamiltonian 的基本状态。

我们还定义了一个帮助操作，该操作会自动执行典型的量程化学试验的所有步骤。 例如，我们提供了以下内容，它将返回 adiabatic 状态准备所产生状态的能源估算：

```qsharp
operation EstimateAdiabaticStateEnergy(
    nQubits : Int,
    statePrepUnitary : (Qubit[] => Unit),
    adiabaticUnitary : (Qubit[] => Unit),
    qpeUnitary: (Qubit[] => Unit is Adj + Ctl),
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double))
: Double {
...
}
```

`nQubits` 用于对初始量程状态进行编码的 qubits 的数目。 `statePrepUnitary` 从计算基础 $ \ket{0\cdots 0} $ 准备开始状态。 `adiabaticUnitary` 是实现 adiabatic 状态准备的单一操作，如函数生成的  `InterpolatedEvolution` 。 `qpeUnitary` 用于对生成的量程状态执行阶段估计的单一操作。 `phaseEstAlgorithm` 是我们选择的阶段估算算法。

> [!TIP]
> 示例中介绍了 adiabatic 状态准备的应用程序。 对于 Ising 模型，使用手动实现 adiabatic 状态准备，而不是使用 `AdiabaticEvolution` 函数，请参阅 [ **AdiabaticIsing** 示例](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/adiabatic)。
> 有关 Ising 模型中的阶段估算和 adiabatic 状态准备，请参阅 [ **IsingPhaseEstimation** 示例](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/phase-estimation)。

> [!TIP]
> [分子 Hydrogen 的模拟](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/command-line)是一个有趣且简单的示例。 [O'Malley et](https://arxiv.org/abs/1512.06860)中报告的模型和实验性结果。 只需要 Pauli 矩阵，并采用 $ \hat H = g \_ {0} I \_ 0 i \_ 1 + g \_ 1 {z \_ 0} + g \_ 2 {Z 1 \_ } + g \_ 3 {z \_ 0} {z 1} + g \_ \_ 4 {x 0} { \_ \_ \_ \_ x 1} \_ $。 这是一个有效的 Hamiltonian，只需要2个 qubits，在这种情况下，将根据两个 Hydrogen 原子之间的距离 $R $ 计算 $g $ 的常量。 使用 canon 函数，Paulis 转换为 unitaries，然后使用 Trotter-Suzuki 分解在短时间段内演变。 可以在不使用 adiabatic 状态准备的情况下创建 $H _2 $ 地面状态的良好近似值，因此，可以通过利用 canon 中的阶段估算直接找到地面状态。

## <a name="shors-algorithm"></a>秀尔算法 ##
选定的算法仍是量程计算中最重要的开发，因为它显示了量程计算机可以用于解决重要的当前经典棘手问题。
选定的算法提供了一种使用量程计算机（称为 " *分解*" 的问题）对较大数字进行因式分解的快速方法。
许多 cryptosystems 的安全是基于不存在任何快速算法以进行分解的假设。
因此，选定的算法对我们在一个量程后世界中的安全性的看法产生了深远的影响。

选定的算法可以看作是一种混合算法。
量程计算机用于执行称为 "期间查找" 的计算硬任务。
然后，将经典的结果处理为估算系数。
下面是两个步骤。

### <a name="period-finding"></a>期间查找 ###

了解到量程傅立叶转换和阶段估算工作原理 (参阅 [量程算法](xref:microsoft.quantum.libraries.standard.algorithms)) ，我们可以使用这些工具解决称为 *时间段查找* 的经典硬计算问题。  在下一部分中，我们将了解如何应用时间段查找以进行分解。

给定两个整数 $a $ 和 $N $，其中 $a<N $，句点的目标（也称为顺序查找）是查找 $r $ $a $ $N $ 的 _顺序_ $r $ $a $，其中 $ 被定义为最少的正整数，^ r \equiv 1 \text{Mod} N $。  

若要查找使用量程计算机的顺序，可以使用应用于以下单一运算符的阶段估算算法，$U _a $： $ $ U_a \ket{x} \equiv \ket{ (ax) \text{mod} N}。 $ $ $U _a $ 的本征向量为 integer $s $ 和 $ 0 \ leq s \leq r-$1，$ $ \ket{x_s} \equiv 1/\sqrt{r} \sum \_ {k = 0} ^ {r}} \frac{-2\pi ^ \ket{a {mod} N}，$ $ 是 $U _a $ 的 _k\text_ 。
$U _a $ 的本征值是 $ $ U \_ a \ket{x \_ s} = e ^ {2 \ pi i s/r} \ket{x \_ s}。 $$

这样，阶段估计就会输出本征值 $e ^ {2 \ pi i s/r} $，其中 $r $ 可以通过 $s/r $ 中的 [连续分数](https://en.wikipedia.org/wiki/Continued_fraction) 有效地进行学习。

量程期间查找的线路关系图为：

![量程期间查找的线路关系图](~/media/QPE.svg)

此时，$ 2n $ qubits 将初始化为 $ \ket {0} $，并将 $n $ qubits 初始化为 $ \ket {1} $。
读者可能会想知道，将 eigenstates 的量程寄存器初始化为 $ \ket $ 的原因 {1} 。
如果事先不知道订单 $r $，我们实际上无法直接准备 $ \ket{x_s} $ 状态。
幸好，事实证明，$ 1/\ sqrt {r} \sum \_ {s = 0} ^ {r-1} \ket{x \_ s} = \ket {1} $。
我们不需要实际准备 $ \ket{x} $！
只需在状态 $ \ket $ 中准备 $n $ qubits 的量程寄存器 {1} 。 

线路包含 QFT 和多个受控入口。
[之前](xref:microsoft.quantum.libraries.standard.algorithms)已描述 QFT 入口。
如果控件 qubit 是 $ \ket $，则受控 $U _a $ 入口映射 $ \ket{x} $ 到 $ \ket{ (ax) \text{mod} N} $ {1} ，否则将 $ \ket{x} $ 映射到 $ \ket{x} $。

若要实现 $ (^ nx) \text{mod} N $，只需应用受控-$U _ {a ^ N} $，在此计算 $a ^ N \text{mod} N $ 经典，以插入量程线路。  
[量程算法文档](./algorithms.md#arithmetic)中介绍了实现这种模块化算法的线路，具体而言，我们需要使用模块求幂线路来实现受控-$U \_ {a ^ i} $ 操作。

尽管上面的线路对应于 [量程阶段估算](xref:Microsoft.Quantum.Characterization.QuantumPhaseEstimation) ，并显式启用了订单查找，但我们可以减少所需的 qubits 数量。 我们可以按照 [arXiv： quant/0205095V3 第8页](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)中所述的顺序查找 Beauregard 的方法，或使用中提供的一个阶段估算例程。 例如， [强健的阶段估算](xref:Microsoft.Quantum.Characterization.RobustPhaseEstimation) 还使用一个额外的 qubit。

### <a name="factoring"></a>分解 ###
因式分解的目标是确定整数 $N $ 的两个质数因素，其中 $N $ 是 $n $ 位数字。  
因式分解包含如下所述的步骤。 步骤分为三个部分： "传统预处理" 例程 (1-4) ;用于查找 $a \text{mod} N $ (5) 的顺序的量程计算例程;和一个传统的后处理例程，用于从订单 (6-9) 中派生出质数。

传统预处理例程包含以下步骤：
1. 如果 $N $ 为偶数，则返回质数系数 $2 $。
2. 如果 $p \geq1 $ $N = p ^ q $，$q \geq2 $，则返回 $p $ 的质数。  此步骤在经典执行。
3. 选择一个随机数字 $a $，$1 < < N-$1。
4. 如果 $ \text{gcd} (a，N) # B0 $1，则返回质数系数 $ \text{gcd} (a，N) $。 此步骤使用 Euclid 的算法进行计算。
如果未返回任何主要因素，我们将继续执行量程例程：
5. 调用量子 period 查找算法来计算 $a \text{mod} N $ $r $ 的顺序。 使用传统的后处理例程中的 $r $ 来确定主要因素：
6. 如果 $r $ 是奇数，请返回到 "预处理步骤 (3) "。
7. 如果 $r $ 甚至 $a ^ {r/2} =-1 \ text {mod} N $，请返回到预处理步骤 (3) 。
8. 如果 $ \text{gcd} (^ {r/2} + 1，N) $ 是 $N $ 的一个非常简单的因素，则返回 $ \text{gcd} (^ {r/2} + 1，N) $。
9. 如果 $ \text{gcd} (^ {r/2}-1，N) $ 是 $N $ 的一个非常简单的因素，则返回 $ \text{gcd} (^ {r/2}-1，N) $。


分解算法是概率的：它可以表明，概率至少为1的一半 $r $ 将为偶数，$a ^ {r/2} \neq-1 \text{mod} N $，因此产生了一个主要因素。   (参阅 [选定的原始纸张](https://doi.org/10.1109/SFCS.1994.365700)以获取详细 [信息](xref:microsoft.quantum.more-information)，请参阅中的 *基础量程计算* 文本之一) 。
如果未返回一个质数因素，则只需重复步骤 (1) 中的算法。  $N $ 次尝试后，每次尝试失败的概率最多为 $ 2 ^ {-n} $。
因此，在重复该算法后，几乎可确保成功的次数较少。
