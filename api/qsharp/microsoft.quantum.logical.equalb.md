---
uid: Microsoft.Quantum.Logical.EqualB
title: EqualB 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualB
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 91ab51180018a9b95a2f9010477c0a24f3a54617
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699753"
---
# <a name="equalb-function"></a>EqualB 函数

命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)

软件包 [](https://nuget.org/packages/)


当且仅当两个输入相等时，返回 true。

```qsharp
function EqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>输入

### <a name="a--bool"></a>a： [Bool](xref:microsoft.quantum.lang-ref.bool)

要比较的第一个值。


### <a name="b--bool"></a>b： [Bool](xref:microsoft.quantum.lang-ref.bool)

要比较的第二个值。



## <a name="output--bool"></a>输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值

`true` 当且仅当 `a` 等于时 `b` 。

## <a name="remarks"></a>注解

以下项是等效的：

```Q#
let cond = a == b;
let cond = EqualB(a, b);
```