---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 7ff80f13f432a18f216b2dee4bd65b1e82034fa5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696506"
---
# <a name="indexof-function"></a>IndexOf 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


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

