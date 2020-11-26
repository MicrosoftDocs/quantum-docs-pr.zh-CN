---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 166dff211d6db9da5d39c607af1924ffd6d276dd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201761"
---
# <a name="equalityfactr-function"></a><span data-ttu-id="6e048-102">EqualityFactR 函数</span><span class="sxs-lookup"><span data-stu-id="6e048-102">EqualityFactR function</span></span>

<span data-ttu-id="6e048-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="6e048-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="6e048-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6e048-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6e048-105">断言传统结果变量具有预期值。</span><span class="sxs-lookup"><span data-stu-id="6e048-105">Asserts that a classical Result variable has the expected value.</span></span>

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="6e048-106">输入</span><span class="sxs-lookup"><span data-stu-id="6e048-106">Input</span></span>

### <a name="actual--__invalidresult__"></a><span data-ttu-id="6e048-107">实际：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="6e048-107">actual : __invalid<Result>__</span></span>

<span data-ttu-id="6e048-108">要检查的变量。</span><span class="sxs-lookup"><span data-stu-id="6e048-108">The variable to be checked.</span></span>


### <a name="expected--__invalidresult__"></a><span data-ttu-id="6e048-109">应为 __： <Result> 无效__</span><span class="sxs-lookup"><span data-stu-id="6e048-109">expected : __invalid<Result>__</span></span>

<span data-ttu-id="6e048-110">预期值。</span><span class="sxs-lookup"><span data-stu-id="6e048-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="6e048-111">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="6e048-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="6e048-112">触发断言时要使用的失败消息字符串。</span><span class="sxs-lookup"><span data-stu-id="6e048-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6e048-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6e048-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

