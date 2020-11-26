---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: 196bdab67528aa8672a010ac3830459e27276ce9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227516"
---
# <a name="pnormalized-function"></a><span data-ttu-id="f93b8-102">PNormalized 函数</span><span class="sxs-lookup"><span data-stu-id="f93b8-102">PNormalized function</span></span>

<span data-ttu-id="f93b8-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="f93b8-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="f93b8-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f93b8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f93b8-105">规范化中的向量 `Double` `L(p)` 。</span><span class="sxs-lookup"><span data-stu-id="f93b8-105">Normalizes a vector of `Double`s in the `L(p)` norm.</span></span>

<span data-ttu-id="f93b8-106">也就是说，给定类型的数组 $x $ `Double[]` ，这将返回一个数组，其中所有元素均除以 $p $-标准 $ \| x \| _p $。</span><span class="sxs-lookup"><span data-stu-id="f93b8-106">That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.</span></span>

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a><span data-ttu-id="f93b8-107">输入</span><span class="sxs-lookup"><span data-stu-id="f93b8-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="f93b8-108">p： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f93b8-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f93b8-109">指数 $p $ $p $-标准。</span><span class="sxs-lookup"><span data-stu-id="f93b8-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="f93b8-110">array： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="f93b8-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="f93b8-111">输出： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="f93b8-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="f93b8-112">由 $p $-标准 $ \| x _p $ 标准化 $x $ 的数组 \| 。</span><span class="sxs-lookup"><span data-stu-id="f93b8-112">The array $x$ normalized by the $p$-norm $\|x\|_p$.</span></span>

## <a name="see-also"></a><span data-ttu-id="f93b8-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f93b8-113">See Also</span></span>

- [<span data-ttu-id="f93b8-114">PNorm。</span><span class="sxs-lookup"><span data-stu-id="f93b8-114">Microsoft.Quantum.Math.PNorm</span></span>](xref:Microsoft.Quantum.Math.PNorm)