---
uid: Microsoft.Quantum.Simulation.GetGeneratorSystemFunction
title: GetGeneratorSystemFunction 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GetGeneratorSystemFunction
qsharp.summary: Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.
ms.openlocfilehash: 60ebbdbd1020d41a54426377043fc0c84ceec504
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700876"
---
# <a name="getgeneratorsystemfunction-function"></a><span data-ttu-id="c3d6b-102">GetGeneratorSystemFunction 函数</span><span class="sxs-lookup"><span data-stu-id="c3d6b-102">GetGeneratorSystemFunction function</span></span>

<span data-ttu-id="c3d6b-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c3d6b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c3d6b-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c3d6b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c3d6b-105">检索 `GeneratorIndex` 中的函数 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="c3d6b-105">Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.</span></span>

```qsharp
function GetGeneratorSystemFunction (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex)
```


## <a name="input"></a><span data-ttu-id="c3d6b-106">输入</span><span class="sxs-lookup"><span data-stu-id="c3d6b-106">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="c3d6b-107">generatorSystem： [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="c3d6b-107">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="c3d6b-108">有关的 `GeneratorSystem`。</span><span class="sxs-lookup"><span data-stu-id="c3d6b-108">The `GeneratorSystem` of interest.</span></span>



## <a name="output--int---generatorindex"></a><span data-ttu-id="c3d6b-109">输出： [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="c3d6b-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="c3d6b-110">用于对 Hamiltonian 中的每个字词进行索引的函数 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="c3d6b-110">An function that indexes each `GeneratorIndex` term in a Hamiltonian.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3d6b-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3d6b-111">See Also</span></span>

- [<span data-ttu-id="c3d6b-112">GeneratorIndex。</span><span class="sxs-lookup"><span data-stu-id="c3d6b-112">Microsoft.Quantum.Simulation.GeneratorIndex</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorIndex)
- [<span data-ttu-id="c3d6b-113">GeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="c3d6b-113">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)