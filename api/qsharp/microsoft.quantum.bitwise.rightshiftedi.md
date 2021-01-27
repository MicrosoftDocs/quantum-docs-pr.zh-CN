---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 5c3106eb73178554184cbfb37333c027805c69f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845258"
---
# <a name="rightshiftedi-function"></a>RightShiftedI 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Bitwise)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


将数字的按位表示形式向右移位给定的位数。

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a>输入

### <a name="value--int"></a>值： [Int](xref:microsoft.quantum.lang-ref.int)

要 (不太重要) 向右移动的按位表示形式的数字。


### <a name="amount--int"></a>金额： [Int](xref:microsoft.quantum.lang-ref.int)

要向右移动的位数 `value` 。



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

的值，右移一 `value` `amount` 位。

## <a name="remarks"></a>备注

以下项是等效的：

```qsharp
let c = a >>> b;
let c = RightShiftedI(a, b);
```