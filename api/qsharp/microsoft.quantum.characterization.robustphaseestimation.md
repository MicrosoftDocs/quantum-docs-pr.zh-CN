---
uid: Microsoft.Quantum.Characterization.RobustPhaseEstimation
title: RobustPhaseEstimation 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: RobustPhaseEstimation
qsharp.summary: Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.
ms.openlocfilehash: d04ee578c0e6f916e9a4da451075b79e0630c70a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695878"
---
# <a name="robustphaseestimation-operation"></a><span data-ttu-id="7c1fc-102">RobustPhaseEstimation 操作</span><span class="sxs-lookup"><span data-stu-id="7c1fc-102">RobustPhaseEstimation operation</span></span>

<span data-ttu-id="7c1fc-103">命名空间 [：](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="7c1fc-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="7c1fc-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7c1fc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7c1fc-105">为给定的 oracle 和 eigenstate 执行强健的非迭代量程阶段估算算法 `U` ，并提供针对海森堡限制处的变化缩放阶段的单个实际值估算。</span><span class="sxs-lookup"><span data-stu-id="7c1fc-105">Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.</span></span>

```qsharp
operation RobustPhaseEstimation (bitsPrecision : Int, oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="7c1fc-106">输入</span><span class="sxs-lookup"><span data-stu-id="7c1fc-106">Input</span></span>

### <a name="bitsprecision--int"></a><span data-ttu-id="7c1fc-107">bitsPrecision： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7c1fc-107">bitsPrecision : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7c1fc-108">这将使用标准偏差 $ \sigma \le 2 \ pi/2 ^ \text{bitsPrecision} $ （如 $ \sigma \le 10.7 \pi/\text{# of 查询} $）来估计 $ \phi $ with</span><span class="sxs-lookup"><span data-stu-id="7c1fc-108">This provides an estimate of $\phi$ with standard deviation $\sigma \le 2\pi / 2^\text{bitsPrecision}$ using a number of queries scaling like $\sigma \le 10.7 \pi / \text{# of queries}$.</span></span>


### <a name="oracle--discreteoracle"></a><span data-ttu-id="7c1fc-109">oracle： [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="7c1fc-109">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="7c1fc-110">为给定整数幂运算实现 $U ^ m $ $m $ 的操作。</span><span class="sxs-lookup"><span data-stu-id="7c1fc-110">An operation implementing $U^m$ for given integer powers $m$.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="7c1fc-111">targetState： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7c1fc-111">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7c1fc-112">$U $ 作用于的量程寄存器。</span><span class="sxs-lookup"><span data-stu-id="7c1fc-112">A quantum register that $U$ acts on.</span></span> <span data-ttu-id="7c1fc-113">如果它存储 $U $ 的 eigenstate $ \ket{\phi} $，则 $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ for $ \phi\in (-\pi，\pi] $ 未知阶段。</span><span class="sxs-lookup"><span data-stu-id="7c1fc-113">If it stores an eigenstate $\ket{\phi}$ of $U$, then $U\ket{\phi} = e^{i\phi} \ket{\phi}$ for $\phi\in(-\pi,\pi]$ an unknown phase.</span></span>



## <a name="output--double"></a><span data-ttu-id="7c1fc-114">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7c1fc-114">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="7c1fc-115">注解</span><span class="sxs-lookup"><span data-stu-id="7c1fc-115">Remarks</span></span>

<span data-ttu-id="7c1fc-116">在大量查询的限制中，$ \phi $ 满足 $ \sigma \ge 2 \pi/\text{# of 查询} $ 的估计值的标准偏差 Cramer-Rao 下限。</span><span class="sxs-lookup"><span data-stu-id="7c1fc-116">In the limit of a large number of queries, Cramer-Rao lower bounds for the standard deviation of the estimate of $\phi$ satisfy $\sigma \ge 2 \pi / \text{# of queries}$.</span></span>

## <a name="references"></a><span data-ttu-id="7c1fc-117">参考</span><span class="sxs-lookup"><span data-stu-id="7c1fc-117">References</span></span>

- <span data-ttu-id="7c1fc-118">通过 Shelby Kimmel、Guang 脱离 Hao Low、Theodore Yoder 对通用 Single-Qubit Gate-Set 进行可靠的校准 https://arxiv.org/abs/1502.02677</span><span class="sxs-lookup"><span data-stu-id="7c1fc-118">Robust Calibration of a Universal Single-Qubit Gate-Set via Robust Phase Estimation Shelby Kimmel, Guang Hao Low, Theodore J. Yoder https://arxiv.org/abs/1502.02677</span></span>