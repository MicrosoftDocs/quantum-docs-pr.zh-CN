---
uid: Microsoft.Quantum.Intrinsic.Message
title: 消息函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 4eb55dd4fd8d78e4b5a9bb289dacfbdb3aa4beb8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199006"
---
# <a name="message-function"></a><span data-ttu-id="da7ce-102">消息函数</span><span class="sxs-lookup"><span data-stu-id="da7ce-102">Message function</span></span>

<span data-ttu-id="da7ce-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="da7ce-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="da7ce-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="da7ce-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="da7ce-105">在日志中记录消息。</span><span class="sxs-lookup"><span data-stu-id="da7ce-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="da7ce-106">输入</span><span class="sxs-lookup"><span data-stu-id="da7ce-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="da7ce-107">msg： [String](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="da7ce-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="da7ce-108">要报告的消息。</span><span class="sxs-lookup"><span data-stu-id="da7ce-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="da7ce-109">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="da7ce-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="da7ce-110">备注</span><span class="sxs-lookup"><span data-stu-id="da7ce-110">Remarks</span></span>

<span data-ttu-id="da7ce-111">此函数的特定行为与模拟器相关，但在大多数情况下，会将给定消息写入控制台。</span><span class="sxs-lookup"><span data-stu-id="da7ce-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>