---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 06615c7ffb6aafc296077990dfca0ce25e1e00fa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695143"
---
# <a name="notequalr-function"></a>NotEqualR 函数

命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)

软件包 [](https://nuget.org/packages/)


当且仅当两个输入不相等时，返回 true。

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a>输入

### <a name="a--__invalidresult__"></a>答： __无效 <Result>__

要比较的第一个值。


### <a name="b--__invalidresult__"></a>b： __无效 <Result>__

要比较的第二个值。



## <a name="output--bool"></a>输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值

`true` 当且仅当不 `a` 等于时 `b` 。

## <a name="remarks"></a>注解

以下项是等效的：

```Q#
let cond = a != b;
let cond = NotEqualR(a, b);
```