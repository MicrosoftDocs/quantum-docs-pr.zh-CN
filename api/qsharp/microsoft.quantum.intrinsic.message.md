---
uid: Microsoft.Quantum.Intrinsic.Message
title: 消息函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 0428a46bc639bc8a0697f5bd392f85b8b9f40ee5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695376"
---
# <a name="message-function"></a>消息函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)

软件包 [](https://nuget.org/packages/)


在日志中记录消息。

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a>输入

### <a name="msg--string"></a>msg： [String](xref:microsoft.quantum.lang-ref.string)

要报告的消息。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

此函数的特定行为与模拟器相关，但在大多数情况下，会将给定消息写入控制台。