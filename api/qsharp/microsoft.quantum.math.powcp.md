---
uid: Microsoft.Quantum.Math.PowCP
title: PowCP 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowCP
qsharp.summary: Returns a number raised to a given power.
ms.openlocfilehash: 185d40acff6027a775130faaff64582c58384a90
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194638"
---
# <a name="powcp-function"></a><span data-ttu-id="2ebca-102">PowCP 函数</span><span class="sxs-lookup"><span data-stu-id="2ebca-102">PowCP function</span></span>

<span data-ttu-id="2ebca-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="2ebca-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="2ebca-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2ebca-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2ebca-105">返回一个数的指定幂。</span><span class="sxs-lookup"><span data-stu-id="2ebca-105">Returns a number raised to a given power.</span></span>

```qsharp
function PowCP (a : Microsoft.Quantum.Math.ComplexPolar, power : Microsoft.Quantum.Math.ComplexPolar) : Microsoft.Quantum.Math.ComplexPolar
```


## <a name="input"></a><span data-ttu-id="2ebca-106">输入</span><span class="sxs-lookup"><span data-stu-id="2ebca-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="2ebca-107">答： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="2ebca-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="2ebca-108">要引发 $a $ 的数字。</span><span class="sxs-lookup"><span data-stu-id="2ebca-108">The number $a$ that is to be raised.</span></span>


### <a name="power--complexpolar"></a><span data-ttu-id="2ebca-109">电源： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="2ebca-109">power : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="2ebca-110">$A $ 应引发的 power $b $。</span><span class="sxs-lookup"><span data-stu-id="2ebca-110">The power $b$ to which $a$ should be raised.</span></span>



## <a name="output--complexpolar"></a><span data-ttu-id="2ebca-111">输出： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="2ebca-111">Output : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="2ebca-112">Power $a ^ b $</span><span class="sxs-lookup"><span data-stu-id="2ebca-112">The power $a^b$</span></span>