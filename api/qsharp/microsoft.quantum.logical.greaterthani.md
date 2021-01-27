---
uid: Microsoft.Quantum.Logical.GreaterThanI
title: GreaterThanI 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanI
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 86fc8e927c292a2ea814ed80a33de42bffdb96b1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815953"
---
# <a name="greaterthani-function"></a>GreaterThanI 函数

命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


当且仅当一个数字大于另一个数字时，返回 true。

```qsharp
function GreaterThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a>输入

### <a name="a--int"></a>a： [Int](xref:microsoft.quantum.lang-ref.int)

要比较的第一个值。


### <a name="b--int"></a>b： [Int](xref:microsoft.quantum.lang-ref.int)

要比较的第二个值。



## <a name="output--bool"></a>输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值

`true` 当且仅当 `a` 严格大于时 `b` 。

## <a name="remarks"></a>备注

以下项是等效的：

```qsharp
let cond = a > b;
let cond = GreaterThanI(a, b);
```