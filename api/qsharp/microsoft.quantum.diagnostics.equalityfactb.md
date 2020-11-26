---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: a87d6690e701eb1530be3134d24884a8c19357e9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201914"
---
# <a name="equalityfactb-function"></a><span data-ttu-id="f3a9f-102">EqualityFactB 函数</span><span class="sxs-lookup"><span data-stu-id="f3a9f-102">EqualityFactB function</span></span>

<span data-ttu-id="f3a9f-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="f3a9f-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="f3a9f-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f3a9f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f3a9f-105">断言传统 Bool 变量具有预期值。</span><span class="sxs-lookup"><span data-stu-id="f3a9f-105">Asserts that a classical Bool variable has the expected value.</span></span>

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="f3a9f-106">输入</span><span class="sxs-lookup"><span data-stu-id="f3a9f-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="f3a9f-107">实际： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f3a9f-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f3a9f-108">要检查的变量。</span><span class="sxs-lookup"><span data-stu-id="f3a9f-108">The variable to be checked.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="f3a9f-109">应为： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f3a9f-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f3a9f-110">预期值。</span><span class="sxs-lookup"><span data-stu-id="f3a9f-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="f3a9f-111">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="f3a9f-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="f3a9f-112">触发断言时要使用的失败消息字符串。</span><span class="sxs-lookup"><span data-stu-id="f3a9f-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f3a9f-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f3a9f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

