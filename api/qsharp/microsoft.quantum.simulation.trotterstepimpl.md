---
uid: Microsoft.Quantum.Simulation.TrotterStepImpl
title: TrotterStepImpl 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStepImpl
qsharp.summary: Implements time-evolution by a term contained in a `GeneratorSystem`.
ms.openlocfilehash: 1ddd7ab33df243d729b5b48cba393d976bfd3640
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701096"
---
# <a name="trotterstepimpl-operation"></a><span data-ttu-id="8e17b-102">TrotterStepImpl 操作</span><span class="sxs-lookup"><span data-stu-id="8e17b-102">TrotterStepImpl operation</span></span>

<span data-ttu-id="8e17b-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="8e17b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="8e17b-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8e17b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8e17b-105">通过中包含的术语实现时间演变 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="8e17b-105">Implements time-evolution by a term contained in a `GeneratorSystem`.</span></span>

```qsharp
operation TrotterStepImpl (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, idx : Int, stepsize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="8e17b-106">输入</span><span class="sxs-lookup"><span data-stu-id="8e17b-106">Input</span></span>

### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="8e17b-107">evolutionGenerator： [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="8e17b-107">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="8e17b-108">要模拟的系统的完整说明。</span><span class="sxs-lookup"><span data-stu-id="8e17b-108">A complete description of the system to be simulated.</span></span>


### <a name="idx--int"></a><span data-ttu-id="8e17b-109">idx： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8e17b-109">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8e17b-110">所述系统中某个术语的整数索引。</span><span class="sxs-lookup"><span data-stu-id="8e17b-110">Integer index to a term in the described system.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="8e17b-111">stepsize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8e17b-111">stepsize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8e17b-112">按术语编制索引的按时间推移的持续时间的乘数 `idx` 。</span><span class="sxs-lookup"><span data-stu-id="8e17b-112">Multiplier on duration of time-evolution by term indexed by `idx`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="8e17b-113">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8e17b-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8e17b-114">Qubits 由模拟处理。</span><span class="sxs-lookup"><span data-stu-id="8e17b-114">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8e17b-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8e17b-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

