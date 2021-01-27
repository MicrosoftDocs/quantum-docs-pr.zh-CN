---
uid: Microsoft.Quantum.Diagnostics.Fact
title: 事实函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 8e86000f04c01040d420c2f682fc1b4ccf35cf39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853310"
---
# <a name="fact-function"></a><span data-ttu-id="73339-102">事实函数</span><span class="sxs-lookup"><span data-stu-id="73339-102">Fact function</span></span>

<span data-ttu-id="73339-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="73339-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="73339-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="73339-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="73339-105">声明传统条件为 true。</span><span class="sxs-lookup"><span data-stu-id="73339-105">Declares that a classical condition is true.</span></span>

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="73339-106">输入</span><span class="sxs-lookup"><span data-stu-id="73339-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="73339-107">实际： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="73339-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="73339-108">要声明的条件。</span><span class="sxs-lookup"><span data-stu-id="73339-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="73339-109">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="73339-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="73339-110">在古典条件为 false 时要打印的失败消息字符串。</span><span class="sxs-lookup"><span data-stu-id="73339-110">Failure message string to be printed in the case that the classical condition is false.</span></span>



## <a name="output--unit"></a><span data-ttu-id="73339-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="73339-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="73339-112">示例</span><span class="sxs-lookup"><span data-stu-id="73339-112">Example</span></span>

<span data-ttu-id="73339-113">以下 Q # 代码段将失败：</span><span class="sxs-lookup"><span data-stu-id="73339-113">The following Q# snippet will fail:</span></span>

```qsharp
Fact(false, "Expected true.");
```

## <a name="see-also"></a><span data-ttu-id="73339-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73339-114">See Also</span></span>

- [<span data-ttu-id="73339-115">Microsoft 量子. 矛盾</span><span class="sxs-lookup"><span data-stu-id="73339-115">Microsoft.Quantum.Diagnostics.Contradiction</span></span>](xref:Microsoft.Quantum.Diagnostics.Contradiction)