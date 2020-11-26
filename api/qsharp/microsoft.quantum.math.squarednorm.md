---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: ecbc66a8851f23187e0c0ea53ce121442323733b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227295"
---
# <a name="squarednorm-function"></a><span data-ttu-id="c07d5-102">SquaredNorm 函数</span><span class="sxs-lookup"><span data-stu-id="c07d5-102">SquaredNorm function</span></span>

<span data-ttu-id="c07d5-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="c07d5-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="c07d5-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c07d5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c07d5-105">返回向量的2平方标准。</span><span class="sxs-lookup"><span data-stu-id="c07d5-105">Returns the squared 2-norm of a vector.</span></span>

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a><span data-ttu-id="c07d5-106">描述</span><span class="sxs-lookup"><span data-stu-id="c07d5-106">Description</span></span>

<span data-ttu-id="c07d5-107">返回向量的2平方值;也就是说，如果输入 $ \vec{x} $，则返回 x_i ^ 2 $ 的 $ \ sum_i。</span><span class="sxs-lookup"><span data-stu-id="c07d5-107">Returns the squared 2-norm of a vector; that is, given an input $\vec{x}$, returns $\sum_i x_i^2$.</span></span>

## <a name="input"></a><span data-ttu-id="c07d5-108">输入</span><span class="sxs-lookup"><span data-stu-id="c07d5-108">Input</span></span>

### <a name="array--double"></a><span data-ttu-id="c07d5-109">array： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="c07d5-109">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="c07d5-110">要返回其方形2标准的向量。</span><span class="sxs-lookup"><span data-stu-id="c07d5-110">The vector whose squared 2-norm is to be returned.</span></span>



## <a name="output--double"></a><span data-ttu-id="c07d5-111">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c07d5-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c07d5-112">的2平方标准 `array` 。</span><span class="sxs-lookup"><span data-stu-id="c07d5-112">The squared 2-norm of `array`.</span></span>