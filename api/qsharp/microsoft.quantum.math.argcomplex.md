---
uid: Microsoft.Quantum.Math.ArgComplex
title: ArgComplex 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: 629aa32ad80e5aa3d6f5ff75ac65df9b1a96fc15
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700508"
---
# <a name="argcomplex-function"></a><span data-ttu-id="d9543-102">ArgComplex 函数</span><span class="sxs-lookup"><span data-stu-id="d9543-102">ArgComplex function</span></span>

<span data-ttu-id="d9543-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="d9543-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="d9543-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d9543-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d9543-105">返回类型为的复数的相位 `Complex` 。</span><span class="sxs-lookup"><span data-stu-id="d9543-105">Returns the phase of a complex number of type `Complex`.</span></span>

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a><span data-ttu-id="d9543-106">输入</span><span class="sxs-lookup"><span data-stu-id="d9543-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="d9543-107">输入： [复杂](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="d9543-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="d9543-108">复数 $c = x + i y $。</span><span class="sxs-lookup"><span data-stu-id="d9543-108">Complex number $c = x + i y$.</span></span>



## <a name="output--double"></a><span data-ttu-id="d9543-109">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d9543-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d9543-110">阶段 $ \text{Arg} [c] = \text{ArcTan} (y，x) \in (-\pi，\pi] $。</span><span class="sxs-lookup"><span data-stu-id="d9543-110">Phase $\text{Arg}[c] = \text{ArcTan}(y,x) \in (-\pi,\pi]$.</span></span>