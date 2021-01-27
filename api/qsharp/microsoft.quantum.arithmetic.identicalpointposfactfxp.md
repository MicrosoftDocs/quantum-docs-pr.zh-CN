---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: IdenticalPointPosFactFxP 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 7212f918e1d0ee86b12b85caa6e0c27bc2cebe58
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846616"
---
# <a name="identicalpointposfactfxp-function"></a><span data-ttu-id="08f7e-102">IdenticalPointPosFactFxP 函数</span><span class="sxs-lookup"><span data-stu-id="08f7e-102">IdenticalPointPosFactFxP function</span></span>

<span data-ttu-id="08f7e-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="08f7e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="08f7e-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="08f7e-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="08f7e-105">断言当从最小有效位进行计数时，提供的数组中的所有固定点都具有相同的点位置。</span><span class="sxs-lookup"><span data-stu-id="08f7e-105">Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit.</span></span> <span data-ttu-id="08f7e-106">也就是说，对于数组中的所有固定点，位数减去点的位数必须是常量。</span><span class="sxs-lookup"><span data-stu-id="08f7e-106">I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.</span></span>

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a><span data-ttu-id="08f7e-107">输入</span><span class="sxs-lookup"><span data-stu-id="08f7e-107">Input</span></span>

### <a name="fixedpoints--fixedpoint"></a><span data-ttu-id="08f7e-108">fixedPoints： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span><span class="sxs-lookup"><span data-stu-id="08f7e-108">fixedPoints : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span></span>

<span data-ttu-id="08f7e-109">将使用断言) 检查兼容性 (的量程固定点数的数组。</span><span class="sxs-lookup"><span data-stu-id="08f7e-109">Array of quantum fixed-point numbers that will be checked for compatibility (using assertions).</span></span>



## <a name="output--unit"></a><span data-ttu-id="08f7e-110">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="08f7e-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

