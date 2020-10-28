---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: MultiplyGeneratorSystem 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: 1d28de99dab3f7aca4bf3706fe98f5ef7c5286a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696683"
---
# <a name="multiplygeneratorsystem-function"></a><span data-ttu-id="361a3-102">MultiplyGeneratorSystem 函数</span><span class="sxs-lookup"><span data-stu-id="361a3-102">MultiplyGeneratorSystem function</span></span>

<span data-ttu-id="361a3-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="361a3-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="361a3-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="361a3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="361a3-105">将中所有字词的系数相乘 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="361a3-105">Multiplies the coefficient of all terms in a `GeneratorSystem`.</span></span>

```qsharp
function MultiplyGeneratorSystem (multiplier : Double, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="361a3-106">输入</span><span class="sxs-lookup"><span data-stu-id="361a3-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="361a3-107">乘数： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="361a3-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="361a3-108">系数的乘数。</span><span class="sxs-lookup"><span data-stu-id="361a3-108">The multiplier on the coefficient.</span></span>


### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="361a3-109">generatorSystem： [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="361a3-109">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="361a3-110">作为被乘数的 `GeneratorSystem`。</span><span class="sxs-lookup"><span data-stu-id="361a3-110">The `GeneratorSystem` to be multiplied.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="361a3-111">输出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="361a3-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="361a3-112">， `GeneratorSystem` 它表示系数大于系数的系统 `multiplier` 。</span><span class="sxs-lookup"><span data-stu-id="361a3-112">A `GeneratorSystem` representing a system with coefficients a factor `multiplier` larger.</span></span>

## <a name="see-also"></a><span data-ttu-id="361a3-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="361a3-113">See Also</span></span>

- [<span data-ttu-id="361a3-114">GeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="361a3-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)