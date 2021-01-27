---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: ComputeReciprocalFxP 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: db7425f1a8a9b5ddfdc6b123dad003298e3670e6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843247"
---
# <a name="computereciprocalfxp-operation"></a><span data-ttu-id="9b78f-102">ComputeReciprocalFxP 操作</span><span class="sxs-lookup"><span data-stu-id="9b78f-102">ComputeReciprocalFxP operation</span></span>

<span data-ttu-id="9b78f-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9b78f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9b78f-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="9b78f-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="9b78f-105">计算固定点数字的 $ 1/x $ $x $。</span><span class="sxs-lookup"><span data-stu-id="9b78f-105">Computes $1/x$ for a fixed-point number $x$.</span></span>

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9b78f-106">输入</span><span class="sxs-lookup"><span data-stu-id="9b78f-106">Input</span></span>

### <a name="x--fixedpoint"></a><span data-ttu-id="9b78f-107">x： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="9b78f-107">x : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="9b78f-108">要反转的固定点数字。</span><span class="sxs-lookup"><span data-stu-id="9b78f-108">Fixed-point number to be inverted.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="9b78f-109">result： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="9b78f-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="9b78f-110">将保存结果的定点数。</span><span class="sxs-lookup"><span data-stu-id="9b78f-110">Fixed-point number that will hold the result.</span></span> <span data-ttu-id="9b78f-111">必须初始化为 $ \ket{0.0} $。</span><span class="sxs-lookup"><span data-stu-id="9b78f-111">Must be initialized to $\ket{0.0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9b78f-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9b78f-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

