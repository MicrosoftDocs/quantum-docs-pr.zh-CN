---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: 6f9dfebe83f52cbf486cd8e6874d3699f5e6b8ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700228"
---
# <a name="pnormalized-function"></a><span data-ttu-id="0b212-102">PNormalized 函数</span><span class="sxs-lookup"><span data-stu-id="0b212-102">PNormalized function</span></span>

<span data-ttu-id="0b212-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="0b212-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="0b212-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0b212-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0b212-105">规范化中的向量 `Double` `L(p)` 。</span><span class="sxs-lookup"><span data-stu-id="0b212-105">Normalizes a vector of `Double`s in the `L(p)` norm.</span></span>

<span data-ttu-id="0b212-106">也就是说，给定类型的数组 $x $ `Double[]` ，这将返回一个数组，其中所有元素均除以 $p $-标准 $ \| x \| _p $。</span><span class="sxs-lookup"><span data-stu-id="0b212-106">That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.</span></span>

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a><span data-ttu-id="0b212-107">输入</span><span class="sxs-lookup"><span data-stu-id="0b212-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="0b212-108">p： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0b212-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0b212-109">指数 $p $ $p $-标准。</span><span class="sxs-lookup"><span data-stu-id="0b212-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="0b212-110">array： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="0b212-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="0b212-111">输出： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="0b212-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="0b212-112">由 $p $-标准 $ \| x _p $ 标准化 $x $ 的数组 \| 。</span><span class="sxs-lookup"><span data-stu-id="0b212-112">The array $x$ normalized by the $p$-norm $\|x\|_p$.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b212-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b212-113">See Also</span></span>

- [<span data-ttu-id="0b212-114">PNorm。</span><span class="sxs-lookup"><span data-stu-id="0b212-114">Microsoft.Quantum.Math.PNorm</span></span>](xref:Microsoft.Quantum.Math.PNorm)