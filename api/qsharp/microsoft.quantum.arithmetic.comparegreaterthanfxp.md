---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: CompareGreaterThanFxP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: bd3bcedd7a4a81fc600f7f4b6bdf1d2a797abbd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699925"
---
# <a name="comparegreaterthanfxp-operation"></a><span data-ttu-id="771fc-102">CompareGreaterThanFxP 操作</span><span class="sxs-lookup"><span data-stu-id="771fc-102">CompareGreaterThanFxP operation</span></span>

<span data-ttu-id="771fc-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="771fc-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="771fc-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="771fc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="771fc-105">比较量程寄存器中存储的两个固定点数字，并控制对结果的反向。</span><span class="sxs-lookup"><span data-stu-id="771fc-105">Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.</span></span>

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="771fc-106">输入</span><span class="sxs-lookup"><span data-stu-id="771fc-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="771fc-107">fp1： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="771fc-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="771fc-108">要比较的第一个固定点数字。</span><span class="sxs-lookup"><span data-stu-id="771fc-108">First fixed-point number to be compared.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="771fc-109">fp2： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="771fc-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="771fc-110">要比较的第二个定点数字。</span><span class="sxs-lookup"><span data-stu-id="771fc-110">Second fixed-point number to be compared.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="771fc-111">result： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="771fc-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="771fc-112">比较的结果。</span><span class="sxs-lookup"><span data-stu-id="771fc-112">Result of the comparison.</span></span> <span data-ttu-id="771fc-113">如果为，则将翻转 `fp1 > fp2` 。</span><span class="sxs-lookup"><span data-stu-id="771fc-113">Will be flipped if `fp1 > fp2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="771fc-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="771fc-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="771fc-115">注解</span><span class="sxs-lookup"><span data-stu-id="771fc-115">Remarks</span></span>

<span data-ttu-id="771fc-116">当前实现要求两个固定点数字具有相同的点位置和相同数量的 qubits。</span><span class="sxs-lookup"><span data-stu-id="771fc-116">The current implementation requires the two fixed-point numbers to have the same point position and the same number of qubits.</span></span>