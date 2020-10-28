---
uid: Microsoft.Quantum.Arithmetic.EvaluateOddPolynomialFxP
title: EvaluateOddPolynomialFxP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateOddPolynomialFxP
qsharp.summary: Evaluates an odd polynomial in a fixed-point representation.
ms.openlocfilehash: d52da4092f16d43ab9d08b03f798a4d6789c7348
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699892"
---
# <a name="evaluateoddpolynomialfxp-operation"></a><span data-ttu-id="6fada-102">EvaluateOddPolynomialFxP 操作</span><span class="sxs-lookup"><span data-stu-id="6fada-102">EvaluateOddPolynomialFxP operation</span></span>

<span data-ttu-id="6fada-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6fada-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6fada-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6fada-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6fada-105">计算定点表示形式的奇多项式。</span><span class="sxs-lookup"><span data-stu-id="6fada-105">Evaluates an odd polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateOddPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="6fada-106">输入</span><span class="sxs-lookup"><span data-stu-id="6fada-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="6fada-107">系数： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="6fada-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="6fada-108">将奇多项式的系数视为 double 数组，即，数组 $ [a_0，a_1，...，a_k] $ 用于奇多项式 $P (x) = a_0 x + a_1 x ^ 3 + \cdots + a_k x ^ {2k + 1} $。</span><span class="sxs-lookup"><span data-stu-id="6fada-108">Coefficients of the odd polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the odd polynomial $P(x) = a_0 x + a_1 x^3 + \cdots + a_k x^{2k+1}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="6fada-109">fpx： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="6fada-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="6fada-110">为其计算多项式的定点数。</span><span class="sxs-lookup"><span data-stu-id="6fada-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="6fada-111">result： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="6fada-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="6fada-112">用来容纳 P (x) 的固定点数。</span><span class="sxs-lookup"><span data-stu-id="6fada-112">Output fixed-point number which will hold P(x).</span></span> <span data-ttu-id="6fada-113">最初必须处于 $ \ket {0} $ 状态。</span><span class="sxs-lookup"><span data-stu-id="6fada-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6fada-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6fada-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

