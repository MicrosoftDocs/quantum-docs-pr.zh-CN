---
uid: Microsoft.Quantum.Research.Characterization.RandomWalkPhaseEstimation
title: RandomWalkPhaseEstimation 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Characterization
qsharp.name: RandomWalkPhaseEstimation
qsharp.summary: Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.
ms.openlocfilehash: f9edafcce62c8b30a6bd52b7dbaa2df2c50c920d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846002"
---
# <a name="randomwalkphaseestimation-operation"></a><span data-ttu-id="df07c-102">RandomWalkPhaseEstimation 操作</span><span class="sxs-lookup"><span data-stu-id="df07c-102">RandomWalkPhaseEstimation operation</span></span>

<span data-ttu-id="df07c-103">命名空间 [： ...](xref:Microsoft.Quantum.Research.Characterization)</span><span class="sxs-lookup"><span data-stu-id="df07c-103">Namespace: [Microsoft.Quantum.Research.Characterization](xref:Microsoft.Quantum.Research.Characterization)</span></span>

<span data-ttu-id="df07c-104">包： [Microsoft 量子. 信息](https://nuget.org/packages/Microsoft.Quantum.Research.Characterization)</span><span class="sxs-lookup"><span data-stu-id="df07c-104">Package: [Microsoft.Quantum.Research.Characterization](https://nuget.org/packages/Microsoft.Quantum.Research.Characterization)</span></span>


<span data-ttu-id="df07c-105">执行迭代阶段估算，并使用随机遍历来估算给定 oracle 和 eigenstate 的传统测量结果中的 Bayesian 推理。</span><span class="sxs-lookup"><span data-stu-id="df07c-105">Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.</span></span>

```qsharp
operation RandomWalkPhaseEstimation (initialMean : Double, initialStdDev : Double, nMeasurements : Int, maxMeasurements : Int, unwind : Int, oracle : Microsoft.Quantum.Oracles.ContinuousOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="df07c-106">输入</span><span class="sxs-lookup"><span data-stu-id="df07c-106">Input</span></span>

### <a name="initialmean--double"></a><span data-ttu-id="df07c-107">initialMean： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="df07c-107">initialMean : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="df07c-108">$ \Phi $ 前面初始正常分布的平均值。</span><span class="sxs-lookup"><span data-stu-id="df07c-108">Mean of the initial normal prior distribution over $\phi$.</span></span>


### <a name="initialstddev--double"></a><span data-ttu-id="df07c-109">initialStdDev： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="df07c-109">initialStdDev : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="df07c-110">在 $ \phi $ 之前的初始正常之前的标准偏差。</span><span class="sxs-lookup"><span data-stu-id="df07c-110">Standard deviation of the initial normal prior distribution over $\phi$.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="df07c-111">nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="df07c-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="df07c-112">要接受到最终后验估计值的度量值的数量。</span><span class="sxs-lookup"><span data-stu-id="df07c-112">Number of measurements to be accepted into the final posterior estimate.</span></span>


### <a name="maxmeasurements--int"></a><span data-ttu-id="df07c-113">maxMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="df07c-113">maxMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="df07c-114">在操作被视为失败之前可以执行的度量总数。</span><span class="sxs-lookup"><span data-stu-id="df07c-114">Total number of measurements than can be taken before the operation is considered to have failed.</span></span>


### <a name="unwind--int"></a><span data-ttu-id="df07c-115">展开： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="df07c-115">unwind : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="df07c-116">一致性检查失败时要记住的结果数。</span><span class="sxs-lookup"><span data-stu-id="df07c-116">Number of results to forget when consistency checks fail.</span></span>


### <a name="oracle--continuousoracle"></a><span data-ttu-id="df07c-117">oracle： [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span><span class="sxs-lookup"><span data-stu-id="df07c-117">oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span></span>

<span data-ttu-id="df07c-118">表示单一 $U $ 的操作，$U (t) \ket{\phi} = e ^ {\phi}\ket{\phi} $ for eigenstates $ \ket{\phi} $，其中包含未知阶段 $ \phi \in \mathbb{R} ^ + $。</span><span class="sxs-lookup"><span data-stu-id="df07c-118">An operation representing a unitary $U$ such that $U(t)\ket{\phi} = e^{i t \phi}\ket{\phi}$ for eigenstates $\ket{\phi}$ with unknown phase $\phi \in \mathbb{R}^+$.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="df07c-119">targetState： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="df07c-119">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="df07c-120">$U $ 操作的寄存器。</span><span class="sxs-lookup"><span data-stu-id="df07c-120">A register that $U$ acts on.</span></span>



## <a name="output--double"></a><span data-ttu-id="df07c-121">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="df07c-121">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="df07c-122">最终的估计 $ \hat{\phi} \mathrel{： =} \expect [\phi] $，其中，假定所有接受的数据都超出了后验。</span><span class="sxs-lookup"><span data-stu-id="df07c-122">The final estimate $\hat{\phi} \mathrel{:=} \expect[\phi]$ , where the expectation is over the posterior given all accepted data.</span></span>

## <a name="remarks"></a><span data-ttu-id="df07c-123">备注</span><span class="sxs-lookup"><span data-stu-id="df07c-123">Remarks</span></span>

### <a name="iterative-phase-estimation-and-eigenstates"></a><span data-ttu-id="df07c-124">迭代阶段估计和 Eigenstates</span><span class="sxs-lookup"><span data-stu-id="df07c-124">Iterative Phase Estimation and Eigenstates</span></span>

<span data-ttu-id="df07c-125">通常，输入寄存器 `eigenstate` 不需要是 $U $ 的 eigenstate $ \ket{\phi} $，但可以是 eigenstates 上的 superposition。</span><span class="sxs-lookup"><span data-stu-id="df07c-125">In general, the input register `eigenstate` need not be an eigenstate $\ket{\phi}$ of $U$, but can be a superposition over eigenstates.</span></span> <span data-ttu-id="df07c-126">假设输入状态由 \begin{align} \ket{\psi} & = \sum \_ {j} \alpha \_ j \ket{\phi \_ j}，\end{align}，其中 $ \{ \alpha \_ j \} $ 是复数系数，如 $ \sum \_ j | \alpha \_ j | ^ 2 = $1，其中 $U \ket{\phi \_ j} = \phi \_ j\ket {\ phi \_ j} $。</span><span class="sxs-lookup"><span data-stu-id="df07c-126">Suppose that the input state is given by \begin{align} \ket{\psi} & = \sum\_{j} \alpha\_j \ket{\phi\_j}, \end{align} where $\{\alpha\_j\}$ are complex coefficients such that $\sum\_j |\alpha\_j|^2 = 1$ and where $U\ket{\phi\_j} = \phi\_j\ket{\phi\_j}$.</span></span>

<span data-ttu-id="df07c-127">然后，执行迭代阶段估算最终将聚合到单个 eigenstate，如 [开发指南](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates)中所述。</span><span class="sxs-lookup"><span data-stu-id="df07c-127">Then, performing iterative phase estimation will eventually converge to a single eigenstate, as described in the [development guide](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates).</span></span>

### <a name="experiment-design"></a><span data-ttu-id="df07c-128">试验设计</span><span class="sxs-lookup"><span data-stu-id="df07c-128">Experiment Design</span></span>

<span data-ttu-id="df07c-129">根据粒子推测试探法 $ \theta $ 传递到的度量 $t 时间 $ $ `oracle` ， \Begin{align} \theta \sim \Pr ( \phi) ，\quad t \approx \frac {1} {\variance{\phi}}。</span><span class="sxs-lookup"><span data-stu-id="df07c-129">The measurement times $t$ and inversion angles $\theta$ passed to `oracle` are chosen according to the *particle guess heuristic*, \begin{align} \theta \sim \Pr(\phi),\quad t \approx \frac{1}{\variance{\phi}}.</span></span>
<span data-ttu-id="df07c-130">\end{align} 这种试探的最佳做法是，在以前的假设条件下，使用迭代阶段估算来减少预期的后验方差。</span><span class="sxs-lookup"><span data-stu-id="df07c-130">\end{align} This heuristic is optimal for reducing the expected posterior variance in iterative phase estimation under the assumption of a normal prior.</span></span>

### <a name="optimality"></a><span data-ttu-id="df07c-131">最优性</span><span class="sxs-lookup"><span data-stu-id="df07c-131">Optimality</span></span>

<span data-ttu-id="df07c-132">此操作近似于阶段 $ \phi $ 的最佳估计器，因为使用二次丢失 $L ( \phi，\hat{\phi} ) \mathrel{： =} ( \phi-\hat{\phi} ) ^ $2。</span><span class="sxs-lookup"><span data-stu-id="df07c-132">This operation approximates the optimal estimator for the phase $\phi$, as evaluated using the quadratic loss $L(\phi, \hat{\phi}) \mathrel{:=} (\phi - \hat{\phi})^2$.</span></span>

<span data-ttu-id="df07c-133">有关迭代阶段估算统计信息的详细信息，请参阅 [Bayesian 阶段估算](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) 。</span><span class="sxs-lookup"><span data-stu-id="df07c-133">See [Bayesian Phase Estimation](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) for more details on the statistics of iterative phase estimation.</span></span>

## <a name="references"></a><span data-ttu-id="df07c-134">参考</span><span class="sxs-lookup"><span data-stu-id="df07c-134">References</span></span>

- <span data-ttu-id="df07c-135">Ferrie *et al.* 2011 [doi>10.1145： 10/tfx-cli](https://doi.org/10.1007/s11128-012-0407-6)， [arXiv： 1110.3067](https://arxiv.org/abs/1110.3067)。</span><span class="sxs-lookup"><span data-stu-id="df07c-135">Ferrie *et al.* 2011 [doi:10/tfx](https://doi.org/10.1007/s11128-012-0407-6), [arXiv:1110.3067](https://arxiv.org/abs/1110.3067).</span></span>
- <span data-ttu-id="df07c-136">Wiebe *et al.* 2013 [doi>10.1145： 10/tf3](https://doi.org/10.1103/PhysRevLett.112.190501)、 [arXiv： 1309.0876](https://arxiv.org/abs/1309.0876)</span><span class="sxs-lookup"><span data-stu-id="df07c-136">Wiebe *et al.* 2013 [doi:10/tf3](https://doi.org/10.1103/PhysRevLett.112.190501), [arXiv:1309.0876](https://arxiv.org/abs/1309.0876)</span></span>
- <span data-ttu-id="df07c-137">Wiebe 和 Granade 2018 *(准备)*。</span><span class="sxs-lookup"><span data-stu-id="df07c-137">Wiebe and Granade 2018 *(in preparation)*.</span></span>