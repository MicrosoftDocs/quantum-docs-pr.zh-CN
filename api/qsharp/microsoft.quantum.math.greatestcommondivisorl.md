---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorL
title: GreatestCommonDivisorL 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorL
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 77bdb040908e9a8af81dee09451a3582f7b7d159
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700616"
---
# <a name="greatestcommondivisorl-function"></a><span data-ttu-id="2bc08-102">GreatestCommonDivisorL 函数</span><span class="sxs-lookup"><span data-stu-id="2bc08-102">GreatestCommonDivisorL function</span></span>

<span data-ttu-id="2bc08-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="2bc08-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="2bc08-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2bc08-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2bc08-105">计算 $a $ 和 $b $ 的最大公因数。</span><span class="sxs-lookup"><span data-stu-id="2bc08-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="2bc08-106">GCD 始终为正值。</span><span class="sxs-lookup"><span data-stu-id="2bc08-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="2bc08-107">输入</span><span class="sxs-lookup"><span data-stu-id="2bc08-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="2bc08-108">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2bc08-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="2bc08-109">计算最大的最大公因数的第一个数字</span><span class="sxs-lookup"><span data-stu-id="2bc08-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="2bc08-110">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2bc08-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="2bc08-111">正在计算的最大扩展常见除数的第二个数字</span><span class="sxs-lookup"><span data-stu-id="2bc08-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigint"></a><span data-ttu-id="2bc08-112">输出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2bc08-112">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="2bc08-113">$a $ 和 $b $ 的最大公因数</span><span class="sxs-lookup"><span data-stu-id="2bc08-113">Greatest common divisor of $a$ and $b$</span></span>