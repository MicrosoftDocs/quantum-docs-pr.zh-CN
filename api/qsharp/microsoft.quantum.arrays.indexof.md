---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 64db55e831078a7130a3ced6a30bfbd2299c392d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848522"
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



## <a name="example"></a>示例

假设 `IsEven : Int -> Bool` 是一个函数，该函数在 `true` 且仅当其输入为偶数时返回。 然后，可将其与一起用于 `IndexOf` 查找数组中的第一个偶数元素：

```qsharp
let items = [1, 3, 17, 2, 21];
let idx = IndexOf(IsEven, items); // returns 3
```