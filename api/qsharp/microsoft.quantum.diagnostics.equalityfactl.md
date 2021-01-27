---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: b7d37b5115c51596c1b3ed93c53a29e9f36b811d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829146"
---
# <a name="equalityfactl-function"></a><span data-ttu-id="5ae26-102">EqualityFactL 函数</span><span class="sxs-lookup"><span data-stu-id="5ae26-102">EqualityFactL function</span></span>

<span data-ttu-id="5ae26-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="5ae26-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="5ae26-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5ae26-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5ae26-105">断言传统 BigInt 变量具有预期值。</span><span class="sxs-lookup"><span data-stu-id="5ae26-105">Asserts that a classical BigInt variable has the expected value.</span></span>

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="5ae26-106">输入</span><span class="sxs-lookup"><span data-stu-id="5ae26-106">Input</span></span>

### <a name="actual--bigint"></a><span data-ttu-id="5ae26-107">实际： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5ae26-107">actual : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5ae26-108">要检查的数字。</span><span class="sxs-lookup"><span data-stu-id="5ae26-108">The number to be checked.</span></span>


### <a name="expected--bigint"></a><span data-ttu-id="5ae26-109">应为： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5ae26-109">expected : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5ae26-110">预期值。</span><span class="sxs-lookup"><span data-stu-id="5ae26-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="5ae26-111">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="5ae26-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="5ae26-112">触发断言时要使用的失败消息字符串。</span><span class="sxs-lookup"><span data-stu-id="5ae26-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5ae26-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5ae26-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

