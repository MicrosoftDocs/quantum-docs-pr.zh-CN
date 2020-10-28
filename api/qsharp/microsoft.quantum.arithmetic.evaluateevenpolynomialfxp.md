---
uid: Microsoft.Quantum.Arithmetic.EvaluateEvenPolynomialFxP
title: EvaluateEvenPolynomialFxP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateEvenPolynomialFxP
qsharp.summary: Evaluates an even polynomial in a fixed-point representation.
ms.openlocfilehash: e49a6d47553a60766b561525e8cfa37e95fda9e8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699893"
---
# <a name="evaluateevenpolynomialfxp-operation"></a><span data-ttu-id="7a61f-102">EvaluateEvenPolynomialFxP 操作</span><span class="sxs-lookup"><span data-stu-id="7a61f-102">EvaluateEvenPolynomialFxP operation</span></span>

<span data-ttu-id="7a61f-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7a61f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7a61f-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7a61f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7a61f-105">计算定点表示形式的偶数。</span><span class="sxs-lookup"><span data-stu-id="7a61f-105">Evaluates an even polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateEvenPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="7a61f-106">输入</span><span class="sxs-lookup"><span data-stu-id="7a61f-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="7a61f-107">系数： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="7a61f-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="7a61f-108">作为 double 数组的偶数的系数，即数组 $ [a_0，a_1，...，a_k] $ for 偶数 $P (x) = a_0 + a_1 x ^ 2 + \cdots + a_k x ^ {2k} $。</span><span class="sxs-lookup"><span data-stu-id="7a61f-108">Coefficients of the even polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the even polynomial $P(x) = a_0 + a_1 x^2 + \cdots + a_k x^{2k}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="7a61f-109">fpx： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="7a61f-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="7a61f-110">为其计算多项式的定点数。</span><span class="sxs-lookup"><span data-stu-id="7a61f-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="7a61f-111">result： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="7a61f-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="7a61f-112">将保留 $P (x) $ 的定点数。</span><span class="sxs-lookup"><span data-stu-id="7a61f-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="7a61f-113">最初必须处于 $ \ket {0} $ 状态。</span><span class="sxs-lookup"><span data-stu-id="7a61f-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7a61f-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7a61f-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

