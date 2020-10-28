---
uid: Microsoft.Quantum.Arrays.Most
title: 大多数函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: ca89041a4e70472e9bf7a63ffcacccb35aad527c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696477"
---
# <a name="most-function"></a>大多数函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


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