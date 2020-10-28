---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: 冲突函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: a5f3f26c5ada2eea9206699a2cc77575a9b5eebd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695582"
---
# <a name="contradiction-function"></a><span data-ttu-id="d6160-102">冲突函数</span><span class="sxs-lookup"><span data-stu-id="d6160-102">Contradiction function</span></span>

<span data-ttu-id="d6160-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="d6160-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="d6160-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d6160-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d6160-105">声明传统条件为 false。</span><span class="sxs-lookup"><span data-stu-id="d6160-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="d6160-106">输入</span><span class="sxs-lookup"><span data-stu-id="d6160-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="d6160-107">实际： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d6160-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d6160-108">要声明的条件。</span><span class="sxs-lookup"><span data-stu-id="d6160-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="d6160-109">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="d6160-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="d6160-110">在古典条件为 true 时要打印的失败消息字符串。</span><span class="sxs-lookup"><span data-stu-id="d6160-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d6160-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d6160-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="d6160-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6160-112">See Also</span></span>

- [<span data-ttu-id="d6160-113">"..."</span><span class="sxs-lookup"><span data-stu-id="d6160-113">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)