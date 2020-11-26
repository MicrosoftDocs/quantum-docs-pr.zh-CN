---
uid: Microsoft.Quantum.Math.AbsComplexPolar
title: AbsComplexPolar 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplexPolar
qsharp.summary: Returns the absolute value of a complex number of type `ComplexPolar`.
ms.openlocfilehash: 01845556cbabde768f9c7c47c733453048df9416
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195981"
---
# <a name="abscomplexpolar-function"></a><span data-ttu-id="0a10b-102">AbsComplexPolar 函数</span><span class="sxs-lookup"><span data-stu-id="0a10b-102">AbsComplexPolar function</span></span>

<span data-ttu-id="0a10b-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="0a10b-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="0a10b-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0a10b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0a10b-105">返回类型的复数的绝对值 `ComplexPolar` 。</span><span class="sxs-lookup"><span data-stu-id="0a10b-105">Returns the absolute value of a complex number of type `ComplexPolar`.</span></span>

```qsharp
function AbsComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a><span data-ttu-id="0a10b-106">输入</span><span class="sxs-lookup"><span data-stu-id="0a10b-106">Input</span></span>

### <a name="input--complexpolar"></a><span data-ttu-id="0a10b-107">输入： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="0a10b-107">input : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="0a10b-108">复数 $c = r e ^ {i t} $。</span><span class="sxs-lookup"><span data-stu-id="0a10b-108">Complex number $c = r e^{i t}$.</span></span>



## <a name="output--double"></a><span data-ttu-id="0a10b-109">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0a10b-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0a10b-110">绝对值 $ | c |= r $。</span><span class="sxs-lookup"><span data-stu-id="0a10b-110">Absolute value $|c| = r$.</span></span>