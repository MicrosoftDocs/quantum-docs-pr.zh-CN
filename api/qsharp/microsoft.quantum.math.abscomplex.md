---
uid: Microsoft.Quantum.Math.AbsComplex
title: AbsComplex 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplex
qsharp.summary: Returns the absolute value of a complex number of type `Complex`.
ms.openlocfilehash: d9afb4b9b37b6cdd83bfd3829d3174d769c5f41b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211383"
---
# <a name="abscomplex-function"></a><span data-ttu-id="d8c19-102">AbsComplex 函数</span><span class="sxs-lookup"><span data-stu-id="d8c19-102">AbsComplex function</span></span>

<span data-ttu-id="d8c19-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="d8c19-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="d8c19-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d8c19-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d8c19-105">返回类型的复数的绝对值 `Complex` 。</span><span class="sxs-lookup"><span data-stu-id="d8c19-105">Returns the absolute value of a complex number of type `Complex`.</span></span>

```qsharp
function AbsComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a><span data-ttu-id="d8c19-106">输入</span><span class="sxs-lookup"><span data-stu-id="d8c19-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="d8c19-107">输入： [复杂](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="d8c19-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="d8c19-108">复数 $c = x + i y $。</span><span class="sxs-lookup"><span data-stu-id="d8c19-108">Complex number $c = x + i y$.</span></span>



## <a name="output--double"></a><span data-ttu-id="d8c19-109">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d8c19-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d8c19-110">绝对值 $ | c |= \sqrt{x ^ 2 + y ^ 2} $。</span><span class="sxs-lookup"><span data-stu-id="d8c19-110">Absolute value $|c| = \sqrt{x^2 + y^2}$.</span></span>