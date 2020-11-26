---
uid: Microsoft.Quantum.Arrays.Chunks
title: 区块函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: b323fdab1b207c72a4f46d5ca4cb368ecf0df818
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221600"
---
# <a name="chunks-function"></a>区块函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


将数组拆分为长度相等的多个部分。

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a>输入

### <a name="nelements--int"></a>nElements： [Int](xref:microsoft.quantum.lang-ref.int)

每个区块的长度。


### <a name="arr--t"></a>arr： t []

要拆分的数组。



## <a name="output--t"></a>输出： t [] []

包含原始数组的每个块的数组。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找



## <a name="remarks"></a>备注

请注意，输出的最后一个元素可能比不能被整除的更短 `nElements` `Length(arr)` `nElements` 。