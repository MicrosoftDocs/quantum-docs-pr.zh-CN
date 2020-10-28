---
uid: Microsoft.Quantum.Arrays.ElementsAt
title: ElementsAt 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ElementsAt
qsharp.summary: Returns the array's elements at a given range of indices.
ms.openlocfilehash: b4bbba4dc83c4f9b89cdcb8ec32769f1c586357e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696534"
---
# <a name="elementsat-function"></a>ElementsAt 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


返回给定索引范围内的数组元素。

```qsharp
function ElementsAt<'T> (range : Range, array : 'T[]) : 'T[]
```


## <a name="input"></a>输入

### <a name="range--range"></a>范围： [范围](xref:microsoft.quantum.lang-ref.range)

数组索引范围


### <a name="array--t"></a>array： t []

Array



## <a name="output--t"></a>输出： t []



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

的每个元素的类型 `array` 。

## <a name="see-also"></a>另请参阅

- [.Value.elementat。](xref:Microsoft.Quantum.Arrays.ElementAt)
- [LookupFunction。](xref:Microsoft.Quantum.Arrays.LookupFunction)