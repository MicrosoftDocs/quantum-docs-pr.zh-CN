---
uid: Microsoft.Quantum.Diagnostics.EqualityFactI
title: EqualityFactI 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactI
qsharp.summary: Asserts that a classical Int variable has the expected value.
ms.openlocfilehash: 34bb38a9447f71372ec0b234731f31a5818d3af1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695567"
---
# <a name="equalityfacti-function"></a><span data-ttu-id="937c2-102">EqualityFactI 函数</span><span class="sxs-lookup"><span data-stu-id="937c2-102">EqualityFactI function</span></span>

<span data-ttu-id="937c2-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="937c2-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="937c2-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="937c2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="937c2-105">断言传统 Int 变量具有预期值。</span><span class="sxs-lookup"><span data-stu-id="937c2-105">Asserts that a classical Int variable has the expected value.</span></span>

```qsharp
function EqualityFactI (actual : Int, expected : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="937c2-106">输入</span><span class="sxs-lookup"><span data-stu-id="937c2-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="937c2-107">实际： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="937c2-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="937c2-108">要检查的数字。</span><span class="sxs-lookup"><span data-stu-id="937c2-108">The number to be checked.</span></span>


### <a name="expected--int"></a><span data-ttu-id="937c2-109">应为： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="937c2-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="937c2-110">预期值。</span><span class="sxs-lookup"><span data-stu-id="937c2-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="937c2-111">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="937c2-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="937c2-112">触发断言时要使用的失败消息字符串。</span><span class="sxs-lookup"><span data-stu-id="937c2-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="937c2-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="937c2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

