---
uid: Microsoft.Quantum.Simulation.GetGeneratorSystemFunction
title: GetGeneratorSystemFunction 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GetGeneratorSystemFunction
qsharp.summary: Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.
ms.openlocfilehash: 28e3c12d0ae0b08fc368c25eeb6f38d2834ca912
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229301"
---
# <a name="getgeneratorsystemfunction-function"></a><span data-ttu-id="3d7b9-102">GetGeneratorSystemFunction 函数</span><span class="sxs-lookup"><span data-stu-id="3d7b9-102">GetGeneratorSystemFunction function</span></span>

<span data-ttu-id="3d7b9-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="3d7b9-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="3d7b9-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3d7b9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3d7b9-105">检索 `GeneratorIndex` 中的函数 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="3d7b9-105">Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.</span></span>

```qsharp
function GetGeneratorSystemFunction (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex)
```


## <a name="input"></a><span data-ttu-id="3d7b9-106">输入</span><span class="sxs-lookup"><span data-stu-id="3d7b9-106">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="3d7b9-107">generatorSystem： [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="3d7b9-107">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="3d7b9-108">有关的 `GeneratorSystem`。</span><span class="sxs-lookup"><span data-stu-id="3d7b9-108">The `GeneratorSystem` of interest.</span></span>



## <a name="output--int---generatorindex"></a><span data-ttu-id="3d7b9-109">输出： [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="3d7b9-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="3d7b9-110">用于对 Hamiltonian 中的每个字词进行索引的函数 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="3d7b9-110">An function that indexes each `GeneratorIndex` term in a Hamiltonian.</span></span>

## <a name="see-also"></a><span data-ttu-id="3d7b9-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3d7b9-111">See Also</span></span>

- [<span data-ttu-id="3d7b9-112">GeneratorIndex。</span><span class="sxs-lookup"><span data-stu-id="3d7b9-112">Microsoft.Quantum.Simulation.GeneratorIndex</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorIndex)
- [<span data-ttu-id="3d7b9-113">GeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="3d7b9-113">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)