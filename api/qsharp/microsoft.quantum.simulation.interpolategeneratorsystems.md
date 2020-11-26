---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystems
title: InterpolateGeneratorSystems 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystems
qsharp.summary: Returns a `TimeDependentGeneratorSystem` representing the linear interpolation between two `GeneratorSystem`s.
ms.openlocfilehash: ee47637996313fe1b77c76f00b08417dac956247
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230576"
---
# <a name="interpolategeneratorsystems-function"></a><span data-ttu-id="e240f-102">InterpolateGeneratorSystems 函数</span><span class="sxs-lookup"><span data-stu-id="e240f-102">InterpolateGeneratorSystems function</span></span>

<span data-ttu-id="e240f-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e240f-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e240f-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e240f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e240f-105">返回一个， `TimeDependentGeneratorSystem` 它表示两个之间的线性内插 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="e240f-105">Returns a `TimeDependentGeneratorSystem` representing the linear interpolation between two `GeneratorSystem`s.</span></span>

```qsharp
function InterpolateGeneratorSystems (generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
```


## <a name="input"></a><span data-ttu-id="e240f-106">输入</span><span class="sxs-lookup"><span data-stu-id="e240f-106">Input</span></span>

### <a name="generatorsystemstart--generatorsystem"></a><span data-ttu-id="e240f-107">generatorSystemStart： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="e240f-107">generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="e240f-108">开始 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="e240f-108">The start `GeneratorSystem`.</span></span>


### <a name="generatorsystemend--generatorsystem"></a><span data-ttu-id="e240f-109">generatorSystemEnd： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="e240f-109">generatorSystemEnd : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="e240f-110">结束 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="e240f-110">The end `GeneratorSystem`.</span></span>



## <a name="output--timedependentgeneratorsystem"></a><span data-ttu-id="e240f-111">输出： [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="e240f-111">Output : [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span></span>

<span data-ttu-id="e240f-112">一个， `TimeDependentGeneratorSystem` 它表示一个系统，该系统是输入生成器系统的总和，权重 $ (1-s) $ on， `generatorSystemStart` 权重 $s $ on `generatorSystemEnd` 。</span><span class="sxs-lookup"><span data-stu-id="e240f-112">A `TimeDependentGeneratorSystem` representing a system that is the sum of the input generator systems, with weight $(1-s)$ on `generatorSystemStart` and weight $s$ on `generatorSystemEnd`.</span></span>

## <a name="see-also"></a><span data-ttu-id="e240f-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e240f-113">See Also</span></span>

- [<span data-ttu-id="e240f-114">GeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="e240f-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)
- [<span data-ttu-id="e240f-115">TimeDependentGeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="e240f-115">Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)