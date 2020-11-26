---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: 2aaabf39d6ce49952466a877685776490ef438ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201795"
---
# <a name="equalityfactl-function"></a><span data-ttu-id="e0020-102">EqualityFactL 函数</span><span class="sxs-lookup"><span data-stu-id="e0020-102">EqualityFactL function</span></span>

<span data-ttu-id="e0020-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e0020-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e0020-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e0020-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e0020-105">断言传统 BigInt 变量具有预期值。</span><span class="sxs-lookup"><span data-stu-id="e0020-105">Asserts that a classical BigInt variable has the expected value.</span></span>

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="e0020-106">输入</span><span class="sxs-lookup"><span data-stu-id="e0020-106">Input</span></span>

### <a name="actual--bigint"></a><span data-ttu-id="e0020-107">实际： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e0020-107">actual : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e0020-108">要检查的数字。</span><span class="sxs-lookup"><span data-stu-id="e0020-108">The number to be checked.</span></span>


### <a name="expected--bigint"></a><span data-ttu-id="e0020-109">应为： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e0020-109">expected : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e0020-110">预期值。</span><span class="sxs-lookup"><span data-stu-id="e0020-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="e0020-111">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="e0020-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="e0020-112">触发断言时要使用的失败消息字符串。</span><span class="sxs-lookup"><span data-stu-id="e0020-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e0020-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e0020-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

