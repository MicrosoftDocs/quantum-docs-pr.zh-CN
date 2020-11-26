---
uid: Microsoft.Quantum.Arrays.Most
title: 大多数函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: 81e66e0b64ae8dfc44d163b68370ccadd191c729
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220597"
---
# <a name="most-function"></a>大多数函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


创建一个等于输入数组的数组，只不过最后一个数组元素被删除。

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>输入

### <a name="array--t"></a>array： t []

一个数组，其第一个到第二个元素是形成输出数组。



## <a name="output--t"></a>输出： t []

包含元素的数组 `array[0..Length(array) - 2]` 。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

数组元素的类型。