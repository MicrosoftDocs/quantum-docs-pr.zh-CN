---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: ComputeReciprocalFxP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: e8f31d82fc69a3d7f4b571c4a679255dffc28b7f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699909"
---
# <a name="computereciprocalfxp-operation"></a><span data-ttu-id="1e01c-102">ComputeReciprocalFxP 操作</span><span class="sxs-lookup"><span data-stu-id="1e01c-102">ComputeReciprocalFxP operation</span></span>

<span data-ttu-id="1e01c-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1e01c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1e01c-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1e01c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1e01c-105">计算固定点数字的 $ 1/x $ $x $。</span><span class="sxs-lookup"><span data-stu-id="1e01c-105">Computes $1/x$ for a fixed-point number $x$.</span></span>

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="1e01c-106">输入</span><span class="sxs-lookup"><span data-stu-id="1e01c-106">Input</span></span>

### <a name="x--fixedpoint"></a><span data-ttu-id="1e01c-107">x： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="1e01c-107">x : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="1e01c-108">要反转的固定点数字。</span><span class="sxs-lookup"><span data-stu-id="1e01c-108">Fixed-point number to be inverted.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="1e01c-109">result： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="1e01c-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="1e01c-110">将保存结果的定点数。</span><span class="sxs-lookup"><span data-stu-id="1e01c-110">Fixed-point number that will hold the result.</span></span> <span data-ttu-id="1e01c-111">必须初始化为 $ \ket{0.0} $。</span><span class="sxs-lookup"><span data-stu-id="1e01c-111">Must be initialized to $\ket{0.0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1e01c-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1e01c-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

