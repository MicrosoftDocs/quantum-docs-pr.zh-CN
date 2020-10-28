---
uid: Microsoft.Quantum.Arrays.Where
title: Where 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 1c9fa0463ed49788d12502257d735b965565d1ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696436"
---
# <a name="where-function"></a>Where 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


给定谓词和数组后，返回该数组的索引，其中谓词为 true。

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a>输入

### <a name="predicate--t---bool"></a>谓词：不 >[布尔](xref:microsoft.quantum.lang-ref.bool)值

从 `'T` 到用于筛选元素的布尔值的函数。


### <a name="array--t"></a>array： t []

上的元素的数组 `'T` 。



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)[]

一个索引数组，其中 `predicate` 为 true。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

元素的类型 `array` 。