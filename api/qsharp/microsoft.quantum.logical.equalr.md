---
uid: Microsoft.Quantum.Logical.EqualR
title: EqualR 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: d68b2f1a26bf318400d3c88b37d9aabcc38cbdfe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197999"
---
# <a name="equalr-function"></a>EqualR 函数

命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


当且仅当两个输入相等时，返回 true。

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a>输入

### <a name="a--__invalidresult__"></a>答：__无效 <Result>__

要比较的第一个值。


### <a name="b--__invalidresult__"></a>b：__无效 <Result>__

要比较的第二个值。



## <a name="output--bool"></a>输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值

`true` 当且仅当 `a` 等于时 `b` 。

## <a name="remarks"></a>备注

以下项是等效的：

```Q#
let cond = a == b;
let cond = EqualR(a, b);
```