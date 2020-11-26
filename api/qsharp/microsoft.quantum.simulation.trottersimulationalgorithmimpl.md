---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithmImpl
title: TrotterSimulationAlgorithmImpl 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithmImpl
qsharp.summary: Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp(_-iHt_).
ms.openlocfilehash: 5b796245e2a4434228260a229cb61be66f3e38d6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203393"
---
# <a name="trottersimulationalgorithmimpl-operation"></a><span data-ttu-id="dddc5-102">TrotterSimulationAlgorithmImpl 操作</span><span class="sxs-lookup"><span data-stu-id="dddc5-102">TrotterSimulationAlgorithmImpl operation</span></span>

<span data-ttu-id="dddc5-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="dddc5-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="dddc5-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dddc5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dddc5-105">进行重复调用 `TrotterStep` ，以近似于时间演化运算符 exp (_-iHt_) 。</span><span class="sxs-lookup"><span data-stu-id="dddc5-105">Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp(_-iHt_).</span></span>

```qsharp
operation TrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="dddc5-106">输入</span><span class="sxs-lookup"><span data-stu-id="dddc5-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="dddc5-107">trotterStepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="dddc5-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="dddc5-108">单个 Trotter 步骤中模拟时间演化的持续时间。</span><span class="sxs-lookup"><span data-stu-id="dddc5-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="dddc5-109">trotterOrder： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dddc5-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dddc5-110">Trotter 集成器的顺序。</span><span class="sxs-lookup"><span data-stu-id="dddc5-110">Order of Trotter integrator.</span></span> <span data-ttu-id="dddc5-111">此值必须是1或偶数。</span><span class="sxs-lookup"><span data-stu-id="dddc5-111">This must be either 1 or an even number.</span></span>


### <a name="maxtime--double"></a><span data-ttu-id="dddc5-112">maxTime： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="dddc5-112">maxTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="dddc5-113">模拟 $t $ 的总持续时间。</span><span class="sxs-lookup"><span data-stu-id="dddc5-113">Total duration of simulation $t$.</span></span>


### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="dddc5-114">evolutionGenerator： [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="dddc5-114">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="dddc5-115">要模拟的系统的完整说明。</span><span class="sxs-lookup"><span data-stu-id="dddc5-115">A complete description of the system to be simulated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="dddc5-116">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="dddc5-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="dddc5-117">Qubits 由模拟处理。</span><span class="sxs-lookup"><span data-stu-id="dddc5-117">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dddc5-118">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dddc5-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

