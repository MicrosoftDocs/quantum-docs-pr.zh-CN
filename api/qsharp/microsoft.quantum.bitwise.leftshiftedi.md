---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: ce68311adf211169c2fb499bb189332370a6d6ac
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696421"
---
# <a name="leftshiftedi-function"></a>LeftShiftedI 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Bitwise)

软件包 [](https://nuget.org/packages/)


将数字的按位表示形式向左移动给定的位数。

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a>输入

### <a name="value--int"></a>值： [Int](xref:microsoft.quantum.lang-ref.int)

要向左移动 (更重要) 的按位表示形式的数字。


### <a name="amount--int"></a>金额： [Int](xref:microsoft.quantum.lang-ref.int)

要向左移动的位数 `value` 。



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

的值 `value` ，按位向左移动 `amount` 。

## <a name="remarks"></a>注解

以下项是等效的：

```Q#
let c = a <<< b;
let c = LeftShiftedI(a, b);
```