---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: EqualityWithinToleranceFact 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: 6ada2632974fddd6dd0fd8e4e6ab0866e4f29524
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201710"
---
# <a name="equalitywithintolerancefact-function"></a><span data-ttu-id="9541e-102">EqualityWithinToleranceFact 函数</span><span class="sxs-lookup"><span data-stu-id="9541e-102">EqualityWithinToleranceFact function</span></span>

<span data-ttu-id="9541e-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="9541e-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="9541e-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9541e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9541e-105">表示某一传统浮点值具有到给定绝对公差的预期值。</span><span class="sxs-lookup"><span data-stu-id="9541e-105">Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.</span></span>

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="9541e-106">输入</span><span class="sxs-lookup"><span data-stu-id="9541e-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="9541e-107">实际： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9541e-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9541e-108">要检查的数字。</span><span class="sxs-lookup"><span data-stu-id="9541e-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="9541e-109">应为： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9541e-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9541e-110">预期值。</span><span class="sxs-lookup"><span data-stu-id="9541e-110">The expected value.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="9541e-111">容差： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9541e-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9541e-112">实际值与预期值的绝对容差。</span><span class="sxs-lookup"><span data-stu-id="9541e-112">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9541e-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9541e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

