---
uid: Microsoft.Quantum.Simulation.TrotterStep
title: TrotterStep 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStep
qsharp.summary: Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.
ms.openlocfilehash: 7a1a27ba4dc4b8b7bbc4da6a378d4a1494bc9415
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701104"
---
# <a name="trotterstep-function"></a><span data-ttu-id="221a3-102">TrotterStep 函数</span><span class="sxs-lookup"><span data-stu-id="221a3-102">TrotterStep function</span></span>

<span data-ttu-id="221a3-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="221a3-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="221a3-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="221a3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="221a3-105">使用 Trotter – Suzuki 分解中所述的系统实现一次时间演变 `EvolutionGenerator` 。</span><span class="sxs-lookup"><span data-stu-id="221a3-105">Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.</span></span>

```qsharp
function TrotterStep (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, trotterOrder : Int, trotterStepSize : Double) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="221a3-106">输入</span><span class="sxs-lookup"><span data-stu-id="221a3-106">Input</span></span>

### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="221a3-107">evolutionGenerator： [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="221a3-107">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="221a3-108">要模拟的系统的完整说明。</span><span class="sxs-lookup"><span data-stu-id="221a3-108">A complete description of the system to be simulated.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="221a3-109">trotterOrder： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="221a3-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="221a3-110">Trotter 集成器的顺序。</span><span class="sxs-lookup"><span data-stu-id="221a3-110">Order of Trotter integrator.</span></span> <span data-ttu-id="221a3-111">此值必须是1或偶数。</span><span class="sxs-lookup"><span data-stu-id="221a3-111">This must be either 1 or an even number.</span></span>


### <a name="trotterstepsize--double"></a><span data-ttu-id="221a3-112">trotterStepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="221a3-112">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="221a3-113">单个 Trotter 步骤中模拟时间演化的持续时间。</span><span class="sxs-lookup"><span data-stu-id="221a3-113">Duration of simulated time-evolution in single Trotter step.</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="221a3-114">Output： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="221a3-114">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="221a3-115">一项操作，该操作约为持续时间演化的单个步骤 `trotterStepSize` 。</span><span class="sxs-lookup"><span data-stu-id="221a3-115">Unitary operation that approximates a single step of time-evolution for duration `trotterStepSize`.</span></span>

## <a name="remarks"></a><span data-ttu-id="221a3-116">注解</span><span class="sxs-lookup"><span data-stu-id="221a3-116">Remarks</span></span>

<span data-ttu-id="221a3-117">有关 Trotter – Suzuki 分解的详细信息，请参阅 [按时间排序的组合](/quantum/libraries/control-flow#time-ordered-composition)。</span><span class="sxs-lookup"><span data-stu-id="221a3-117">For more on the Trotter–Suzuki decomposition, see [Time-Ordered Composition](/quantum/libraries/control-flow#time-ordered-composition).</span></span>