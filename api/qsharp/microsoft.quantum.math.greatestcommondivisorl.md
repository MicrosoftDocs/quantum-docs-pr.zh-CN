---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorL
title: GreatestCommonDivisorL 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorL
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 0f545f7888f5a9a353cc6000a12988648ac82dd8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856373"
---
# <a name="greatestcommondivisorl-function"></a><span data-ttu-id="43a4b-102">GreatestCommonDivisorL 函数</span><span class="sxs-lookup"><span data-stu-id="43a4b-102">GreatestCommonDivisorL function</span></span>

<span data-ttu-id="43a4b-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="43a4b-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="43a4b-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="43a4b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="43a4b-105">计算 $a $ 和 $b $ 的最大公因数。</span><span class="sxs-lookup"><span data-stu-id="43a4b-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="43a4b-106">GCD 始终为正值。</span><span class="sxs-lookup"><span data-stu-id="43a4b-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="43a4b-107">输入</span><span class="sxs-lookup"><span data-stu-id="43a4b-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="43a4b-108">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="43a4b-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="43a4b-109">计算最大的最大公因数的第一个数字</span><span class="sxs-lookup"><span data-stu-id="43a4b-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="43a4b-110">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="43a4b-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="43a4b-111">正在计算的最大扩展常见除数的第二个数字</span><span class="sxs-lookup"><span data-stu-id="43a4b-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigint"></a><span data-ttu-id="43a4b-112">输出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="43a4b-112">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="43a4b-113">$a $ 和 $b $ 的最大公因数</span><span class="sxs-lookup"><span data-stu-id="43a4b-113">Greatest common divisor of $a$ and $b$</span></span>