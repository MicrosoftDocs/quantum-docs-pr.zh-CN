---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: LeftShiftedL 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 17e5c845755f74e9703381bc82bfd63be836d038
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696416"
---
# <a name="leftshiftedl-function"></a>LeftShiftedL 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Bitwise)

软件包 [](https://nuget.org/packages/)


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

## <a name="remarks"></a>注解

以下项是等效的：

```Q#
let c = a <<< b;
let c = LeftShiftedL(a, b);
```