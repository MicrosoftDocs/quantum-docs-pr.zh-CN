---
uid: Microsoft.Quantum.Characterization.DiscretePhaseEstimationIteration
title: DiscretePhaseEstimationIteration 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: DiscretePhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.
ms.openlocfilehash: 8ce1e1a2bda6507285f055c87619a8760c891082
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204379"
---
# <a name="discretephaseestimationiteration-operation"></a><span data-ttu-id="95311-102">DiscretePhaseEstimationIteration 操作</span><span class="sxs-lookup"><span data-stu-id="95311-102">DiscretePhaseEstimationIteration operation</span></span>

<span data-ttu-id="95311-103">命名空间 [：](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="95311-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="95311-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="95311-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="95311-105">使用单一 oracle 的整数幂，对迭代 (经典控制的) 阶段估算算法执行单个迭代。</span><span class="sxs-lookup"><span data-stu-id="95311-105">Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.</span></span>

```qsharp
operation DiscretePhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, power : Int, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="95311-106">输入</span><span class="sxs-lookup"><span data-stu-id="95311-106">Input</span></span>

### <a name="oracle--discreteoracle"></a><span data-ttu-id="95311-107">oracle： [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="95311-107">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="95311-108">对整数和寄存器进行操作，以便将 $U ^ m $ 应用于给定寄存器，其中 $U $ 是要估计其阶段的那个那个，其中 $m $ 是为 oracle 提供的整数幂</span><span class="sxs-lookup"><span data-stu-id="95311-108">Operation acting on an integer and a register, such that $U^m$ is applied to the given register, where $U$ is the unitary whose phase is to be estimated, and where $m$ is the integer power given to the oracle</span></span>


### <a name="power--int"></a><span data-ttu-id="95311-109">幂： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="95311-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="95311-110">应用给定的单一 oracle 的次数。</span><span class="sxs-lookup"><span data-stu-id="95311-110">Number of times to apply the given unitary oracle.</span></span>


### <a name="theta--double"></a><span data-ttu-id="95311-111">theta： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="95311-111">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="95311-112">在操作目标状态之前，要将控制 qubit 上的阶段反转的角度。</span><span class="sxs-lookup"><span data-stu-id="95311-112">Angle by which to invert the phase on the control qubit before acting on the target state.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="95311-113">targetState： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="95311-113">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="95311-114">注册由给定的单一 oracle 处理的状态。</span><span class="sxs-lookup"><span data-stu-id="95311-114">Register of state acted upon by the given unitary oracle.</span></span>


### <a name="controlqubit--qubit"></a><span data-ttu-id="95311-115">controlQubit： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="95311-115">controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="95311-116">用于控制给定 oracle 的应用程序的辅助 qubit。</span><span class="sxs-lookup"><span data-stu-id="95311-116">An auxiliary qubit used to control the application of the given oracle.</span></span>



## <a name="output--unit"></a><span data-ttu-id="95311-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="95311-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

