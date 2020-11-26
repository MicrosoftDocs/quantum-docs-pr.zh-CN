---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: GeneratorSystem 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 20092a8deca50c90f46f4d79c6b40b805f135754
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225221"
---
# <a name="generatorsystem-user-defined-type"></a><span data-ttu-id="51f74-102">GeneratorSystem 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="51f74-102">GeneratorSystem user defined type</span></span>

<span data-ttu-id="51f74-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="51f74-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="51f74-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="51f74-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="51f74-105">表示 es 的集合 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="51f74-105">Represents a collection of `GeneratorIndex`es.</span></span>

<span data-ttu-id="51f74-106">我们使用单个索引的整数来循环访问此集合，并假定集合的大小是已知的。</span><span class="sxs-lookup"><span data-stu-id="51f74-106">We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.</span></span>

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a><span data-ttu-id="51f74-107">备注</span><span class="sxs-lookup"><span data-stu-id="51f74-107">Remarks</span></span>

<span data-ttu-id="51f74-108">`GeneratorSystem`可以使用函数轻松定义的实例 <xref:microsoft.quantum.arrays.lookupfunction> 。</span><span class="sxs-lookup"><span data-stu-id="51f74-108">Instances of `GeneratorSystem` can be defined easily using the <xref:microsoft.quantum.arrays.lookupfunction> function.</span></span>

## <a name="see-also"></a><span data-ttu-id="51f74-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51f74-109">See Also</span></span>

- [<span data-ttu-id="51f74-110">LookupFunction。</span><span class="sxs-lookup"><span data-stu-id="51f74-110">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)