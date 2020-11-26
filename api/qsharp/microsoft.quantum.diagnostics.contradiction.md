---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: 冲突函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: f9ad9a7d67bda8e50c76f679f535ad55ba07698e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202135"
---
# <a name="contradiction-function"></a><span data-ttu-id="06a06-102">冲突函数</span><span class="sxs-lookup"><span data-stu-id="06a06-102">Contradiction function</span></span>

<span data-ttu-id="06a06-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="06a06-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="06a06-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="06a06-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="06a06-105">声明传统条件为 false。</span><span class="sxs-lookup"><span data-stu-id="06a06-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="06a06-106">输入</span><span class="sxs-lookup"><span data-stu-id="06a06-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="06a06-107">实际： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="06a06-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="06a06-108">要声明的条件。</span><span class="sxs-lookup"><span data-stu-id="06a06-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="06a06-109">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="06a06-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="06a06-110">在古典条件为 true 时要打印的失败消息字符串。</span><span class="sxs-lookup"><span data-stu-id="06a06-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="06a06-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="06a06-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="06a06-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="06a06-112">See Also</span></span>

- [<span data-ttu-id="06a06-113">"..."</span><span class="sxs-lookup"><span data-stu-id="06a06-113">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)