---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorI
title: GreatestCommonDivisorI 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorI
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 7fd891aa2e4753020ec9ac4e702f8af9edc9df0a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700617"
---
# <a name="greatestcommondivisori-function"></a><span data-ttu-id="66222-102">GreatestCommonDivisorI 函数</span><span class="sxs-lookup"><span data-stu-id="66222-102">GreatestCommonDivisorI function</span></span>

<span data-ttu-id="66222-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="66222-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="66222-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="66222-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="66222-105">计算 $a $ 和 $b $ 的最大公因数。</span><span class="sxs-lookup"><span data-stu-id="66222-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="66222-106">GCD 始终为正值。</span><span class="sxs-lookup"><span data-stu-id="66222-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorI (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="66222-107">输入</span><span class="sxs-lookup"><span data-stu-id="66222-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="66222-108">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="66222-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="66222-109">计算最大的最大公因数的第一个数字</span><span class="sxs-lookup"><span data-stu-id="66222-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--int"></a><span data-ttu-id="66222-110">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="66222-110">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="66222-111">正在计算的最大扩展常见除数的第二个数字</span><span class="sxs-lookup"><span data-stu-id="66222-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--int"></a><span data-ttu-id="66222-112">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="66222-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="66222-113">$a $ 和 $b $ 的最大公因数</span><span class="sxs-lookup"><span data-stu-id="66222-113">Greatest common divisor of $a$ and $b$</span></span>