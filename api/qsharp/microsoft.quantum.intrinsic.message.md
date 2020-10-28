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
# <a name="message-function"></a><span data-ttu-id="6a28b-102">消息函数</span><span class="sxs-lookup"><span data-stu-id="6a28b-102">Message function</span></span>

<span data-ttu-id="6a28b-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="6a28b-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="6a28b-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6a28b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6a28b-105">在日志中记录消息。</span><span class="sxs-lookup"><span data-stu-id="6a28b-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="6a28b-106">输入</span><span class="sxs-lookup"><span data-stu-id="6a28b-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="6a28b-107">msg： [String](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="6a28b-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="6a28b-108">要报告的消息。</span><span class="sxs-lookup"><span data-stu-id="6a28b-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6a28b-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6a28b-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6a28b-110">注解</span><span class="sxs-lookup"><span data-stu-id="6a28b-110">Remarks</span></span>

<span data-ttu-id="6a28b-111">此函数的特定行为与模拟器相关，但在大多数情况下，会将给定消息写入控制台。</span><span class="sxs-lookup"><span data-stu-id="6a28b-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>