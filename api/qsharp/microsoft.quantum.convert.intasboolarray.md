---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 8b3d230605cc756a5da01e45e47f91c5b8e9f541
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833308"
---
# <a name="intasboolarray-function"></a>IntAsBoolArray 函数

命名空间 [：](xref:Microsoft.Quantum.Convert)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


使用返回的数组的小字节序表示形式，生成非负整数的二进制表示形式。

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a>输入

### <a name="number--int"></a>number： [Int](xref:microsoft.quantum.lang-ref.int)

要转换为布尔值数组的非负整数。


### <a name="bits--int"></a>bits： [Int](xref:microsoft.quantum.lang-ref.int)

的二进制表示形式的位数 `number` 。



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)[]

表示的布尔值数组 `number` 。

## <a name="remarks"></a>备注

输入 `bits` 必须介于0到63之间。
输入 `number` 必须介于0到 $ 2 ^ {\texttt{bits}}-$1 之间。