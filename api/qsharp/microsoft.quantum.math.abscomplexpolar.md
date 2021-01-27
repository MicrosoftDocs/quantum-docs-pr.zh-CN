---
uid: Microsoft.Quantum.Math.AbsComplexPolar
title: AbsComplexPolar 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplexPolar
qsharp.summary: Returns the absolute value of a complex number of type `ComplexPolar`.
ms.openlocfilehash: c2b60cbdf69723dfc1470535dbc5beb060e68b86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856403"
---
# <a name="abscomplexpolar-function"></a><span data-ttu-id="cea84-102">AbsComplexPolar 函数</span><span class="sxs-lookup"><span data-stu-id="cea84-102">AbsComplexPolar function</span></span>

<span data-ttu-id="cea84-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="cea84-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="cea84-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cea84-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cea84-105">返回类型的复数的绝对值 `ComplexPolar` 。</span><span class="sxs-lookup"><span data-stu-id="cea84-105">Returns the absolute value of a complex number of type `ComplexPolar`.</span></span>

```qsharp
function AbsComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a><span data-ttu-id="cea84-106">输入</span><span class="sxs-lookup"><span data-stu-id="cea84-106">Input</span></span>

### <a name="input--complexpolar"></a><span data-ttu-id="cea84-107">输入： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="cea84-107">input : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="cea84-108">复数 $c = r e ^ {i t} $。</span><span class="sxs-lookup"><span data-stu-id="cea84-108">Complex number $c = r e^{i t}$.</span></span>



## <a name="output--double"></a><span data-ttu-id="cea84-109">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cea84-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cea84-110">绝对值 $ | c |= r $。</span><span class="sxs-lookup"><span data-stu-id="cea84-110">Absolute value $|c| = r$.</span></span>