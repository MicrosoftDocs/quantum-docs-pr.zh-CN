---
uid: Microsoft.Quantum.Arithmetic.EvaluateOddPolynomialFxP
title: EvaluateOddPolynomialFxP 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateOddPolynomialFxP
qsharp.summary: Evaluates an odd polynomial in a fixed-point representation.
ms.openlocfilehash: 852e986cd09c3b2e31263f53e381d9da73298415
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846664"
---
# <a name="evaluateoddpolynomialfxp-operation"></a><span data-ttu-id="4cf1f-102">EvaluateOddPolynomialFxP 操作</span><span class="sxs-lookup"><span data-stu-id="4cf1f-102">EvaluateOddPolynomialFxP operation</span></span>

<span data-ttu-id="4cf1f-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4cf1f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4cf1f-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="4cf1f-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="4cf1f-105">计算定点表示形式的奇多项式。</span><span class="sxs-lookup"><span data-stu-id="4cf1f-105">Evaluates an odd polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateOddPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4cf1f-106">输入</span><span class="sxs-lookup"><span data-stu-id="4cf1f-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="4cf1f-107">系数： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="4cf1f-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="4cf1f-108">将奇多项式的系数视为 double 数组，即，数组 $ [a_0，a_1，...，a_k] $ 用于奇多项式 $P (x) = a_0 x + a_1 x ^ 3 + \cdots + a_k x ^ {2k + 1} $。</span><span class="sxs-lookup"><span data-stu-id="4cf1f-108">Coefficients of the odd polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the odd polynomial $P(x) = a_0 x + a_1 x^3 + \cdots + a_k x^{2k+1}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="4cf1f-109">fpx： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="4cf1f-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="4cf1f-110">为其计算多项式的定点数。</span><span class="sxs-lookup"><span data-stu-id="4cf1f-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="4cf1f-111">result： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="4cf1f-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="4cf1f-112">用来容纳 P (x) 的固定点数。</span><span class="sxs-lookup"><span data-stu-id="4cf1f-112">Output fixed-point number which will hold P(x).</span></span> <span data-ttu-id="4cf1f-113">最初必须处于 $ \ket {0} $ 状态。</span><span class="sxs-lookup"><span data-stu-id="4cf1f-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4cf1f-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4cf1f-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

