---
uid: Microsoft.Quantum.Math.PNorm
title: PNorm 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: 3fe029bd893fc4d11aaf351f7ea566256cac5a9e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194723"
---
# <a name="pnorm-function"></a><span data-ttu-id="b88d4-102">PNorm 函数</span><span class="sxs-lookup"><span data-stu-id="b88d4-102">PNorm function</span></span>

<span data-ttu-id="b88d4-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b88d4-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b88d4-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b88d4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b88d4-105">返回 `L(p)` 向量的标准 `Double` 。</span><span class="sxs-lookup"><span data-stu-id="b88d4-105">Returns the `L(p)` norm of a vector of `Double`s.</span></span>

<span data-ttu-id="b88d4-106">也就是说，给定类型的数组 $x $ `Double[]` ，这将返回 $p $-标准 $ \| x \| \_ p = ( \ sum_ {j} | x_j | ^ {p} ) ^ {1/p} $。</span><span class="sxs-lookup"><span data-stu-id="b88d4-106">That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.</span></span>

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a><span data-ttu-id="b88d4-107">输入</span><span class="sxs-lookup"><span data-stu-id="b88d4-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="b88d4-108">p： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b88d4-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b88d4-109">指数 $p $ $p $-标准。</span><span class="sxs-lookup"><span data-stu-id="b88d4-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="b88d4-110">array： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="b88d4-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="b88d4-111">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b88d4-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b88d4-112">$P $-标准 $ \| x \| _p $。</span><span class="sxs-lookup"><span data-stu-id="b88d4-112">The $p$-norm $\|x\|_p$.</span></span>