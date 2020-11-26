---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorI
title: GreatestCommonDivisorI 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorI
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 2b6ba8a6d5ac78b69e6ee20160f3a3b1df61a879
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228468"
---
# <a name="greatestcommondivisori-function"></a><span data-ttu-id="dcd22-102">GreatestCommonDivisorI 函数</span><span class="sxs-lookup"><span data-stu-id="dcd22-102">GreatestCommonDivisorI function</span></span>

<span data-ttu-id="dcd22-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="dcd22-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="dcd22-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dcd22-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dcd22-105">计算 $a $ 和 $b $ 的最大公因数。</span><span class="sxs-lookup"><span data-stu-id="dcd22-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="dcd22-106">GCD 始终为正值。</span><span class="sxs-lookup"><span data-stu-id="dcd22-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorI (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="dcd22-107">输入</span><span class="sxs-lookup"><span data-stu-id="dcd22-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="dcd22-108">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dcd22-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dcd22-109">计算最大的最大公因数的第一个数字</span><span class="sxs-lookup"><span data-stu-id="dcd22-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--int"></a><span data-ttu-id="dcd22-110">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dcd22-110">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dcd22-111">正在计算的最大扩展常见除数的第二个数字</span><span class="sxs-lookup"><span data-stu-id="dcd22-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--int"></a><span data-ttu-id="dcd22-112">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dcd22-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dcd22-113">$a $ 和 $b $ 的最大公因数</span><span class="sxs-lookup"><span data-stu-id="dcd22-113">Greatest common divisor of $a$ and $b$</span></span>