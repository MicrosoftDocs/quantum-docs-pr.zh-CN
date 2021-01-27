---
uid: Microsoft.Quantum.Simulation.SumGeneratorSystems
title: SumGeneratorSystems 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SumGeneratorSystems
qsharp.summary: Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.
ms.openlocfilehash: 0e64d2b599c55c19711208670030fd01e09aff7e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851025"
---
# <a name="sumgeneratorsystems-function"></a><span data-ttu-id="2b59b-102">SumGeneratorSystems 函数</span><span class="sxs-lookup"><span data-stu-id="2b59b-102">SumGeneratorSystems function</span></span>

<span data-ttu-id="2b59b-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="2b59b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="2b59b-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2b59b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2b59b-105">添加多个 `GeneratorSystem` 创建新 GeneratorSystem 的。</span><span class="sxs-lookup"><span data-stu-id="2b59b-105">Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.</span></span>

```qsharp
function SumGeneratorSystems (generatorSystems : Microsoft.Quantum.Simulation.GeneratorSystem[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="2b59b-106">输入</span><span class="sxs-lookup"><span data-stu-id="2b59b-106">Input</span></span>

### <a name="generatorsystems--generatorsystem"></a><span data-ttu-id="2b59b-107">generatorSystems： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span><span class="sxs-lookup"><span data-stu-id="2b59b-107">generatorSystems : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span></span>

<span data-ttu-id="2b59b-108">`GeneratorSystem[]` 类型的数组。</span><span class="sxs-lookup"><span data-stu-id="2b59b-108">An array of type `GeneratorSystem[]`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="2b59b-109">输出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="2b59b-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="2b59b-110">一个， `GeneratorSystem` 它表示作为输入生成器系统的总和的系统。</span><span class="sxs-lookup"><span data-stu-id="2b59b-110">A `GeneratorSystem` representing a system that is the sum of the input generator systems.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b59b-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b59b-111">See Also</span></span>

- [<span data-ttu-id="2b59b-112">GeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="2b59b-112">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)