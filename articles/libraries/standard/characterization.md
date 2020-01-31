---
title: 'Q # 标准库-特性 |Microsoft Docs'
description: 'Q # 标准库-特性'
author: QuantumWriter
uid: microsoft.quantum.libraries.characterization
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 51124dc78feedf6d5c85fe224898e66a1c5ed459
ms.sourcegitcommit: ca5015fed409eaf0395a89c2e4bc6a890c360aa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76870342"
---
# <a name="quantum-characterization-and-statistics"></a>量程特性和统计信息 #

为了开发有用的量程算法，能够为操作的效果建立特征非常重要。
这是一项挑战，因为量程系统的每个度量值最多可产生一位信息。
若要了解 eigenvalue，只需将一个量程状态通知给多个度量值，就必须将多个度量值的结果拼接在一起，以便用户能够搜集表示这些概念所需的许多信息。
量程状态特别棘手，因为[无克隆定理](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem)规定，无法从状态的单一副本了解任意量程状态，因为这样做可以让你创建状态的副本。
这种情况下，用户的量程状态模糊会反映出来，因为 Q # 不会公开，甚至不会定义量程程序*的状态。*
因此，通过将操作和状态视为黑箱来实现量程的特征;这种方法与量程特征、验证和验证（QCVV）的实验操作非常常见。

特性与前面讨论的其他许多库不同。
此处的目标是更少了解有关系统的传统信息，而不是对状态向量执行单一转换。
因此，这些库必须同时进行传统和量程信息处理。


## <a name="iterative-phase-estimation"></a>迭代阶段估算 ##

根据量程特征来查看量程编程，这一建议可替代量程阶段估算。
也就是说，我们可以查看阶段估算，而不是准备 $n $-qubit register *，使其*包含阶段的二进制表示形式（如在量程阶段估算中）。
在量程情况下，我们将使用相位 kickback 将黑色方框操作的应用程序转变为一个未知角度来旋转，但会测量 ancilla qubit，这是我们在每一步之后的每个步骤。
这样做的优点是，我们只需要一个额外的 qubit 来执行量程情况下所述的阶段 kickback，因为我们然后以迭代方式从每个步骤的测量结果中学习阶段。  
以下建议的每个方法都使用不同的策略来设计试验，并使用不同的数据处理方法来了解这一阶段。  它们各自具有独特的优势，包括严格的错误界限、合并先前信息的能力、容忍错误或在内存 limitted 传统计算机上运行。

在讨论迭代阶段估计时，我们会将一个单一 $U $ 指定为一个黑色的操作。
如 "[数据结构](xref:microsoft.quantum.libraries.data-structures)中的 oracles" 一节中所述，Q # canon 按 <xref:microsoft.quantum.oracles.discreteoracle> 用户定义类型对 `((Int, Qubit[]) => Unit : Adjoint, Controlled)`的元组类型定义的操作进行建模。
具体而言，如果 `U : DiscreteOracle`，则 `U(m)` 实现 `m : Int`$U ^ m $。

使用此定义时，每个迭代阶段估计步骤会在 $ \ket{+} $ 状态中准备一个辅助 qubit，并将其假定为 $U [eigenvector](xref:microsoft.quantum.concepts.matrix-advanced) （m） $，即 $U （m） \ket{\phi} = e ^ {im\phi} \ 票证 {\ phi} $。  
然后，将使用 `U(m)` 的受控应用程序来准备状态 $ \left （R\_1 （m \phi） \ket{+} \right） \ket{\phi} $。
正如在量程情况下，受影响的 oracle `U(m)` 的受控应用程序的影响与在 $ \ket{+} $ 上将 $R _1 $ 应用于未知阶段的效果完全相同，因此我们可以更简单的方式描述 $U $ 的影响。
然后，该算法通过应用 $R _1 （-m\theta） $ 以获取状态 $ \ket{\psi} = \left （R\_1 （m [\phi-\theta]） \ket{+} \right） \ket{\phi} $ $ 来旋转控件 qubit。
然后，将辅助 qubit 用作 `U(m)` 的控件，并按 $X $ basis 度量，以获取单个传统 `Result`。

此时，从通过迭代阶段估算获取的 `Result` 值重建阶段是一种传统的统计推理问题。
如果查找 $m $ 这一值可最大化获取的信息，则在给定固定推理方法的情况下，只是统计信息中的一个问题。
我们将在 Bayesian 参数估算形式中简要介绍理论级别的迭代阶段估算，然后再继续介绍 Q # canon 中提供的用于解决这一传统推理问题的统计算法。

### <a name="iterative-phase-estimation-without-eigenstates"></a>不 Eigenstates 的迭代阶段估算 ###

如果提供的是不是 eigenstate 的输入状态，这意味着如果 $U （m） \ket{\phi\_j} = e ^ {im\phi\_j} $，则阶段估算的进程将不确定地将量程状态引导到单个能源 eigenstate。  它最终聚合为的 eigenstate 是最有可能产生观察 `Result`的 eigenstate。

具体而言，PE 的单个步骤会在状态 \begin{align} \ sum_j \sqrt{\Pr （\phi\_j）} \ket{\phi\_j} \mapsto \sum\_j\frac {\ sqrt {\ Pr 上执行以下非单一转换（\phi\_j）} \sqrt{\Pr （\text{Result} | \phi\_j）} \ket{\phi\_j}} {\sqrt{\Pr （\phi\_j） \sum\_j \Pr （\text{Result} | \phi\_j）}}。
\end{align}，因为此过程是通过多个 `Result` 值进行迭代的，所以不具有最大值 $ \ prod_k \Pr （\text{Result}\_k | \phi\_j） $ 的 eigenstates 将被指数地抑制。
这样一来，如果正确选择了试验，推理过程将成为一种 eigenvalue 的状态。

Bayes ' 定理进一步建议以 \begin{align} \frac{\sqrt{\Pr （\phi\_j）} \sqrt{\Pr （\text{Result} | \phi\_j）} \ket{\phi （\Sqrt{\Pr | \phi j）} \sum\_j}} {\Pr （\text{Result}\_j） \phi\_j \Sqrt{\Pr （\Phi | \text{Result}\_
此处的 \end{align} $ \Pr （\phi\_j | \text{Result}） $ 可以解释为每个假设应 ascribe 给每个假设的概率：

1. 计量之前的量程状态的知识，
2. 了解 $U $ 和的 eigenstates
3. $U $ 的本征值的知识。

了解这三个问题在传统计算机上通常是呈指数级的。
从一开始就可以执行这样一种量程学习任务，而无需知道阶段估算的实用程序。
此原因的阶段估算出现在提供指数加速的多个量程算法中。

### <a name="bayesian-phase-estimation"></a>Bayesian 阶段估算 ###

> [!TIP]
> 有关 Bayesian 阶段估算的详细信息，请参阅[**PhaseEstimation**](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation)示例。

Bayesian 阶段估算的理念非常简单。
从阶段估算协议收集度量值统计信息，然后使用 Bayesian 推理来处理结果，并提供参数的估计值。
此处理可让你估计 eigenvalue 以及该估计值的不确定性。
它还允许您执行自适应试验并利用以前的信息。
方法的主要缺点是它需要进行计算。

若要了解此 Bayesian 推理过程的工作原理，请考虑处理单个 `Zero` 结果的情况。
请注意，$X = \ket{+} \bra{+}-\ket{-}\bra{-}$，这样，$ \ket{+} $ 就是对应于 `Zero`的 $X $ 的唯一肯定 eigenstate。
在给定输入状态 $ \ket{\psi}\ket{\phi} $ 的情况 qubit，在第一个上 `Zero` 观察[`PauliX` 度量值](xref:microsoft.quantum.concepts.pauli)的概率，因此 \begin{equation} \Pr （\texttt{Zero} | \psi） = \left |\braket{+ | \psi} \right | ^ 2。
\end{equation} 在迭代阶段估算的情况下，我们已将 $ \ket{\psi} = R_1 （m [\phi-\theta]） \ket{+} $，以便 \begin{align} \Pr （\texttt{Zero} | \phi; m，\theta） & = \left |\braket{+ |R_1 （m [\phi-\theta]） |+} \right | ^ 2 \\\\ & = \left |\frac12 \left （\bra{0} + \bra{1} \right） \left （\ket{0} + e ^ {i m [\phi-\theta]} \ket{1} \right） \right | ^ 2 \\\\ & = \left |\frac{1 + e ^ {i m [\phi-\theta]}}{2} \right | ^ 2 \\\\ & = \cos ^ 2 （m [\phi-\theta]/2） \tag{★} \label{eq：。
\end{align} 是迭代阶段估算，其中包含正弦函数的振荡频率，因为能够使用该 sinusoid 给定的偏移量来翻转硬币。
按照传统的传统术语，我们调用了 $ \eqref{eq：时间-est-est} $*概率函数*以进行迭代阶段估算。

在观察到迭代阶段估算可能性函数的 `Result` 后，就可以使用 Bayes 的规则来规定应该将该阶段确定为遵循该观察阶段。
具体而言，\begin{equation} \Pr （\phi | d） = \frac{\Pr （d | \phi） \Pr （\phi）} {\int \Pr （d | \phi） \Pr （\phi） {\mathrm d} \phi} \Pr （\phi），\end{equation}，其中 $d \in \\{\texttt{Zero}，\texttt{One}\\} $ 是 `Result`，其中 $ \Pr （\phi） $ 描述了之前的信仰 $ \phi $。
然后，这会使迭代阶段的迭代本质明确明了，因为后验分布 $ \Pr （\phi | d） $ 介绍了我们的信仰，紧靠下一个 `Result`。

在此过程中，我们可以在此过程中的任何时间点将古典控制器推导为 \begin{equation} \hat{\phi} \mathrel{： =} \expect [\phi | \text{data}] = \int \phi \Pr （\phi | \text{data}） {\mathrm d} \phi，\end{equation}，其中 $ \text{data} $ 代表获得的所有 `Result` 值的整个记录。

确切的 Bayesian 推理在实践棘手中。
为此，我们想要了解 $x $ $n $ 位变量。
之前的分发 $ \Pr （x） $ 支持 $x $ 的 $ 2 ^ n $ 假设值。
这意味着，如果需要对 $x $ 进行非常准确的估计，Bayesian 阶段估计可能需要内存和处理时间不高。
对于某些应用程序，如量程模拟，所需的 limitted 准确性不会排除这样的方法。其他应用程序（如选定的算法）在其阶段估算步骤内不能使用精确的 Bayesian 推理。  出于此原因，我们还提供了近似 Bayesian 方法（如[随机审核阶段估算（RWPE））](xref:microsoft.quantum.research.randomwalkphaseestimation.randomwalkphaseestimation)和非 Bayesian 方法（如可靠的[阶段估算](xref:microsoft.quantum.characterization.robustphaseestimation)）的实现。

### <a name="robust-phase-estimation"></a>可靠阶段估算 ###

最大情况下，最大值为 " *posteriori* Bayesian" 的最大阶段，即从测量结果中重建阶段估算。 因此，大多数可行的阶段估算算法在重建中会牺牲一定的质量，而在 exchange 中，这种情况下，会将 polynomially 与进行的度量值进行缩放。

一个这样的示例（一个有效的传统后处理步骤）是[可靠的阶段估算算法](https://arxiv.org/abs/1502.02677)，其签名和输入如下所述。 它假定输入单一的黑框 $U $ 封装为 `DiscreteOracle` 类型，因此仅查询受控 $U $ 的整数幂。 如果 `Qubit[]` register 中的输入状态为 eigenstate $U \ket{\psi} = e ^ {i\phi} \ 票证 {\ psi} $，则可靠阶段估算算法会将 $ \hat{\phi}\in $ 的估算值返回为 `Double`。

与大多数其他有用的变体共享的可靠阶段估算的最重要功能是，$ \hat{\phi} $ 的重建质量在某种意义上是海森堡的。 这意味着，如果从 true 值到 $ \sigma $，$ \hat{\phi} $ 的偏差为 $ \sigma $，则 $ $ 将按对受控-$U $ （即 $ \sigma = \mathcal{O} （1/Q） $ 进行的 $Q 查询总数成反比。 现在，偏差定义在不同的估计算法之间有所不同。 在某些情况下，这可能意味着至少有 $ \mathcal{O} （1） $ 概率，估计错误 $ | \hat{\phi}-\phi |\_\circ\le \sigma $ on a 循环度量 $ \circ $。 对于可靠的阶段估算，偏差精确到 $ \sigma ^ 2 = \mathbb{E}\_\hat{\phi} [（\mod\_{2 \ pi} （\hat{\phi}-\phi + \pi）-\pi） ^ 2] $ 如果将定期阶段解为单个有限间隔 $ （-\pi，\pi] $。 更准确地说，可靠阶段估算中的标准偏差满足不相等 $ $ \begin{align} 2.0 \pi/Q \le \sigma \le 2 \ pi/2 ^ {n} \le 10.7 \ pi/Q，\end{align} $ $，其中的下限达到了 asymptotically 大 $Q $ 的限制，并且即使是小型样本大小也可保证上限。  请注意，$n 由 `bitsPrecision` 输入选择的 $，它隐式定义 $Q $。

其他相关的详细信息包括：仅 $1 $ ancilla qubit 的小空间开销，或该过程是非自适应，这意味着所需的量程试验顺序与中间测量结果无关。 在此示例中，如果选择阶段估算算法非常重要，其中一项应引用文档（如 @"microsoft.quantum.characterization.robustphaseestimation"）和引用的发布，以获取详细信息及其实现。

> [!TIP]
> 在许多示例中，使用了可靠的阶段估算。 有关提取各个物理系统的地面状态能量的阶段估算，请参阅[ **H2 模拟**示例](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line)、 [ **SimpleIsing**示例](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/simple)和[ **Hubbard 模型**示例](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard)。


### <a name="continuous-oracles"></a>连续 Oracles ###

我们还可以从上述 oracle 模型通用化，以允许按 canon 类型 <xref:microsoft.quantum.oracles.continuousoracle>建模的持续时间 oracles。
请考虑不要使用单个单一运算符 $U $，而是 $t \in \mathbb{R} $ 中有一个单一运算符系列 $U （t） $，这样 $U （t） U （s） $ = $U （t + s） $。
这是一个比离散大小写更弱的语句，因为我们可以通过将 $t = m\,\delta t $ 限制为某个固定的 $ \delta t $ 来构造 <xref:microsoft.quantum.oracles.discreteoracle>。
按[石头的定理](https://en.wikipedia.org/wiki/Stone%27s_theorem_on_one-parameter_unitary_groups)，$U （t） = \exp （i H t） $ for a operator $H $，其中 $ \exp $ 是矩阵指数，如[高级矩阵](xref:microsoft.quantum.concepts.matrix-advanced)中所述。
Eigenstate $ \ket{\phi} $ of $H $，因此 $H \ket{\phi} = \phi \ket{\phi} $ 还 $U （t） $，适用于所有 $t $，eigenstate U （t） \begin{equation} = e ^ {i \ket{\phi} t} \phi
\end{equation}

可以应用对[Bayesian 阶段估算](#bayesian-phase-estimation)讨论的完全相同的分析，并且可能性函数对于此更常规的 oracle 模型是完全相同的： $ $ \Pr （\texttt{Zero} | \phi; t，\theta） = \cos ^ 2 \ 左（\frac{t [\phi-\theta]}{2}\right）。
$ $ 而且，如果 $U $ 是 dynamical 生成器的模拟， [Hamiltonian 模拟](xref:microsoft.quantum.libraries.applications#hamiltonian-simulation)情况下，我们会将 $ \phi $ 解释为能源。
因此，通过连续查询使用阶段估算，可以了解分子、[材料](https://arxiv.org/abs/1510.03859)或[现场理论](https://arxiv.org/abs/1111.3633v2)的模拟[能源](https://arxiv.org/abs/quant-ph/0604193)，无需通过要求将 $t $ 为整数来损害我们选择的实验。

### <a name="random-walk-phase-estimation"></a>随机审核阶段估算 ###

Q # 提供了一个非常有用的 Bayesian 阶段估算，旨在使用接近于量程的设备，这些设备通过对从迭代阶段估算获取的数据记录进行随机审核来进行。
此方法既是自适应的，也是完全确定性的，允许在估计阶段 $ \hat{\phi} $ 中的错误中进行近乎最佳的缩放，内存开销非常低。

协议使用近似的 Bayesian 推理方法，该方法假定之前的分布是高斯。
此高斯假设允许使用分析公式来最大程度地减少后验方差。
然后，该算法将根据该实验的结果，将 $ \phi $ 的估计值向左或向右移动一个预先确定的量，并按预先确定的量来缩减该方差。
此平均值和方差为下一次试验提供了在 $ \phi $ 之前指定高斯所需的所有信息。
意外的度量失败，或在初始之前的反面上的实际结果可能导致此方法失败。
它通过执行试验来测试当前平均值和标准偏差是否适用于系统，从而从失败中恢复。
如果不是，则该算法将执行遍历的反向步骤，并继续执行该过程。
单步执行的功能还允许该算法了解，即使初始之前的标准偏差 inapropriately 小也是如此。

## <a name="calling-phase-estimation-algorithms"></a>调用阶段估算算法 ##

使用 Q # canon 提供的每个阶段估计操作采用一组不同的输入，参数化从最终估计 $ \hat{\phi} $ 中所需的质量。
但这些不同的输入都有多个共同的输入，因此，部分应用程序的质量参数导致公共签名。
例如，在下一部分中讨论的 <xref:microsoft.quantum.characterization.robustphaseestimation> 操作具有以下签名：

```qsharp
operation RobustPhaseEstimation(bitsPrecision : Int, oracle : DiscreteOracle, eigenstate : Qubit[])  : Double
```

`bitsPrecision` 输入对于 `RobustPhaseEstimation`是唯一的，而 `oracle` 和 `eigenstate` 是通用的。
因此，如**H2Sample**中所示，操作可以接受具有格式 `(DiscreteOracle, Qubit[]) => Unit` 的迭代阶段估算算法，以允许用户指定任意阶段估算算法：

```qsharp
operation H2EstimateEnergy(
    idxBondLength : Int,
    trotterStepSize : Double,
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double))
: Double
```

这些无数阶段估算算法针对不同的属性和输入参数进行了优化，这些属性和输入参数必须被理解为目标应用程序的最佳选择。 例如，某些阶段估算算法是自适应的，这意味着，以后的步骤经典由前面步骤的测量结果控制。 有些情况下，需要能够通过任意实际的 exponentiate 来其黑洞的单一 oracle，而其他人只需使用整数，而只需要解析阶段估算 $ 2 \ pi $。 有些辅助 qubits，而其他只需要一个。

同样，使用随机审核阶段估算的方式与 canon 提供的其他算法的执行方式几乎相同：

```qsharp
operation ApplyExampleOracle(
    eigenphase : Double,
    time : Double,
    register : Qubit[])
: Unit is Adj + Ctl {
    Rz(2.0 * eigenphase * time, register[0]);
}

operation EstimateBayesianPhase(eigenphase : Double) : Double {
    let oracle = ContinuousOracle(ApplyExampleOracle(eigenphase, _, _));
    using (eigenstate = Qubit()) {
        X(eigenstate);
        // The additional inputs here specify the mean and variance of the prior, the number of
        // iterations to perform, how many iterations to perform as a maximum, and how many
        // steps to roll back on an approximation failure.
        let est = RandomWalkPhaseEstimation(0.0, 1.0, 61, 100000, 1, oracle, [eigenstate]);
        Reset(eigenstate);
        return est;
    }
}
```
