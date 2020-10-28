---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithmImpl
title: TimeDependentTrotterSimulationAlgorithmImpl 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithmImpl
qsharp.summary: Implementation of multiple Trotter steps to approximate a unitary operator that solves the time-dependent Schrödinger equation.
ms.openlocfilehash: c6d1c976d29c69d3ac14d9a2be09826602c8cc1d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696620"
---
# <a name="timedependenttrottersimulationalgorithmimpl-operation"></a><span data-ttu-id="b103f-102">TimeDependentTrotterSimulationAlgorithmImpl 操作</span><span class="sxs-lookup"><span data-stu-id="b103f-102">TimeDependentTrotterSimulationAlgorithmImpl operation</span></span>

<span data-ttu-id="b103f-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="b103f-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="b103f-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b103f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b103f-105">实现多个 Trotter 步骤，以近似求解依赖于时间的 Schrödinger 公式的单一运算符。</span><span class="sxs-lookup"><span data-stu-id="b103f-105">Implementation of multiple Trotter steps to approximate a unitary operator that solves the time-dependent Schrödinger equation.</span></span>

```qsharp
operation TimeDependentTrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionSchedule : Microsoft.Quantum.Simulation.EvolutionSchedule, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="b103f-106">输入</span><span class="sxs-lookup"><span data-stu-id="b103f-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="b103f-107">trotterStepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b103f-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b103f-108">单个 Trotter 步骤中模拟时间演化的持续时间。</span><span class="sxs-lookup"><span data-stu-id="b103f-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="b103f-109">trotterOrder： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b103f-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b103f-110">Trotter 集成器的顺序。</span><span class="sxs-lookup"><span data-stu-id="b103f-110">Order of Trotter integrator.</span></span> <span data-ttu-id="b103f-111">此值必须是1或偶数。</span><span class="sxs-lookup"><span data-stu-id="b103f-111">This must be either 1 or an even number.</span></span>


### <a name="maxtime--double"></a><span data-ttu-id="b103f-112">maxTime： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b103f-112">maxTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b103f-113">模拟 $t $ 的总持续时间。</span><span class="sxs-lookup"><span data-stu-id="b103f-113">Total duration of simulation $t$.</span></span>


### <a name="evolutionschedule--evolutionschedule"></a><span data-ttu-id="b103f-114">evolutionSchedule： [evolutionSchedule](xref:Microsoft.Quantum.Simulation.EvolutionSchedule)</span><span class="sxs-lookup"><span data-stu-id="b103f-114">evolutionSchedule : [EvolutionSchedule](xref:Microsoft.Quantum.Simulation.EvolutionSchedule)</span></span>

<span data-ttu-id="b103f-115">要模拟的与时间相关的系统的完整说明。</span><span class="sxs-lookup"><span data-stu-id="b103f-115">A complete description of the time-dependent system to be simulated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="b103f-116">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b103f-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b103f-117">Qubits 由模拟处理。</span><span class="sxs-lookup"><span data-stu-id="b103f-117">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b103f-118">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b103f-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

