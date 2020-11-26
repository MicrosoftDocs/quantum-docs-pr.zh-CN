---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: LeftShiftedL 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 00d4f9151c620e044074930933ea2912b52534ed
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219662"
---
# <a name="leftshiftedl-function"></a>LeftShiftedL 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Bitwise)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


将数字的按位表示形式向左移动给定的位数。

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a>输入

### <a name="value--bigint"></a>值： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

要向左移动 (更重要) 的按位表示形式的数字。


### <a name="amount--int"></a>金额： [Int](xref:microsoft.quantum.lang-ref.int)

要向左移动的位数 `value` 。



## <a name="output--bigint"></a>输出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

的值 `value` ，按位向左移动 `amount` 。

## <a name="remarks"></a>备注

以下项是等效的：

```Q#
let c = a <<< b;
let c = LeftShiftedL(a, b);
```