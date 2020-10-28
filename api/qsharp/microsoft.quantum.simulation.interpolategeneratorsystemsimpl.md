---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystemsImpl
title: InterpolateGeneratorSystemsImpl 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystemsImpl
qsharp.summary: Linearly interpolates between two `GeneratorSystems` according to a schedule parameter `s` between 0 and 1 (inclusive).
ms.openlocfilehash: 212ed4c473fab3572f73ea250061057ad13e393f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695092"
---
# <a name="interpolategeneratorsystemsimpl-function"></a><span data-ttu-id="411ec-102">InterpolateGeneratorSystemsImpl 函数</span><span class="sxs-lookup"><span data-stu-id="411ec-102">InterpolateGeneratorSystemsImpl function</span></span>

<span data-ttu-id="411ec-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="411ec-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="411ec-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="411ec-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="411ec-105">`GeneratorSystems`根据计划参数 `s` （介于0和1之间），以线性方式在两个之间内插 (包含) 。</span><span class="sxs-lookup"><span data-stu-id="411ec-105">Linearly interpolates between two `GeneratorSystems` according to a schedule parameter `s` between 0 and 1 (inclusive).</span></span>

```qsharp
function InterpolateGeneratorSystemsImpl (schedule : Double, generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="411ec-106">输入</span><span class="sxs-lookup"><span data-stu-id="411ec-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="411ec-107">计划： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="411ec-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="411ec-108">Schedule 参数 $s \in [0，1] $。</span><span class="sxs-lookup"><span data-stu-id="411ec-108">A schedule parameter $s\in[0,1]$.</span></span>


### <a name="generatorsystemstart--generatorsystem"></a><span data-ttu-id="411ec-109">generatorSystemStart： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="411ec-109">generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="411ec-110">开始 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="411ec-110">The start `GeneratorSystem`.</span></span>


### <a name="generatorsystemend--generatorsystem"></a><span data-ttu-id="411ec-111">generatorSystemEnd： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="411ec-111">generatorSystemEnd : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="411ec-112">结束 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="411ec-112">The end `GeneratorSystem`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="411ec-113">输出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="411ec-113">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="411ec-114">一个， `GeneratorSystem` 它表示一个系统，该系统是输入生成器系统的总和，权重 $ (1-s) $ on， `generatorSystemStart` 权重 $s $ on `generatorSystemEnd` 。</span><span class="sxs-lookup"><span data-stu-id="411ec-114">A `GeneratorSystem` representing a system that is the sum of the input generator systems, with weight $(1-s)$ on `generatorSystemStart` and weight $s$ on `generatorSystemEnd`.</span></span>

## <a name="see-also"></a><span data-ttu-id="411ec-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="411ec-115">See Also</span></span>

- [<span data-ttu-id="411ec-116">GeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="411ec-116">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)