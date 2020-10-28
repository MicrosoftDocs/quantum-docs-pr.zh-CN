---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 8786250cf2f78ce2e9ff8baddc856d0bc07cb9a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696476"
---
# <a name="mostandtail-function"></a>MostAndTail 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


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