---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: 冲突函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: 7d62c9341b768dfdfbfbf8e73e64748f04317595
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829363"
---
# <a name="contradiction-function"></a>冲突函数

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


声明传统条件为 false。

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a>输入

### <a name="actual--bool"></a>实际： [Bool](xref:microsoft.quantum.lang-ref.bool)

要声明的条件。


### <a name="message--string"></a>消息： [字符串](xref:microsoft.quantum.lang-ref.string)

在古典条件为 true 时要打印的失败消息字符串。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>示例

以下 Q # 代码将打印 "Hello，world"：

```qsharp
Contradiction(2 == 3, "2 is not equal to 3.");
Message("Hello, world.");
```

## <a name="see-also"></a>另请参阅

- ["..."](xref:Microsoft.Quantum.Diagnostics.Fact)