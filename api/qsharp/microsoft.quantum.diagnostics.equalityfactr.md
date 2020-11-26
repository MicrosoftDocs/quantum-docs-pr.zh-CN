---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 166dff211d6db9da5d39c607af1924ffd6d276dd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201761"
---
# <a name="equalityfactr-function"></a>EqualityFactR 函数

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


断言传统结果变量具有预期值。

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a>输入

### <a name="actual--__invalidresult__"></a>实际：__无效 <Result>__

要检查的变量。


### <a name="expected--__invalidresult__"></a>应为 __： <Result> 无效__

预期值。


### <a name="message--string"></a>消息： [字符串](xref:microsoft.quantum.lang-ref.string)

触发断言时要使用的失败消息字符串。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

