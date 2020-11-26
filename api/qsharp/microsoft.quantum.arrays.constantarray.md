---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 8cba68af2f1e178a1ef96921283f85e4feb498ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210057"
---
# <a name="constantarray-function"></a>ConstantArray 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


创建一个给定长度的数组，其中的所有元素都等于给定的值。

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a>输入

### <a name="length--int"></a>长度： [Int](xref:microsoft.quantum.lang-ref.int)

新数组的长度。


### <a name="value--t"></a>值： t

新数组的每个元素的值。



## <a name="output--t"></a>输出： t []

一个新的长度数组 `length` ，使每个元素都是 `value` 。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

