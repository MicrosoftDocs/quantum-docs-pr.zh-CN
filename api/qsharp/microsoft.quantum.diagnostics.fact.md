---
uid: Microsoft.Quantum.Diagnostics.Fact
title: 事实函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 74ec020d0437d885d7cbfc98a2c9c0c1867d5d39
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201676"
---
# <a name="fact-function"></a>事实函数

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


声明传统条件为 true。

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a>输入

### <a name="actual--bool"></a>实际： [Bool](xref:microsoft.quantum.lang-ref.bool)

要声明的条件。


### <a name="message--string"></a>消息： [字符串](xref:microsoft.quantum.lang-ref.string)

在古典条件为 false 时要打印的失败消息字符串。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另请参阅

- [Microsoft 量子. 矛盾](xref:Microsoft.Quantum.Diagnostics.Contradiction)