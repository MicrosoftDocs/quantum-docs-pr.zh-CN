---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: IdenticalPointPosFactFxP 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 907e270e1c3710fb346044ad7757171c6d5f568d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223045"
---
# <a name="identicalpointposfactfxp-function"></a><span data-ttu-id="b3aea-102">IdenticalPointPosFactFxP 函数</span><span class="sxs-lookup"><span data-stu-id="b3aea-102">IdenticalPointPosFactFxP function</span></span>

<span data-ttu-id="b3aea-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b3aea-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b3aea-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="b3aea-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="b3aea-105">断言当从最小有效位进行计数时，提供的数组中的所有固定点都具有相同的点位置。</span><span class="sxs-lookup"><span data-stu-id="b3aea-105">Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit.</span></span> <span data-ttu-id="b3aea-106">也就是说，对于数组中的所有固定点，位数减去点的位数必须是常量。</span><span class="sxs-lookup"><span data-stu-id="b3aea-106">I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.</span></span>

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a><span data-ttu-id="b3aea-107">输入</span><span class="sxs-lookup"><span data-stu-id="b3aea-107">Input</span></span>

### <a name="fixedpoints--fixedpoint"></a><span data-ttu-id="b3aea-108">fixedPoints： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span><span class="sxs-lookup"><span data-stu-id="b3aea-108">fixedPoints : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span></span>

<span data-ttu-id="b3aea-109">将使用断言) 检查兼容性 (的量程固定点数的数组。</span><span class="sxs-lookup"><span data-stu-id="b3aea-109">Array of quantum fixed-point numbers that will be checked for compatibility (using assertions).</span></span>



## <a name="output--unit"></a><span data-ttu-id="b3aea-110">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b3aea-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

