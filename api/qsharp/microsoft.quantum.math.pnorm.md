---
uid: Microsoft.Quantum.Math.PNorm
title: PNorm 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: 6207cca6cda5f9030facd31c327e58bdb9ecbf14
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847652"
---
# <a name="pnorm-function"></a><span data-ttu-id="675ba-102">PNorm 函数</span><span class="sxs-lookup"><span data-stu-id="675ba-102">PNorm function</span></span>

<span data-ttu-id="675ba-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="675ba-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="675ba-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="675ba-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="675ba-105">返回 `L(p)` 向量的标准 `Double` 。</span><span class="sxs-lookup"><span data-stu-id="675ba-105">Returns the `L(p)` norm of a vector of `Double`s.</span></span>

<span data-ttu-id="675ba-106">也就是说，给定类型的数组 $x $ `Double[]` ，这将返回 $p $-标准 $ \| x \| \_ p = ( \ sum_ {j} | x_j | ^ {p} ) ^ {1/p} $。</span><span class="sxs-lookup"><span data-stu-id="675ba-106">That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.</span></span>

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a><span data-ttu-id="675ba-107">输入</span><span class="sxs-lookup"><span data-stu-id="675ba-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="675ba-108">p： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="675ba-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="675ba-109">指数 $p $ $p $-标准。</span><span class="sxs-lookup"><span data-stu-id="675ba-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="675ba-110">array： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="675ba-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="675ba-111">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="675ba-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="675ba-112">$P $-标准 $ \| x \| _p $。</span><span class="sxs-lookup"><span data-stu-id="675ba-112">The $p$-norm $\|x\|_p$.</span></span>