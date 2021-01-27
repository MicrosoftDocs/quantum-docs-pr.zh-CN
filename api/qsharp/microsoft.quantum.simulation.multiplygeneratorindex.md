---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorIndex
title: MultiplyGeneratorIndex 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorIndex
qsharp.summary: Multiplies the coefficient in a `GeneratorIndex`.
ms.openlocfilehash: b53a483a0c2b8c99b733c9c87289fb212b5ffc89
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848030"
---
# <a name="multiplygeneratorindex-function"></a><span data-ttu-id="bd33e-102">MultiplyGeneratorIndex 函数</span><span class="sxs-lookup"><span data-stu-id="bd33e-102">MultiplyGeneratorIndex function</span></span>

<span data-ttu-id="bd33e-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="bd33e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="bd33e-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bd33e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bd33e-105">将中的系数相乘 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="bd33e-105">Multiplies the coefficient in a `GeneratorIndex`.</span></span>

```qsharp
function MultiplyGeneratorIndex (multiplier : Double, generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="bd33e-106">输入</span><span class="sxs-lookup"><span data-stu-id="bd33e-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="bd33e-107">乘数： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bd33e-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="bd33e-108">系数的乘数。</span><span class="sxs-lookup"><span data-stu-id="bd33e-108">The multiplier on the coefficient.</span></span>


### <a name="generatorindex--generatorindex"></a><span data-ttu-id="bd33e-109">generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="bd33e-109">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="bd33e-110">作为被乘数的 `GeneratorIndex`。</span><span class="sxs-lookup"><span data-stu-id="bd33e-110">The `GeneratorIndex` to be multiplied.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="bd33e-111">输出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="bd33e-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="bd33e-112">一个， `GeneratorIndex` 它表示一个系数大于系数的字词 `multiplier` 。</span><span class="sxs-lookup"><span data-stu-id="bd33e-112">A `GeneratorIndex` representing a term with coefficient a factor `multiplier` larger.</span></span>

## <a name="example"></a><span data-ttu-id="bd33e-113">示例</span><span class="sxs-lookup"><span data-stu-id="bd33e-113">Example</span></span>

```qsharp
let gen = GeneratorIndex(([1,2,3],[coeff]),[1,2,3]);
let ((idxPaulis, idxDoubles), idxQubits) = MultiplyGeneratorIndex(multiplier, gen);
// idxDoubles[0] == multiplier * coeff;
```

## <a name="see-also"></a><span data-ttu-id="bd33e-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd33e-114">See Also</span></span>

- [<span data-ttu-id="bd33e-115">GeneratorIndex。</span><span class="sxs-lookup"><span data-stu-id="bd33e-115">Microsoft.Quantum.Simulation.GeneratorIndex</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorIndex)