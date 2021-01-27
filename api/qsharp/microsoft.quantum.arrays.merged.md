---
uid: Microsoft.Quantum.Arrays.Merged
title: 合并函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: 262e7450188370212a7e2a57bf15e9f8ab162814
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845607"
---
# <a name="merged-function"></a>合并函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


给定两个已排序的数组，返回一个数组，其中包含按排序顺序排列的元素。 由合并排序在内部使用。

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a>输入

### <a name="comparison--tt---bool"></a>比较： ( 不) -> [Bool](xref:microsoft.quantum.lang-ref.bool)




### <a name="left--t"></a>left： t []




### <a name="right--t"></a>right： t []





## <a name="output--t"></a>输出： t []



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

