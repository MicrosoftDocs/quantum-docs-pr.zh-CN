---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: cb1d4c471c528d2d3c08c92619fafd532a88c8f0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829202"
---
# <a name="equalityfactb-function"></a><span data-ttu-id="2de1f-102">EqualityFactB 函数</span><span class="sxs-lookup"><span data-stu-id="2de1f-102">EqualityFactB function</span></span>

<span data-ttu-id="2de1f-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2de1f-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2de1f-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2de1f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2de1f-105">断言传统 Bool 变量具有预期值。</span><span class="sxs-lookup"><span data-stu-id="2de1f-105">Asserts that a classical Bool variable has the expected value.</span></span>

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="2de1f-106">输入</span><span class="sxs-lookup"><span data-stu-id="2de1f-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="2de1f-107">实际： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2de1f-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2de1f-108">要检查的变量。</span><span class="sxs-lookup"><span data-stu-id="2de1f-108">The variable to be checked.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="2de1f-109">应为： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2de1f-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2de1f-110">预期值。</span><span class="sxs-lookup"><span data-stu-id="2de1f-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="2de1f-111">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="2de1f-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="2de1f-112">触发断言时要使用的失败消息字符串。</span><span class="sxs-lookup"><span data-stu-id="2de1f-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2de1f-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2de1f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

