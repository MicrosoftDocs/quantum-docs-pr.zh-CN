---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 2b293dc581ed58f7e3864a952fb3ecafa68e759c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695564"
---
# <a name="equalityfactr-function"></a><span data-ttu-id="7f8b3-102">EqualityFactR 函数</span><span class="sxs-lookup"><span data-stu-id="7f8b3-102">EqualityFactR function</span></span>

<span data-ttu-id="7f8b3-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="7f8b3-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="7f8b3-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7f8b3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7f8b3-105">断言传统结果变量具有预期值。</span><span class="sxs-lookup"><span data-stu-id="7f8b3-105">Asserts that a classical Result variable has the expected value.</span></span>

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="7f8b3-106">输入</span><span class="sxs-lookup"><span data-stu-id="7f8b3-106">Input</span></span>

### <a name="actual--__invalidresult__"></a><span data-ttu-id="7f8b3-107">实际： __无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="7f8b3-107">actual : __invalid<Result>__</span></span>

<span data-ttu-id="7f8b3-108">要检查的变量。</span><span class="sxs-lookup"><span data-stu-id="7f8b3-108">The variable to be checked.</span></span>


### <a name="expected--__invalidresult__"></a><span data-ttu-id="7f8b3-109">应为 __： <Result> 无效__</span><span class="sxs-lookup"><span data-stu-id="7f8b3-109">expected : __invalid<Result>__</span></span>

<span data-ttu-id="7f8b3-110">预期值。</span><span class="sxs-lookup"><span data-stu-id="7f8b3-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="7f8b3-111">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="7f8b3-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="7f8b3-112">触发断言时要使用的失败消息字符串。</span><span class="sxs-lookup"><span data-stu-id="7f8b3-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7f8b3-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7f8b3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

