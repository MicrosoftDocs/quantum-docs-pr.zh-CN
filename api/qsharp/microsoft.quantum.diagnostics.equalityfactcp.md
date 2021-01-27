---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: a207ba1c4d08ec58095f5db34ee32c7341002920
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829174"
---
# <a name="equalityfactcp-function"></a>EqualityFactCP 函数

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


断言复数具有预期值。

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a>输入

### <a name="actual--complexpolar"></a>实际： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

要检查的值。


### <a name="expected--complexpolar"></a>应为： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

预期值。


### <a name="message--string"></a>消息： [字符串](xref:microsoft.quantum.lang-ref.string)

触发断言时要使用的失败消息字符串。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

