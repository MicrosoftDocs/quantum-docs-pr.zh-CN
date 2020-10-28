---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 848f18944829d08a10ec602dcb5d99c100c81f76
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696546"
---
# <a name="constantarray-function"></a>ConstantArray 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


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

