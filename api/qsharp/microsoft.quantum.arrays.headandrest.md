---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 9af4ba48a21d3cdf932b2f702051a70a6108db1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696507"
---
# <a name="headandrest-function"></a>HeadAndRest 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


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