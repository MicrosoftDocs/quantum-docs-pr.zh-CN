---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 86d2ddff79f0bca7badd95a2fe2156c558fa7f86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853336"
---
# <a name="equalityfactr-function"></a><span data-ttu-id="d286b-102">EqualityFactR 函数</span><span class="sxs-lookup"><span data-stu-id="d286b-102">EqualityFactR function</span></span>

<span data-ttu-id="d286b-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="d286b-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="d286b-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d286b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d286b-105">断言传统结果变量具有预期值。</span><span class="sxs-lookup"><span data-stu-id="d286b-105">Asserts that a classical Result variable has the expected value.</span></span>

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="d286b-106">输入</span><span class="sxs-lookup"><span data-stu-id="d286b-106">Input</span></span>

### <a name="actual--__invalidresult__"></a><span data-ttu-id="d286b-107">实际：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="d286b-107">actual : __invalid<Result>__</span></span>

<span data-ttu-id="d286b-108">要检查的变量。</span><span class="sxs-lookup"><span data-stu-id="d286b-108">The variable to be checked.</span></span>


### <a name="expected--__invalidresult__"></a><span data-ttu-id="d286b-109">应为 __： <Result> 无效__</span><span class="sxs-lookup"><span data-stu-id="d286b-109">expected : __invalid<Result>__</span></span>

<span data-ttu-id="d286b-110">预期值。</span><span class="sxs-lookup"><span data-stu-id="d286b-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="d286b-111">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="d286b-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="d286b-112">触发断言时要使用的失败消息字符串。</span><span class="sxs-lookup"><span data-stu-id="d286b-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d286b-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d286b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

