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
# <a name="generatorsystem-user-defined-type"></a>GeneratorSystem 用户定义的类型

命名空间 [：](xref:Microsoft.Quantum.Simulation)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


表示 es 的集合 `GeneratorIndex` 。

我们使用单个索引的整数来循环访问此集合，并假定集合的大小是已知的。

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a>备注

`GeneratorSystem`可以使用函数轻松定义的实例 <xref:microsoft.quantum.arrays.lookupfunction> 。

## <a name="see-also"></a>另请参阅

- [LookupFunction。](xref:Microsoft.Quantum.Arrays.LookupFunction)