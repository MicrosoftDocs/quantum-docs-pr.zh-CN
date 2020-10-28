---
uid: Microsoft.Quantum.Math.PNorm
title: PNorm 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: cea85715e448305486f6d8a6c10e11da56edf3ee
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700232"
---
# <a name="pnorm-function"></a><span data-ttu-id="d2bd8-102">PNorm 函数</span><span class="sxs-lookup"><span data-stu-id="d2bd8-102">PNorm function</span></span>

<span data-ttu-id="d2bd8-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="d2bd8-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="d2bd8-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d2bd8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d2bd8-105">返回 `L(p)` 向量的标准 `Double` 。</span><span class="sxs-lookup"><span data-stu-id="d2bd8-105">Returns the `L(p)` norm of a vector of `Double`s.</span></span>

<span data-ttu-id="d2bd8-106">也就是说，给定类型的数组 $x $ `Double[]` ，这将返回 $p $-标准 $ \| x \| \_ p = ( \ sum_ {j} | x_j | ^ {p} ) ^ {1/p} $。</span><span class="sxs-lookup"><span data-stu-id="d2bd8-106">That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.</span></span>

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a><span data-ttu-id="d2bd8-107">输入</span><span class="sxs-lookup"><span data-stu-id="d2bd8-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="d2bd8-108">p： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d2bd8-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d2bd8-109">指数 $p $ $p $-标准。</span><span class="sxs-lookup"><span data-stu-id="d2bd8-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="d2bd8-110">array： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="d2bd8-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="d2bd8-111">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d2bd8-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d2bd8-112">$P $-标准 $ \| x \| _p $。</span><span class="sxs-lookup"><span data-stu-id="d2bd8-112">The $p$-norm $\|x\|_p$.</span></span>