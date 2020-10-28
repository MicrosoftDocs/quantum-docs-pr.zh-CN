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
# <a name="generatorsystem-user-defined-type"></a>GeneratorSystem 用户定义的类型

命名空间 [：](xref:Microsoft.Quantum.Simulation)

软件包 [](https://nuget.org/packages/)


表示 es 的集合 `GeneratorIndex` 。

我们使用单个索引的整数来循环访问此集合，并假定集合的大小是已知的。

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a>注解

`GeneratorSystem`可以使用函数轻松定义的实例 <xref:microsoft.quantum.arrays.lookupfunction> 。

## <a name="see-also"></a>另请参阅

- [LookupFunction。](xref:Microsoft.Quantum.Arrays.LookupFunction)