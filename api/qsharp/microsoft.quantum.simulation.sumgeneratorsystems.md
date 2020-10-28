---
uid: Microsoft.Quantum.Simulation.SumGeneratorSystems
title: SumGeneratorSystems 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SumGeneratorSystems
qsharp.summary: Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.
ms.openlocfilehash: b667a6af313b5bb8950a34a6d0406976bde49311
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696624"
---
# <a name="sumgeneratorsystems-function"></a><span data-ttu-id="8ce47-102">SumGeneratorSystems 函数</span><span class="sxs-lookup"><span data-stu-id="8ce47-102">SumGeneratorSystems function</span></span>

<span data-ttu-id="8ce47-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="8ce47-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="8ce47-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8ce47-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8ce47-105">添加多个 `GeneratorSystem` 创建新 GeneratorSystem 的。</span><span class="sxs-lookup"><span data-stu-id="8ce47-105">Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.</span></span>

```qsharp
function SumGeneratorSystems (generatorSystems : Microsoft.Quantum.Simulation.GeneratorSystem[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="8ce47-106">输入</span><span class="sxs-lookup"><span data-stu-id="8ce47-106">Input</span></span>

### <a name="generatorsystems--generatorsystem"></a><span data-ttu-id="8ce47-107">generatorSystems： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span><span class="sxs-lookup"><span data-stu-id="8ce47-107">generatorSystems : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span></span>

<span data-ttu-id="8ce47-108">`GeneratorSystem[]` 类型的数组。</span><span class="sxs-lookup"><span data-stu-id="8ce47-108">An array of type `GeneratorSystem[]`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="8ce47-109">输出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="8ce47-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="8ce47-110">一个， `GeneratorSystem` 它表示作为输入生成器系统的总和的系统。</span><span class="sxs-lookup"><span data-stu-id="8ce47-110">A `GeneratorSystem` representing a system that is the sum of the input generator systems.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ce47-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8ce47-111">See Also</span></span>

- [<span data-ttu-id="8ce47-112">GeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="8ce47-112">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)