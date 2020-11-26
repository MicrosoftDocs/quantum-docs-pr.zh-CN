---
uid: Microsoft.Quantum.Simulation.InterpolatedEvolution
title: InterpolatedEvolution 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolatedEvolution
qsharp.summary: Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.
ms.openlocfilehash: 2ad907c02a2412dd4bf95630f401b5f1db5c8a08
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225102"
---
# <a name="interpolatedevolution-function"></a><span data-ttu-id="b5360-102">InterpolatedEvolution 函数</span><span class="sxs-lookup"><span data-stu-id="b5360-102">InterpolatedEvolution function</span></span>

<span data-ttu-id="b5360-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="b5360-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="b5360-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b5360-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b5360-105">使用统一的计划在两个生成器之间进行内插，返回一个操作，该操作在生成的时间依赖生成器下将模拟进化应用于 qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="b5360-105">Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.</span></span>

```qsharp
function InterpolatedEvolution (interpolationTime : Double, evolutionGeneratorStart : Microsoft.Quantum.Simulation.EvolutionGenerator, evolutionGeneratorEnd : Microsoft.Quantum.Simulation.EvolutionGenerator, timeDependentSimulationAlgorithm : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="b5360-106">输入</span><span class="sxs-lookup"><span data-stu-id="b5360-106">Input</span></span>

### <a name="interpolationtime--double"></a><span data-ttu-id="b5360-107">interpolationTime： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b5360-107">interpolationTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b5360-108">执行内插的时间。</span><span class="sxs-lookup"><span data-stu-id="b5360-108">Time to perform the interpolation over.</span></span>


### <a name="evolutiongeneratorstart--evolutiongenerator"></a><span data-ttu-id="b5360-109">evolutionGeneratorStart： [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="b5360-109">evolutionGeneratorStart : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="b5360-110">用于模拟进化的初始生成器。</span><span class="sxs-lookup"><span data-stu-id="b5360-110">Initial generator to simulate evolution under.</span></span>


### <a name="evolutiongeneratorend--evolutiongenerator"></a><span data-ttu-id="b5360-111">evolutionGeneratorEnd： [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="b5360-111">evolutionGeneratorEnd : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="b5360-112">用于模拟进化的最终生成器。</span><span class="sxs-lookup"><span data-stu-id="b5360-112">Final generator to simulate evolution under.</span></span>


### <a name="timedependentsimulationalgorithm--timedependentsimulationalgorithm"></a><span data-ttu-id="b5360-113">timeDependentSimulationAlgorithm： [timeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="b5360-113">timeDependentSimulationAlgorithm : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span></span>

<span data-ttu-id="b5360-114">一种依赖于时间的模拟算法，用于模拟统一内插计划期间的演变。</span><span class="sxs-lookup"><span data-stu-id="b5360-114">A time-dependent simulation algorithm that will be used to simulate evolution during the uniform interpolation schedule.</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="b5360-115">Output： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="b5360-115">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="b5360-116">备注</span><span class="sxs-lookup"><span data-stu-id="b5360-116">Remarks</span></span>

<span data-ttu-id="b5360-117">如果选择了内插时间以满足 adiabatic 条件，则此函数将返回一个操作，该操作将为最后一个 dynamical 生成器执行 adiabatic 状态准备。</span><span class="sxs-lookup"><span data-stu-id="b5360-117">If the interpolation time is chosen to meet the adiabatic conditions, then this function returns an operation which performs adiabatic state preparation for the final dynamical generator.</span></span>