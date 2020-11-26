---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 1144e00227df1cd7d96bc76b118b0b556adbaa96
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221073"
---
# <a name="headandrest-function"></a>HeadAndRest 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回数组的第一个和所有剩余元素的元组。

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a>输入

### <a name="array--a"></a>array： ' A []

包含至少一个元素的数组。



## <a name="output--aa"></a>Output： ( ' A，' A [] ) 

数组的第一个和所有剩余元素的元组。

## <a name="type-parameters"></a>类型参数

### <a name="a"></a>' A

数组元素的类型。