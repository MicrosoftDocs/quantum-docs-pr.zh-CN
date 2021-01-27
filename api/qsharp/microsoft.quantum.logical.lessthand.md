---
uid: Microsoft.Quantum.Logical.LessThanD
title: LessThanD 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanD
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 7135ed4b3414d143f5020496ae524bf89980a8a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849162"
---
# <a name="lessthand-function"></a>LessThanD 函数

命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


当且仅当一个数字小于另一个数字时，返回 true。

```qsharp
function LessThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a>输入

### <a name="a--double"></a>答： [Double](xref:microsoft.quantum.lang-ref.double)

要比较的第一个值。


### <a name="b--double"></a>b： [Double](xref:microsoft.quantum.lang-ref.double)

要比较的第二个值。



## <a name="output--bool"></a>输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值

`true` 当且仅当 `a` 严格小于时 `b` 。

## <a name="remarks"></a>备注

以下项是等效的：

```qsharp
let cond = a < b;
let cond = LessThanD(a, b);
```