---
uid: Microsoft.Quantum.Arithmetic.EvaluateEvenPolynomialFxP
title: EvaluateEvenPolynomialFxP 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateEvenPolynomialFxP
qsharp.summary: Evaluates an even polynomial in a fixed-point representation.
ms.openlocfilehash: c3129cb796a344f7ad38a585183db285d48892bf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843233"
---
# <a name="evaluateevenpolynomialfxp-operation"></a><span data-ttu-id="cb215-102">EvaluateEvenPolynomialFxP 操作</span><span class="sxs-lookup"><span data-stu-id="cb215-102">EvaluateEvenPolynomialFxP operation</span></span>

<span data-ttu-id="cb215-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="cb215-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="cb215-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="cb215-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="cb215-105">计算定点表示形式的偶数。</span><span class="sxs-lookup"><span data-stu-id="cb215-105">Evaluates an even polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateEvenPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="cb215-106">输入</span><span class="sxs-lookup"><span data-stu-id="cb215-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="cb215-107">系数： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="cb215-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="cb215-108">作为 double 数组的偶数的系数，即数组 $ [a_0，a_1，...，a_k] $ for 偶数 $P (x) = a_0 + a_1 x ^ 2 + \cdots + a_k x ^ {2k} $。</span><span class="sxs-lookup"><span data-stu-id="cb215-108">Coefficients of the even polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the even polynomial $P(x) = a_0 + a_1 x^2 + \cdots + a_k x^{2k}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="cb215-109">fpx： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="cb215-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="cb215-110">为其计算多项式的定点数。</span><span class="sxs-lookup"><span data-stu-id="cb215-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="cb215-111">result： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="cb215-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="cb215-112">将保留 $P (x) $ 的定点数。</span><span class="sxs-lookup"><span data-stu-id="cb215-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="cb215-113">最初必须处于 $ \ket {0} $ 状态。</span><span class="sxs-lookup"><span data-stu-id="cb215-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cb215-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cb215-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

