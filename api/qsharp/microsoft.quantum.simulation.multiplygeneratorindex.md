---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorIndex
title: MultiplyGeneratorIndex 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorIndex
qsharp.summary: Multiplies the coefficient in a `GeneratorIndex`.
ms.openlocfilehash: 9ee0568073b65b027cc98eb56934e9286b59c27f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700857"
---
# <a name="multiplygeneratorindex-function"></a><span data-ttu-id="69148-102">MultiplyGeneratorIndex 函数</span><span class="sxs-lookup"><span data-stu-id="69148-102">MultiplyGeneratorIndex function</span></span>

<span data-ttu-id="69148-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="69148-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="69148-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="69148-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="69148-105">将中的系数相乘 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="69148-105">Multiplies the coefficient in a `GeneratorIndex`.</span></span>

```qsharp
function MultiplyGeneratorIndex (multiplier : Double, generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="69148-106">输入</span><span class="sxs-lookup"><span data-stu-id="69148-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="69148-107">乘数： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="69148-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="69148-108">系数的乘数。</span><span class="sxs-lookup"><span data-stu-id="69148-108">The multiplier on the coefficient.</span></span>


### <a name="generatorindex--generatorindex"></a><span data-ttu-id="69148-109">generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="69148-109">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="69148-110">作为被乘数的 `GeneratorIndex`。</span><span class="sxs-lookup"><span data-stu-id="69148-110">The `GeneratorIndex` to be multiplied.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="69148-111">输出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="69148-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="69148-112">一个， `GeneratorIndex` 它表示一个系数大于系数的字词 `multiplier` 。</span><span class="sxs-lookup"><span data-stu-id="69148-112">A `GeneratorIndex` representing a term with coefficient a factor `multiplier` larger.</span></span>

## <a name="see-also"></a><span data-ttu-id="69148-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69148-113">See Also</span></span>

- [<span data-ttu-id="69148-114">GeneratorIndex。</span><span class="sxs-lookup"><span data-stu-id="69148-114">Microsoft.Quantum.Simulation.GeneratorIndex</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorIndex)