---
uid: Microsoft.Quantum.Logical.GreaterThanD
title: GreaterThanD 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanD
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: c23d85cf513bb6d37e67260eeeb3b81b42e6771a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198021"
---
# <a name="greaterthand-function"></a>GreaterThanD 函数

命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


当且仅当一个数字大于另一个数字时，返回 true。

```qsharp
function GreaterThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a>输入

### <a name="a--double"></a>答： [Double](xref:microsoft.quantum.lang-ref.double)

要比较的第一个值。


### <a name="b--double"></a>b： [Double](xref:microsoft.quantum.lang-ref.double)

要比较的第二个值。



## <a name="output--bool"></a>输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值

`true` 当且仅当 `a` 严格大于时 `b` 。

## <a name="remarks"></a>备注

以下项是等效的：

```Q#
let cond = a > b;
let cond = GreaterThanD(a, b);
```