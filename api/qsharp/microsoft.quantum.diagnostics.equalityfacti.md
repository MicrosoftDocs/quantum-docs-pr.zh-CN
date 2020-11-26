---
uid: Microsoft.Quantum.Diagnostics.EqualityFactI
title: EqualityFactI 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactI
qsharp.summary: Asserts that a classical Int variable has the expected value.
ms.openlocfilehash: 27c0642f6d89aaa715526092813240e11b9ab530
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201829"
---
# <a name="equalityfacti-function"></a><span data-ttu-id="bdd24-102">EqualityFactI 函数</span><span class="sxs-lookup"><span data-stu-id="bdd24-102">EqualityFactI function</span></span>

<span data-ttu-id="bdd24-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="bdd24-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="bdd24-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bdd24-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bdd24-105">断言传统 Int 变量具有预期值。</span><span class="sxs-lookup"><span data-stu-id="bdd24-105">Asserts that a classical Int variable has the expected value.</span></span>

```qsharp
function EqualityFactI (actual : Int, expected : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="bdd24-106">输入</span><span class="sxs-lookup"><span data-stu-id="bdd24-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="bdd24-107">实际： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bdd24-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bdd24-108">要检查的数字。</span><span class="sxs-lookup"><span data-stu-id="bdd24-108">The number to be checked.</span></span>


### <a name="expected--int"></a><span data-ttu-id="bdd24-109">应为： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bdd24-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bdd24-110">预期值。</span><span class="sxs-lookup"><span data-stu-id="bdd24-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="bdd24-111">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="bdd24-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="bdd24-112">触发断言时要使用的失败消息字符串。</span><span class="sxs-lookup"><span data-stu-id="bdd24-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bdd24-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bdd24-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

