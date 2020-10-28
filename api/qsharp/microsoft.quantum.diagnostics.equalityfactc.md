---
uid: Microsoft.Quantum.Diagnostics.EqualityFactC
title: EqualityFactC 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactC
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 4c7256f9a8c84b4e105b1cbff6b18d6dd99cc441
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695570"
---
# <a name="equalityfactc-function"></a>EqualityFactC 函数

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

软件包 [](https://nuget.org/packages/)


断言复数具有预期值。

```qsharp
function EqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex, message : String) : Unit
```


## <a name="input"></a>输入

### <a name="actual--complex"></a>实际： [复杂](xref:Microsoft.Quantum.Math.Complex)

要检查的值。


### <a name="expected--complex"></a>应为： [复杂](xref:Microsoft.Quantum.Math.Complex)

预期值。


### <a name="message--string"></a>消息： [字符串](xref:microsoft.quantum.lang-ref.string)

触发断言时要使用的失败消息字符串。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

