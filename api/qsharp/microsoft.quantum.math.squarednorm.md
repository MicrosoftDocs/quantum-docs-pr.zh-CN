---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 72ae8266492bef64eaec34cd70c5fe725ee1e8c9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848219"
---
# <a name="squarednorm-function"></a><span data-ttu-id="e67d6-102">SquaredNorm 函数</span><span class="sxs-lookup"><span data-stu-id="e67d6-102">SquaredNorm function</span></span>

<span data-ttu-id="e67d6-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="e67d6-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="e67d6-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e67d6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e67d6-105">返回向量的2平方标准。</span><span class="sxs-lookup"><span data-stu-id="e67d6-105">Returns the squared 2-norm of a vector.</span></span>

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a><span data-ttu-id="e67d6-106">说明</span><span class="sxs-lookup"><span data-stu-id="e67d6-106">Description</span></span>

<span data-ttu-id="e67d6-107">返回向量的2平方值;也就是说，如果输入 $ \vec{x} $，则返回 x_i ^ 2 $ 的 $ \ sum_i。</span><span class="sxs-lookup"><span data-stu-id="e67d6-107">Returns the squared 2-norm of a vector; that is, given an input $\vec{x}$, returns $\sum_i x_i^2$.</span></span>

## <a name="input"></a><span data-ttu-id="e67d6-108">输入</span><span class="sxs-lookup"><span data-stu-id="e67d6-108">Input</span></span>

### <a name="array--double"></a><span data-ttu-id="e67d6-109">array： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="e67d6-109">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="e67d6-110">要返回其方形2标准的向量。</span><span class="sxs-lookup"><span data-stu-id="e67d6-110">The vector whose squared 2-norm is to be returned.</span></span>



## <a name="output--double"></a><span data-ttu-id="e67d6-111">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e67d6-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e67d6-112">的2平方标准 `array` 。</span><span class="sxs-lookup"><span data-stu-id="e67d6-112">The squared 2-norm of `array`.</span></span>