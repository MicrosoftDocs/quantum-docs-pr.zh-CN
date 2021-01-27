---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: cb1d4c471c528d2d3c08c92619fafd532a88c8f0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829202"
---
# <a name="equalityfactb-function"></a>EqualityFactB 函数

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


断言传统 Bool 变量具有预期值。

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a>输入

### <a name="actual--bool"></a>实际： [Bool](xref:microsoft.quantum.lang-ref.bool)

要检查的变量。


### <a name="expected--bool"></a>应为： [Bool](xref:microsoft.quantum.lang-ref.bool)

预期值。


### <a name="message--string"></a>消息： [字符串](xref:microsoft.quantum.lang-ref.string)

触发断言时要使用的失败消息字符串。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

