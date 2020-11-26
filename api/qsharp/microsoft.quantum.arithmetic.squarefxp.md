---
uid: Microsoft.Quantum.Arithmetic.SquareFxP
title: SquareFxP 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareFxP
qsharp.summary: Squares a fixed-point number.
ms.openlocfilehash: 8d08cb51e3a7ae892b23be0adbb7cdf3ee0f4de5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221872"
---
# <a name="squarefxp-operation"></a><span data-ttu-id="f0d56-102">SquareFxP 操作</span><span class="sxs-lookup"><span data-stu-id="f0d56-102">SquareFxP operation</span></span>

<span data-ttu-id="f0d56-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f0d56-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f0d56-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="f0d56-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="f0d56-105">将定点数值作为平方。</span><span class="sxs-lookup"><span data-stu-id="f0d56-105">Squares a fixed-point number.</span></span>

```qsharp
operation SquareFxP (fp : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f0d56-106">输入</span><span class="sxs-lookup"><span data-stu-id="f0d56-106">Input</span></span>

### <a name="fp--fixedpoint"></a><span data-ttu-id="f0d56-107">fp： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="f0d56-107">fp : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="f0d56-108">固定点数字。</span><span class="sxs-lookup"><span data-stu-id="f0d56-108">Fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="f0d56-109">result： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="f0d56-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="f0d56-110">结果固定点数字，最初必须处于状态 $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="f0d56-110">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f0d56-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f0d56-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

