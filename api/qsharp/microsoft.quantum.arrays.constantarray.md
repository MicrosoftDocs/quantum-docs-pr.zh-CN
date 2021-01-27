---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: a3ad8a18856888a0ca6f9dd691242156b0c044d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846226"
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



## <a name="example"></a>示例

下面的代码创建一个具有3个布尔值的数组，每个数组等于 `true` ：

```qsharp
let array = ConstantArray(3, true);
```