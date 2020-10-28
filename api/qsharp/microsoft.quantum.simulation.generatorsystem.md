---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: GeneratorSystem 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: c03caf99b197410c7fa15021c8acaaf55a728781
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700877"
---
# <a name="generatorsystem-user-defined-type"></a><span data-ttu-id="7b163-102">GeneratorSystem 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="7b163-102">GeneratorSystem user defined type</span></span>

<span data-ttu-id="7b163-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="7b163-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="7b163-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7b163-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7b163-105">表示 es 的集合 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="7b163-105">Represents a collection of `GeneratorIndex`es.</span></span>

<span data-ttu-id="7b163-106">我们使用单个索引的整数来循环访问此集合，并假定集合的大小是已知的。</span><span class="sxs-lookup"><span data-stu-id="7b163-106">We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.</span></span>

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a><span data-ttu-id="7b163-107">注解</span><span class="sxs-lookup"><span data-stu-id="7b163-107">Remarks</span></span>

<span data-ttu-id="7b163-108">`GeneratorSystem`可以使用函数轻松定义的实例 <xref:microsoft.quantum.arrays.lookupfunction> 。</span><span class="sxs-lookup"><span data-stu-id="7b163-108">Instances of `GeneratorSystem` can be defined easily using the <xref:microsoft.quantum.arrays.lookupfunction> function.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b163-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b163-109">See Also</span></span>

- [<span data-ttu-id="7b163-110">LookupFunction。</span><span class="sxs-lookup"><span data-stu-id="7b163-110">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)