---
uid: Microsoft.Quantum.Arithmetic.SquareFxP
title: SquareFxP 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareFxP
qsharp.summary: Squares a fixed-point number.
ms.openlocfilehash: ba0364d7c649c2a949fc52f89409a5280f71a82f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842917"
---
# <a name="squarefxp-operation"></a><span data-ttu-id="0a8df-102">SquareFxP 操作</span><span class="sxs-lookup"><span data-stu-id="0a8df-102">SquareFxP operation</span></span>

<span data-ttu-id="0a8df-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0a8df-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0a8df-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="0a8df-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="0a8df-105">将定点数值作为平方。</span><span class="sxs-lookup"><span data-stu-id="0a8df-105">Squares a fixed-point number.</span></span>

```qsharp
operation SquareFxP (fp : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0a8df-106">输入</span><span class="sxs-lookup"><span data-stu-id="0a8df-106">Input</span></span>

### <a name="fp--fixedpoint"></a><span data-ttu-id="0a8df-107">fp： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="0a8df-107">fp : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="0a8df-108">固定点数字。</span><span class="sxs-lookup"><span data-stu-id="0a8df-108">Fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="0a8df-109">result： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="0a8df-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="0a8df-110">结果固定点数字，最初必须处于状态 $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="0a8df-110">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0a8df-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0a8df-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

