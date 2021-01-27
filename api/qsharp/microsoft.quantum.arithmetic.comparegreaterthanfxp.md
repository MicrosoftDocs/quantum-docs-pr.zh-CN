---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: CompareGreaterThanFxP 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: f49c713c8a1e8a6451f2c54fa59a72f00bfbb4c4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843327"
---
# <a name="comparegreaterthanfxp-operation"></a><span data-ttu-id="9f840-102">CompareGreaterThanFxP 操作</span><span class="sxs-lookup"><span data-stu-id="9f840-102">CompareGreaterThanFxP operation</span></span>

<span data-ttu-id="9f840-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9f840-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9f840-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="9f840-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="9f840-105">比较量程寄存器中存储的两个固定点数字，并控制对结果的反向。</span><span class="sxs-lookup"><span data-stu-id="9f840-105">Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.</span></span>

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9f840-106">输入</span><span class="sxs-lookup"><span data-stu-id="9f840-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="9f840-107">fp1： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="9f840-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="9f840-108">要比较的第一个固定点数字。</span><span class="sxs-lookup"><span data-stu-id="9f840-108">First fixed-point number to be compared.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="9f840-109">fp2： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="9f840-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="9f840-110">要比较的第二个定点数字。</span><span class="sxs-lookup"><span data-stu-id="9f840-110">Second fixed-point number to be compared.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="9f840-111">result： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9f840-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9f840-112">比较的结果。</span><span class="sxs-lookup"><span data-stu-id="9f840-112">Result of the comparison.</span></span> <span data-ttu-id="9f840-113">如果为，则将翻转 `fp1 > fp2` 。</span><span class="sxs-lookup"><span data-stu-id="9f840-113">Will be flipped if `fp1 > fp2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9f840-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9f840-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9f840-115">备注</span><span class="sxs-lookup"><span data-stu-id="9f840-115">Remarks</span></span>

<span data-ttu-id="9f840-116">当前实现要求两个固定点数字具有相同的点位置和相同数量的 qubits。</span><span class="sxs-lookup"><span data-stu-id="9f840-116">The current implementation requires the two fixed-point numbers to have the same point position and the same number of qubits.</span></span>