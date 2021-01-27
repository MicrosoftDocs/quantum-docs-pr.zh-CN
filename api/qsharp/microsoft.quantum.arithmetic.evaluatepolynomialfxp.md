---
uid: Microsoft.Quantum.Arithmetic.EvaluatePolynomialFxP
title: EvaluatePolynomialFxP 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluatePolynomialFxP
qsharp.summary: Evaluates a polynomial in a fixed-point representation.
ms.openlocfilehash: d88f9002f4ce39b6a16091837c76168fb3a2f086
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843223"
---
# <a name="evaluatepolynomialfxp-operation"></a><span data-ttu-id="429c0-102">EvaluatePolynomialFxP 操作</span><span class="sxs-lookup"><span data-stu-id="429c0-102">EvaluatePolynomialFxP operation</span></span>

<span data-ttu-id="429c0-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="429c0-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="429c0-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="429c0-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="429c0-105">计算定点表示形式的多项式。</span><span class="sxs-lookup"><span data-stu-id="429c0-105">Evaluates a polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluatePolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="429c0-106">输入</span><span class="sxs-lookup"><span data-stu-id="429c0-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="429c0-107">系数： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="429c0-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="429c0-108">多项式的系数为 double 数组，即数组 $ [a_0，a_1，...，a_d] $ for 多项式 $P (x) = a_0 + a_1 x + \cdots + a_d x ^ d $。</span><span class="sxs-lookup"><span data-stu-id="429c0-108">Coefficients of the polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_d]$ for the polynomial $P(x) = a_0 + a_1 x + \cdots + a_d x^d$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="429c0-109">fpx： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="429c0-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="429c0-110">为其计算多项式的定点数。</span><span class="sxs-lookup"><span data-stu-id="429c0-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="429c0-111">result： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="429c0-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="429c0-112">将保留 $P (x) $ 的定点数。</span><span class="sxs-lookup"><span data-stu-id="429c0-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="429c0-113">最初必须处于 $ \ket {0} $ 状态。</span><span class="sxs-lookup"><span data-stu-id="429c0-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="429c0-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="429c0-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

