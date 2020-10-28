---
uid: Microsoft.Quantum.Logical.EqualCP
title: EqualCP 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualCP
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: c8ee7e6a04cc2478f1c97fcc1d964a1574f7b1fa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699745"
---
# <a name="equalcp-function"></a>EqualCP 函数

命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)

软件包 [](https://nuget.org/packages/)


当且仅当两个输入相等时，返回 true。

```qsharp
function EqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a>输入

### <a name="a--complexpolar"></a>答： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

要比较的第一个值。


### <a name="b--complexpolar"></a>b： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

要比较的第二个值。



## <a name="output--bool"></a>输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值

`true` 当且仅当 `a` 等于时 `b` 。