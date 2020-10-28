---
uid: Microsoft.Quantum.Arrays.Merged
title: 合并函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: da15a36f8f057cdc15062c96070ec21becc4794a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696479"
---
# <a name="merged-function"></a>合并函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


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

