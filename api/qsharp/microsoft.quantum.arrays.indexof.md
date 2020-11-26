---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: d63b204334611f8f2c3860f9ee1d756f637780e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221005"
---
# <a name="indexof-function"></a>IndexOf 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回满足给定谓词的数组中第一个元素的第一个索引。 如果此类元素不存在，则返回-1。

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a>输入

### <a name="predicate--t---bool"></a>谓词：不 >[布尔](xref:microsoft.quantum.lang-ref.bool)值

一个谓词函数，该函数对数组的元素进行操作。


### <a name="arr--t"></a>arr： t []

要使用给定谓词搜索的数组。



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

最小索引 `idx` （例如 `predicate(arr[idx])` true），如果不存在此类元素，则为-1。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

