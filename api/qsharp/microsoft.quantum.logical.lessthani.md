---
uid: Microsoft.Quantum.Logical.LessThanI
title: LessThanI 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanI
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 5d5b17c8481ccf58b8e4fc4bb958e0adbf6d8f00
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197766"
---
# <a name="lessthani-function"></a>LessThanI 函数

命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


当且仅当一个数字小于另一个数字时，返回 true。

```qsharp
function LessThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a>输入

### <a name="a--int"></a>a： [Int](xref:microsoft.quantum.lang-ref.int)

要比较的第一个值。


### <a name="b--int"></a>b： [Int](xref:microsoft.quantum.lang-ref.int)

要比较的第二个值。



## <a name="output--bool"></a>输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值

`true` 当且仅当 `a` 严格小于时 `b` 。

## <a name="remarks"></a>备注

以下项是等效的：

```Q#
let cond = a < b;
let cond = LessThanI(a, b);
```