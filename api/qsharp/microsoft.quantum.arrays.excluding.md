---
uid: Microsoft.Quantum.Arrays.Excluding
title: 排除函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Excluding
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 8848c6e89da50efb4f7550168f1757b25a214a24
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696523"
---
# <a name="excluding-function"></a>排除函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


返回一个数组，其中包含另一个数组的元素，而不包括给定索引列表中的元素。

```qsharp
function Excluding<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a>输入

### <a name="remove--int"></a>删除： [Int](xref:microsoft.quantum.lang-ref.int)[]

指示应从输出中排除哪些元素的索引数组。


### <a name="array--t"></a>array： t []

输出数组中的值采用的数组。



## <a name="output--t"></a>输出： t []

一个数组， `output` 它 `output[0]` 是 `array` 其索引未出现在中的第一个元素 `remove` ，这 `output[1]` 是第二个这样的元素，依此类推。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

数组元素的类型。