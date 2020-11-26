---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: RightShiftedL 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 3d941e1a0bcd96fe54ab01019293d883f11547a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219509"
---
# <a name="rightshiftedl-function"></a>RightShiftedL 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Bitwise)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


将数字的按位表示形式向右移位给定的位数。

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a>输入

### <a name="value--bigint"></a>值： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

要 (不太重要) 向右移动的按位表示形式的数字。


### <a name="amount--int"></a>金额： [Int](xref:microsoft.quantum.lang-ref.int)

要向右移动的位数 `value` 。



## <a name="output--bigint"></a>输出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

的值，右移一 `value` `amount` 位。

## <a name="remarks"></a>备注

以下项是等效的：

```Q#
let c = a >>> b;
let c = RightShiftedL(a, b);
```