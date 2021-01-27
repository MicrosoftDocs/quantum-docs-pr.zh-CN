---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: MultiplyFxP 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 776ccb7a9e1ba1a34b28da6e1cf3a0aafe9da76b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843052"
---
# <a name="multiplyfxp-operation"></a><span data-ttu-id="ac685-102">MultiplyFxP 操作</span><span class="sxs-lookup"><span data-stu-id="ac685-102">MultiplyFxP operation</span></span>

<span data-ttu-id="ac685-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ac685-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ac685-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="ac685-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="ac685-105">将量程寄存器中的两个定点数相乘。</span><span class="sxs-lookup"><span data-stu-id="ac685-105">Multiplies two fixed-point numbers in quantum registers.</span></span>

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ac685-106">输入</span><span class="sxs-lookup"><span data-stu-id="ac685-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="ac685-107">fp1： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="ac685-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="ac685-108">第一个固定点号。</span><span class="sxs-lookup"><span data-stu-id="ac685-108">First fixed-point number.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="ac685-109">fp2： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="ac685-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="ac685-110">第二个定点数。</span><span class="sxs-lookup"><span data-stu-id="ac685-110">Second fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="ac685-111">result： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="ac685-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="ac685-112">结果固定点数字，最初必须处于状态 $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="ac685-112">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ac685-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ac685-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ac685-114">备注</span><span class="sxs-lookup"><span data-stu-id="ac685-114">Remarks</span></span>

<span data-ttu-id="ac685-115">当前实现要求三个固定点数字具有相同的点位置和相同数量的 qubits。</span><span class="sxs-lookup"><span data-stu-id="ac685-115">The current implementation requires the three fixed-point numbers to have the same point position and the same number of qubits.</span></span>