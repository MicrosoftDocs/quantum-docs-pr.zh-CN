---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 392efb20e4aaba80a77664444bb415d8bc9b0930
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220563"
---
# <a name="mostandtail-function"></a>MostAndTail 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回数组的所有元素，而不是数组的最后一个元素。

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a>输入

### <a name="array--a"></a>array： ' A []

包含至少一个元素的数组。



## <a name="output--aa"></a>输出： ( ' A []，' A) 

除数组的一个和最后一个元素之外的所有元素的元组。

## <a name="type-parameters"></a>类型参数

### <a name="a"></a>' A

数组元素的类型。