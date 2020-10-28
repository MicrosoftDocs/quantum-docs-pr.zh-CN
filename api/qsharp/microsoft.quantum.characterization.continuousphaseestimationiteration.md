---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: ContinuousPhaseEstimationIteration 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: a3914a4b19e3b898b6de8808699da09d386f487a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695898"
---
# <a name="continuousphaseestimationiteration-operation"></a><span data-ttu-id="f95e0-102">ContinuousPhaseEstimationIteration 操作</span><span class="sxs-lookup"><span data-stu-id="f95e0-102">ContinuousPhaseEstimationIteration operation</span></span>

<span data-ttu-id="f95e0-103">命名空间 [：](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="f95e0-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="f95e0-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f95e0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f95e0-105">使用单一 oracle 的任意实际幂，执行迭代 (经典控制的) 阶段估算算法的单个迭代。</span><span class="sxs-lookup"><span data-stu-id="f95e0-105">Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.</span></span>

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="f95e0-106">输入</span><span class="sxs-lookup"><span data-stu-id="f95e0-106">Input</span></span>

### <a name="oracle--continuousoracle"></a><span data-ttu-id="f95e0-107">oracle： [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span><span class="sxs-lookup"><span data-stu-id="f95e0-107">oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span></span>

<span data-ttu-id="f95e0-108">在双 $t $ 和 a 寄存器上操作的操作，因此 $U ^ t $ 应用于给定寄存器，其中 $U $ 是要估计其阶段的那个那个，其中 $t $ 是给定于 oracle 的整数幂</span><span class="sxs-lookup"><span data-stu-id="f95e0-108">Operation acting on a double $t$ and a register, such that $U^t$ is applied to the given register, where $U$ is the unitary whose phase is to be estimated, and where $t$ is the integer power given to the oracle</span></span>


### <a name="time--double"></a><span data-ttu-id="f95e0-109">时间： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f95e0-109">time : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f95e0-110">应用给定的单一 oracle 的次数。</span><span class="sxs-lookup"><span data-stu-id="f95e0-110">Number of times to apply the given unitary oracle.</span></span>


### <a name="theta--double"></a><span data-ttu-id="f95e0-111">theta： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f95e0-111">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f95e0-112">在操作目标状态之前，要将控制 qubit 上的阶段反转的角度。</span><span class="sxs-lookup"><span data-stu-id="f95e0-112">Angle by which to invert the phase on the control qubit before acting on the target state.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="f95e0-113">targetState： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f95e0-113">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f95e0-114">注册由给定的单一 oracle 处理的状态。</span><span class="sxs-lookup"><span data-stu-id="f95e0-114">Register of state acted upon by the given unitary oracle.</span></span>


### <a name="controlqubit--qubit"></a><span data-ttu-id="f95e0-115">controlQubit： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f95e0-115">controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="f95e0-116">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f95e0-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

