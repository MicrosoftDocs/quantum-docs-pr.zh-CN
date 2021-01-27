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
# <a name="contradiction-function"></a><span data-ttu-id="3b609-102">冲突函数</span><span class="sxs-lookup"><span data-stu-id="3b609-102">Contradiction function</span></span>

<span data-ttu-id="3b609-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="3b609-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="3b609-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="3b609-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="3b609-105">声明传统条件为 false。</span><span class="sxs-lookup"><span data-stu-id="3b609-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="3b609-106">输入</span><span class="sxs-lookup"><span data-stu-id="3b609-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="3b609-107">实际： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3b609-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3b609-108">要声明的条件。</span><span class="sxs-lookup"><span data-stu-id="3b609-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="3b609-109">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="3b609-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="3b609-110">在古典条件为 true 时要打印的失败消息字符串。</span><span class="sxs-lookup"><span data-stu-id="3b609-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3b609-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3b609-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="3b609-112">示例</span><span class="sxs-lookup"><span data-stu-id="3b609-112">Example</span></span>

<span data-ttu-id="3b609-113">以下 Q # 代码将打印 "Hello，world"：</span><span class="sxs-lookup"><span data-stu-id="3b609-113">The following Q# code will print "Hello, world":</span></span>

```qsharp
Contradiction(2 == 3, "2 is not equal to 3.");
Message("Hello, world.");
```

## <a name="see-also"></a><span data-ttu-id="3b609-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b609-114">See Also</span></span>

- [<span data-ttu-id="3b609-115">"..."</span><span class="sxs-lookup"><span data-stu-id="3b609-115">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)