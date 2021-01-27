---
uid: Microsoft.Quantum.Intrinsic.Message
title: 消息函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 652e33de69ffb725f117db3beeffa66558776f49
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849362"
---
# <a name="message-function"></a>消息函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


在日志中记录消息。

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a>输入

### <a name="msg--string"></a>msg： [String](xref:microsoft.quantum.lang-ref.string)

要报告的消息。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>备注

此函数的特定行为与模拟器相关，但在大多数情况下，会将给定消息写入控制台。