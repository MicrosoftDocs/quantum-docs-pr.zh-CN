---
uid: Microsoft.Quantum.Simulation.TrotterStepImpl
title: TrotterStepImpl 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStepImpl
qsharp.summary: Implements time-evolution by a term contained in a `GeneratorSystem`.
ms.openlocfilehash: 33dc922cd5a60590a1306369fb99615fc6575b22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856730"
---
# <a name="trotterstepimpl-operation"></a><span data-ttu-id="cbdcc-102">TrotterStepImpl 操作</span><span class="sxs-lookup"><span data-stu-id="cbdcc-102">TrotterStepImpl operation</span></span>

<span data-ttu-id="cbdcc-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="cbdcc-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="cbdcc-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cbdcc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cbdcc-105">通过中包含的术语实现时间演变 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="cbdcc-105">Implements time-evolution by a term contained in a `GeneratorSystem`.</span></span>

```qsharp
operation TrotterStepImpl (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, idx : Int, stepsize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="cbdcc-106">输入</span><span class="sxs-lookup"><span data-stu-id="cbdcc-106">Input</span></span>

### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="cbdcc-107">evolutionGenerator： [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="cbdcc-107">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="cbdcc-108">要模拟的系统的完整说明。</span><span class="sxs-lookup"><span data-stu-id="cbdcc-108">A complete description of the system to be simulated.</span></span>


### <a name="idx--int"></a><span data-ttu-id="cbdcc-109">idx： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cbdcc-109">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cbdcc-110">所述系统中某个术语的整数索引。</span><span class="sxs-lookup"><span data-stu-id="cbdcc-110">Integer index to a term in the described system.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="cbdcc-111">stepsize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cbdcc-111">stepsize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cbdcc-112">按术语编制索引的按时间推移的持续时间的乘数 `idx` 。</span><span class="sxs-lookup"><span data-stu-id="cbdcc-112">Multiplier on duration of time-evolution by term indexed by `idx`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="cbdcc-113">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cbdcc-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="cbdcc-114">Qubits 由模拟处理。</span><span class="sxs-lookup"><span data-stu-id="cbdcc-114">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cbdcc-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cbdcc-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

