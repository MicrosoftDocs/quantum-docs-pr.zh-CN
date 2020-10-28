---
uid: Microsoft.Quantum.Simulation.AddGeneratorSystems
title: AddGeneratorSystems 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: AddGeneratorSystems
qsharp.summary: Adds two `GeneratorSystem`s to create a new `GeneratorSystem`.
ms.openlocfilehash: 494037aa7635cccf25978bea9339ecc7aee75142
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695264"
---
# <a name="addgeneratorsystems-function"></a><span data-ttu-id="785c7-102">AddGeneratorSystems 函数</span><span class="sxs-lookup"><span data-stu-id="785c7-102">AddGeneratorSystems function</span></span>

<span data-ttu-id="785c7-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="785c7-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="785c7-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="785c7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="785c7-105">添加两个 `GeneratorSystem` 以创建新的 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="785c7-105">Adds two `GeneratorSystem`s to create a new `GeneratorSystem`.</span></span>

```qsharp
function AddGeneratorSystems (generatorSystemA : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemB : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="785c7-106">输入</span><span class="sxs-lookup"><span data-stu-id="785c7-106">Input</span></span>

### <a name="generatorsystema--generatorsystem"></a><span data-ttu-id="785c7-107">generatorSystemA： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="785c7-107">generatorSystemA : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="785c7-108">第一个 `GeneratorSystem`。</span><span class="sxs-lookup"><span data-stu-id="785c7-108">The first `GeneratorSystem`.</span></span>


### <a name="generatorsystemb--generatorsystem"></a><span data-ttu-id="785c7-109">generatorSystemB： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="785c7-109">generatorSystemB : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="785c7-110">第二个 `GeneratorSystem`。</span><span class="sxs-lookup"><span data-stu-id="785c7-110">The second `GeneratorSystem`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="785c7-111">输出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="785c7-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="785c7-112">一个， `GeneratorSystem` 它表示作为输入生成器系统的总和的系统。</span><span class="sxs-lookup"><span data-stu-id="785c7-112">A `GeneratorSystem` representing a system that is the sum of the input generator systems.</span></span>

## <a name="see-also"></a><span data-ttu-id="785c7-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="785c7-113">See Also</span></span>

- [<span data-ttu-id="785c7-114">GeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="785c7-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)