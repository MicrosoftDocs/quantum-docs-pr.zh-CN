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
# <a name="message-function"></a><span data-ttu-id="3a347-102">消息函数</span><span class="sxs-lookup"><span data-stu-id="3a347-102">Message function</span></span>

<span data-ttu-id="3a347-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="3a347-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="3a347-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="3a347-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="3a347-105">在日志中记录消息。</span><span class="sxs-lookup"><span data-stu-id="3a347-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="3a347-106">输入</span><span class="sxs-lookup"><span data-stu-id="3a347-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="3a347-107">msg： [String](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="3a347-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="3a347-108">要报告的消息。</span><span class="sxs-lookup"><span data-stu-id="3a347-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3a347-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3a347-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3a347-110">备注</span><span class="sxs-lookup"><span data-stu-id="3a347-110">Remarks</span></span>

<span data-ttu-id="3a347-111">此函数的特定行为与模拟器相关，但在大多数情况下，会将给定消息写入控制台。</span><span class="sxs-lookup"><span data-stu-id="3a347-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>