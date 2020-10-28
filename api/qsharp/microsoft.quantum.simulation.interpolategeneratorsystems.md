---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystems
title: InterpolateGeneratorSystems 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystems
qsharp.summary: Returns a `TimeDependentGeneratorSystem` representing the linear interpolation between two `GeneratorSystem`s.
ms.openlocfilehash: 9881c27577023dafff0bfc6d961877db44fec0eb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695253"
---
# <a name="interpolategeneratorsystems-function"></a><span data-ttu-id="2b003-102">InterpolateGeneratorSystems 函数</span><span class="sxs-lookup"><span data-stu-id="2b003-102">InterpolateGeneratorSystems function</span></span>

<span data-ttu-id="2b003-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="2b003-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="2b003-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2b003-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2b003-105">返回一个， `TimeDependentGeneratorSystem` 它表示两个之间的线性内插 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="2b003-105">Returns a `TimeDependentGeneratorSystem` representing the linear interpolation between two `GeneratorSystem`s.</span></span>

```qsharp
function InterpolateGeneratorSystems (generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
```


## <a name="input"></a><span data-ttu-id="2b003-106">输入</span><span class="sxs-lookup"><span data-stu-id="2b003-106">Input</span></span>

### <a name="generatorsystemstart--generatorsystem"></a><span data-ttu-id="2b003-107">generatorSystemStart： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="2b003-107">generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="2b003-108">开始 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="2b003-108">The start `GeneratorSystem`.</span></span>


### <a name="generatorsystemend--generatorsystem"></a><span data-ttu-id="2b003-109">generatorSystemEnd： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="2b003-109">generatorSystemEnd : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="2b003-110">结束 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="2b003-110">The end `GeneratorSystem`.</span></span>



## <a name="output--timedependentgeneratorsystem"></a><span data-ttu-id="2b003-111">输出： [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="2b003-111">Output : [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span></span>

<span data-ttu-id="2b003-112">一个， `TimeDependentGeneratorSystem` 它表示一个系统，该系统是输入生成器系统的总和，权重 $ (1-s) $ on， `generatorSystemStart` 权重 $s $ on `generatorSystemEnd` 。</span><span class="sxs-lookup"><span data-stu-id="2b003-112">A `TimeDependentGeneratorSystem` representing a system that is the sum of the input generator systems, with weight $(1-s)$ on `generatorSystemStart` and weight $s$ on `generatorSystemEnd`.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b003-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b003-113">See Also</span></span>

- [<span data-ttu-id="2b003-114">GeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="2b003-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)
- [<span data-ttu-id="2b003-115">TimeDependentGeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="2b003-115">Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)