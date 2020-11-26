---
uid: Microsoft.Quantum.Simulation.SumGeneratorSystems
title: SumGeneratorSystems 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SumGeneratorSystems
qsharp.summary: Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.
ms.openlocfilehash: 7cb18e161dce3a52d7c9a0bf6a45d4818db2b849
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192462"
---
# <a name="sumgeneratorsystems-function"></a><span data-ttu-id="8e42e-102">SumGeneratorSystems 函数</span><span class="sxs-lookup"><span data-stu-id="8e42e-102">SumGeneratorSystems function</span></span>

<span data-ttu-id="8e42e-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="8e42e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="8e42e-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8e42e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8e42e-105">添加多个 `GeneratorSystem` 创建新 GeneratorSystem 的。</span><span class="sxs-lookup"><span data-stu-id="8e42e-105">Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.</span></span>

```qsharp
function SumGeneratorSystems (generatorSystems : Microsoft.Quantum.Simulation.GeneratorSystem[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="8e42e-106">输入</span><span class="sxs-lookup"><span data-stu-id="8e42e-106">Input</span></span>

### <a name="generatorsystems--generatorsystem"></a><span data-ttu-id="8e42e-107">generatorSystems： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span><span class="sxs-lookup"><span data-stu-id="8e42e-107">generatorSystems : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span></span>

<span data-ttu-id="8e42e-108">`GeneratorSystem[]` 类型的数组。</span><span class="sxs-lookup"><span data-stu-id="8e42e-108">An array of type `GeneratorSystem[]`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="8e42e-109">输出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="8e42e-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="8e42e-110">一个， `GeneratorSystem` 它表示作为输入生成器系统的总和的系统。</span><span class="sxs-lookup"><span data-stu-id="8e42e-110">A `GeneratorSystem` representing a system that is the sum of the input generator systems.</span></span>

## <a name="see-also"></a><span data-ttu-id="8e42e-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e42e-111">See Also</span></span>

- [<span data-ttu-id="8e42e-112">GeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="8e42e-112">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)