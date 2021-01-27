---
uid: Microsoft.Quantum.Math.ArgComplex
title: ArgComplex 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: e8ce73a43940ab0ed66338f962cc6f76fc2b694b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842757"
---
# <a name="argcomplex-function"></a><span data-ttu-id="b4971-102">ArgComplex 函数</span><span class="sxs-lookup"><span data-stu-id="b4971-102">ArgComplex function</span></span>

<span data-ttu-id="b4971-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b4971-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b4971-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b4971-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b4971-105">返回类型为的复数的相位 `Complex` 。</span><span class="sxs-lookup"><span data-stu-id="b4971-105">Returns the phase of a complex number of type `Complex`.</span></span>

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a><span data-ttu-id="b4971-106">输入</span><span class="sxs-lookup"><span data-stu-id="b4971-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="b4971-107">输入： [复杂](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="b4971-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="b4971-108">复数 $c = x + i y $。</span><span class="sxs-lookup"><span data-stu-id="b4971-108">Complex number $c = x + i y$.</span></span>



## <a name="output--double"></a><span data-ttu-id="b4971-109">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b4971-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b4971-110">阶段 $ \text{Arg} [c] = \text{ArcTan} (y，x) \in (-\pi，\pi] $。</span><span class="sxs-lookup"><span data-stu-id="b4971-110">Phase $\text{Arg}[c] = \text{ArcTan}(y,x) \in (-\pi,\pi]$.</span></span>