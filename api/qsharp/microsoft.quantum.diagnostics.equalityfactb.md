---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: d3163281772bda392fbdd61ad58543e22022a600
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695569"
---
# <a name="equalityfactb-function"></a><span data-ttu-id="6ce71-102">EqualityFactB 函数</span><span class="sxs-lookup"><span data-stu-id="6ce71-102">EqualityFactB function</span></span>

<span data-ttu-id="6ce71-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="6ce71-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="6ce71-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6ce71-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6ce71-105">断言传统 Bool 变量具有预期值。</span><span class="sxs-lookup"><span data-stu-id="6ce71-105">Asserts that a classical Bool variable has the expected value.</span></span>

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="6ce71-106">输入</span><span class="sxs-lookup"><span data-stu-id="6ce71-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="6ce71-107">实际： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6ce71-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6ce71-108">要检查的变量。</span><span class="sxs-lookup"><span data-stu-id="6ce71-108">The variable to be checked.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="6ce71-109">应为： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6ce71-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6ce71-110">预期值。</span><span class="sxs-lookup"><span data-stu-id="6ce71-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="6ce71-111">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="6ce71-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="6ce71-112">触发断言时要使用的失败消息字符串。</span><span class="sxs-lookup"><span data-stu-id="6ce71-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6ce71-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6ce71-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

