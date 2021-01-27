---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: GeneratorSystem 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 3748d3fb79597fb526c86a91bc28290155189014
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858409"
---
# <a name="generatorsystem-user-defined-type"></a><span data-ttu-id="a6866-102">GeneratorSystem 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="a6866-102">GeneratorSystem user defined type</span></span>

<span data-ttu-id="a6866-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="a6866-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="a6866-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a6866-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a6866-105">表示 es 的集合 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="a6866-105">Represents a collection of `GeneratorIndex`es.</span></span>

<span data-ttu-id="a6866-106">我们使用单个索引的整数来循环访问此集合，并假定集合的大小是已知的。</span><span class="sxs-lookup"><span data-stu-id="a6866-106">We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.</span></span>

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a><span data-ttu-id="a6866-107">备注</span><span class="sxs-lookup"><span data-stu-id="a6866-107">Remarks</span></span>

<span data-ttu-id="a6866-108">`GeneratorSystem`可以使用函数轻松定义的实例 <xref:microsoft.quantum.arrays.lookupfunction> 。</span><span class="sxs-lookup"><span data-stu-id="a6866-108">Instances of `GeneratorSystem` can be defined easily using the <xref:microsoft.quantum.arrays.lookupfunction> function.</span></span>

## <a name="see-also"></a><span data-ttu-id="a6866-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6866-109">See Also</span></span>

- [<span data-ttu-id="a6866-110">LookupFunction。</span><span class="sxs-lookup"><span data-stu-id="a6866-110">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)