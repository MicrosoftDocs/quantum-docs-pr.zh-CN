---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: fd5569f1b71ac2fdf2b5c08ba7dde172e3a6744e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845592"
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