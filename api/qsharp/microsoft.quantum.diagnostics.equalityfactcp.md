---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: a207ba1c4d08ec58095f5db34ee32c7341002920
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829174"
---
# <a name="equalityfactcp-function"></a><span data-ttu-id="88109-102">EqualityFactCP 函数</span><span class="sxs-lookup"><span data-stu-id="88109-102">EqualityFactCP function</span></span>

<span data-ttu-id="88109-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="88109-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="88109-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="88109-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="88109-105">断言复数具有预期值。</span><span class="sxs-lookup"><span data-stu-id="88109-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="88109-106">输入</span><span class="sxs-lookup"><span data-stu-id="88109-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="88109-107">实际： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="88109-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="88109-108">要检查的值。</span><span class="sxs-lookup"><span data-stu-id="88109-108">The value to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="88109-109">应为： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="88109-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="88109-110">预期值。</span><span class="sxs-lookup"><span data-stu-id="88109-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="88109-111">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="88109-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="88109-112">触发断言时要使用的失败消息字符串。</span><span class="sxs-lookup"><span data-stu-id="88109-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="88109-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="88109-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

