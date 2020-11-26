---
uid: Microsoft.Quantum.Simulation.AddGeneratorSystems
title: AddGeneratorSystems 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: AddGeneratorSystems
qsharp.summary: Adds two `GeneratorSystem`s to create a new `GeneratorSystem`.
ms.openlocfilehash: d6e8f7085cf0558960d055dbeeb08740c3fab049
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229658"
---
# <a name="addgeneratorsystems-function"></a><span data-ttu-id="6ff0b-102">AddGeneratorSystems 函数</span><span class="sxs-lookup"><span data-stu-id="6ff0b-102">AddGeneratorSystems function</span></span>

<span data-ttu-id="6ff0b-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="6ff0b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="6ff0b-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6ff0b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6ff0b-105">添加两个 `GeneratorSystem` 以创建新的 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="6ff0b-105">Adds two `GeneratorSystem`s to create a new `GeneratorSystem`.</span></span>

```qsharp
function AddGeneratorSystems (generatorSystemA : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemB : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="6ff0b-106">输入</span><span class="sxs-lookup"><span data-stu-id="6ff0b-106">Input</span></span>

### <a name="generatorsystema--generatorsystem"></a><span data-ttu-id="6ff0b-107">generatorSystemA： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="6ff0b-107">generatorSystemA : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="6ff0b-108">第一个 `GeneratorSystem`。</span><span class="sxs-lookup"><span data-stu-id="6ff0b-108">The first `GeneratorSystem`.</span></span>


### <a name="generatorsystemb--generatorsystem"></a><span data-ttu-id="6ff0b-109">generatorSystemB： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="6ff0b-109">generatorSystemB : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="6ff0b-110">第二个 `GeneratorSystem`。</span><span class="sxs-lookup"><span data-stu-id="6ff0b-110">The second `GeneratorSystem`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="6ff0b-111">输出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="6ff0b-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="6ff0b-112">一个， `GeneratorSystem` 它表示作为输入生成器系统的总和的系统。</span><span class="sxs-lookup"><span data-stu-id="6ff0b-112">A `GeneratorSystem` representing a system that is the sum of the input generator systems.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ff0b-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ff0b-113">See Also</span></span>

- [<span data-ttu-id="6ff0b-114">GeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="6ff0b-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)