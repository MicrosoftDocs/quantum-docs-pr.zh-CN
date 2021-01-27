---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: EqualityWithinToleranceFact 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: ab7e43d951bf741926b15f27f94d176e88609d4a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828753"
---
# <a name="equalitywithintolerancefact-function"></a><span data-ttu-id="e67b1-102">EqualityWithinToleranceFact 函数</span><span class="sxs-lookup"><span data-stu-id="e67b1-102">EqualityWithinToleranceFact function</span></span>

<span data-ttu-id="e67b1-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e67b1-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e67b1-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e67b1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e67b1-105">表示某一传统浮点值具有到给定绝对公差的预期值。</span><span class="sxs-lookup"><span data-stu-id="e67b1-105">Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.</span></span>

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="e67b1-106">输入</span><span class="sxs-lookup"><span data-stu-id="e67b1-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="e67b1-107">实际： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e67b1-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e67b1-108">要检查的数字。</span><span class="sxs-lookup"><span data-stu-id="e67b1-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="e67b1-109">应为： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e67b1-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e67b1-110">预期值。</span><span class="sxs-lookup"><span data-stu-id="e67b1-110">The expected value.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="e67b1-111">容差： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e67b1-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e67b1-112">实际值与预期值的绝对容差。</span><span class="sxs-lookup"><span data-stu-id="e67b1-112">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e67b1-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e67b1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

