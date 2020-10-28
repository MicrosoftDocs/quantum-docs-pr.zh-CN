---
uid: Microsoft.Quantum.Math.AbsComplex
title: AbsComplex 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplex
qsharp.summary: Returns the absolute value of a complex number of type `Complex`.
ms.openlocfilehash: d47e04616d4bcf49273bec31fc22990a8244962b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700685"
---
# <a name="abscomplex-function"></a><span data-ttu-id="ff906-102">AbsComplex 函数</span><span class="sxs-lookup"><span data-stu-id="ff906-102">AbsComplex function</span></span>

<span data-ttu-id="ff906-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="ff906-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="ff906-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ff906-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ff906-105">返回类型的复数的绝对值 `Complex` 。</span><span class="sxs-lookup"><span data-stu-id="ff906-105">Returns the absolute value of a complex number of type `Complex`.</span></span>

```qsharp
function AbsComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a><span data-ttu-id="ff906-106">输入</span><span class="sxs-lookup"><span data-stu-id="ff906-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="ff906-107">输入： [复杂](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="ff906-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="ff906-108">复数 $c = x + i y $。</span><span class="sxs-lookup"><span data-stu-id="ff906-108">Complex number $c = x + i y$.</span></span>



## <a name="output--double"></a><span data-ttu-id="ff906-109">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ff906-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ff906-110">绝对值 $ | c |= \sqrt{x ^ 2 + y ^ 2} $。</span><span class="sxs-lookup"><span data-stu-id="ff906-110">Absolute value $|c| = \sqrt{x^2 + y^2}$.</span></span>