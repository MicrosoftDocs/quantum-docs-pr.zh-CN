---
uid: Microsoft.Quantum.Diagnostics.Fact
title: 事实函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 6a08703f68f9f38f2224fe4c6a4d255b00756908
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695556"
---
# <a name="fact-function"></a><span data-ttu-id="c3f1e-102">事实函数</span><span class="sxs-lookup"><span data-stu-id="c3f1e-102">Fact function</span></span>

<span data-ttu-id="c3f1e-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="c3f1e-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="c3f1e-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c3f1e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c3f1e-105">声明传统条件为 true。</span><span class="sxs-lookup"><span data-stu-id="c3f1e-105">Declares that a classical condition is true.</span></span>

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="c3f1e-106">输入</span><span class="sxs-lookup"><span data-stu-id="c3f1e-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="c3f1e-107">实际： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c3f1e-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c3f1e-108">要声明的条件。</span><span class="sxs-lookup"><span data-stu-id="c3f1e-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="c3f1e-109">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="c3f1e-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="c3f1e-110">在古典条件为 false 时要打印的失败消息字符串。</span><span class="sxs-lookup"><span data-stu-id="c3f1e-110">Failure message string to be printed in the case that the classical condition is false.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c3f1e-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c3f1e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="c3f1e-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3f1e-112">See Also</span></span>

- [<span data-ttu-id="c3f1e-113">Microsoft 量子. 矛盾</span><span class="sxs-lookup"><span data-stu-id="c3f1e-113">Microsoft.Quantum.Diagnostics.Contradiction</span></span>](xref:Microsoft.Quantum.Diagnostics.Contradiction)