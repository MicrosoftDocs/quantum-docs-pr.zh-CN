---
uid: Microsoft.Quantum.Arithmetic.EvaluatePolynomialFxP
title: EvaluatePolynomialFxP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluatePolynomialFxP
qsharp.summary: Evaluates a polynomial in a fixed-point representation.
ms.openlocfilehash: 3903bf69d5b0a6e57530f2c6a44e1d351c8a605f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699888"
---
# <a name="evaluatepolynomialfxp-operation"></a><span data-ttu-id="a1e2a-102">EvaluatePolynomialFxP 操作</span><span class="sxs-lookup"><span data-stu-id="a1e2a-102">EvaluatePolynomialFxP operation</span></span>

<span data-ttu-id="a1e2a-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a1e2a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a1e2a-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a1e2a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a1e2a-105">计算定点表示形式的多项式。</span><span class="sxs-lookup"><span data-stu-id="a1e2a-105">Evaluates a polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluatePolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="a1e2a-106">输入</span><span class="sxs-lookup"><span data-stu-id="a1e2a-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="a1e2a-107">系数： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a1e2a-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a1e2a-108">多项式的系数为 double 数组，即数组 $ [a_0，a_1，...，a_d] $ for 多项式 $P (x) = a_0 + a_1 x + \cdots + a_d x ^ d $。</span><span class="sxs-lookup"><span data-stu-id="a1e2a-108">Coefficients of the polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_d]$ for the polynomial $P(x) = a_0 + a_1 x + \cdots + a_d x^d$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="a1e2a-109">fpx： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="a1e2a-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="a1e2a-110">为其计算多项式的定点数。</span><span class="sxs-lookup"><span data-stu-id="a1e2a-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="a1e2a-111">result： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="a1e2a-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="a1e2a-112">将保留 $P (x) $ 的定点数。</span><span class="sxs-lookup"><span data-stu-id="a1e2a-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="a1e2a-113">最初必须处于 $ \ket {0} $ 状态。</span><span class="sxs-lookup"><span data-stu-id="a1e2a-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a1e2a-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a1e2a-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

