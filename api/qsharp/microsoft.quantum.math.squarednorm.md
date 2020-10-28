---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 4165a761753f336cb7b94ad36b11ac324ad4e5c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701009"
---
# <a name="squarednorm-function"></a><span data-ttu-id="ffe99-102">SquaredNorm 函数</span><span class="sxs-lookup"><span data-stu-id="ffe99-102">SquaredNorm function</span></span>

<span data-ttu-id="ffe99-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="ffe99-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="ffe99-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ffe99-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ffe99-105">返回向量的2平方标准。</span><span class="sxs-lookup"><span data-stu-id="ffe99-105">Returns the squared 2-norm of a vector.</span></span>

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a><span data-ttu-id="ffe99-106">说明</span><span class="sxs-lookup"><span data-stu-id="ffe99-106">Description</span></span>

<span data-ttu-id="ffe99-107">返回向量的2平方值;也就是说，如果输入 $ \vec{x} $，则返回 x_i ^ 2 $ 的 $ \ sum_i。</span><span class="sxs-lookup"><span data-stu-id="ffe99-107">Returns the squared 2-norm of a vector; that is, given an input $\vec{x}$, returns $\sum_i x_i^2$.</span></span>

## <a name="input"></a><span data-ttu-id="ffe99-108">输入</span><span class="sxs-lookup"><span data-stu-id="ffe99-108">Input</span></span>

### <a name="array--double"></a><span data-ttu-id="ffe99-109">array： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="ffe99-109">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="ffe99-110">要返回其方形2标准的向量。</span><span class="sxs-lookup"><span data-stu-id="ffe99-110">The vector whose squared 2-norm is to be returned.</span></span>



## <a name="output--double"></a><span data-ttu-id="ffe99-111">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ffe99-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ffe99-112">的2平方标准 `array` 。</span><span class="sxs-lookup"><span data-stu-id="ffe99-112">The squared 2-norm of `array`.</span></span>