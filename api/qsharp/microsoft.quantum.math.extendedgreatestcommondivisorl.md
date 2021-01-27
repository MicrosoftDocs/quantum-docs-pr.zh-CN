---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorL
title: ExtendedGreatestCommonDivisorL 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorL
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 1445f1c3d2a5852459a492fa5e6bfd2a685786d9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857527"
---
# <a name="extendedgreatestcommondivisorl-function"></a><span data-ttu-id="b81c7-102">ExtendedGreatestCommonDivisorL 函数</span><span class="sxs-lookup"><span data-stu-id="b81c7-102">ExtendedGreatestCommonDivisorL function</span></span>

<span data-ttu-id="b81c7-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b81c7-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b81c7-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b81c7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b81c7-105">计算元组 $ (u，v) $，以便 $u \cdot a + v \cdot b = \operatorname{GCD} (a，b) $，其中 $ \operatorname{GCD} $ 是 $a $ 最大公因数 $a $ 和 $b $。</span><span class="sxs-lookup"><span data-stu-id="b81c7-105">Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="b81c7-106">GCD 始终为正值。</span><span class="sxs-lookup"><span data-stu-id="b81c7-106">The GCD is always positive.</span></span>

```qsharp
function ExtendedGreatestCommonDivisorL (a : BigInt, b : BigInt) : (BigInt, BigInt)
```


## <a name="input"></a><span data-ttu-id="b81c7-107">输入</span><span class="sxs-lookup"><span data-stu-id="b81c7-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="b81c7-108">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b81c7-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b81c7-109">计算最大的最大公因数的第一个数字</span><span class="sxs-lookup"><span data-stu-id="b81c7-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="b81c7-110">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b81c7-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b81c7-111">正在计算的最大扩展常见除数的第二个数字</span><span class="sxs-lookup"><span data-stu-id="b81c7-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigintbigint"></a><span data-ttu-id="b81c7-112">输出： ([bigint](xref:microsoft.quantum.lang-ref.bigint)、[bigint](xref:microsoft.quantum.lang-ref.bigint)) </span><span class="sxs-lookup"><span data-stu-id="b81c7-112">Output : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span></span>

<span data-ttu-id="b81c7-113">元组 $ (u，v) $，其属性 $u \cdot a + v \cdot b = \operatorname{GCD} (a，b) $。</span><span class="sxs-lookup"><span data-stu-id="b81c7-113">Tuple $(u,v)$ with the property $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$.</span></span>

## <a name="references"></a><span data-ttu-id="b81c7-114">参考</span><span class="sxs-lookup"><span data-stu-id="b81c7-114">References</span></span>

- <span data-ttu-id="b81c7-115">此实现取决于 https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span><span class="sxs-lookup"><span data-stu-id="b81c7-115">This implementation is according to https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span></span>