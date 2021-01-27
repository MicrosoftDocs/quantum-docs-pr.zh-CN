---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 3f551bdba5c8e2a1456838769e4cee0660d0f969
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845308"
---
# <a name="leftshiftedi-function"></a>LeftShiftedI 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Bitwise)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="remarks"></a>备注

以下项是等效的：

```qsharp
let c = a <<< b;
let c = LeftShiftedI(a, b);
```