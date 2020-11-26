---
uid: Microsoft.Quantum.Math.Lg
title: Lg 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Lg
qsharp.summary: Computes the base-2 logarithm of a number.
ms.openlocfilehash: eef4d5b23298250ad6c0553788fca4c88d7836e3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195284"
---
# <a name="lg-function"></a><span data-ttu-id="06e8e-102">Lg 函数</span><span class="sxs-lookup"><span data-stu-id="06e8e-102">Lg function</span></span>

<span data-ttu-id="06e8e-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="06e8e-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="06e8e-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="06e8e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="06e8e-105">计算数字的以2为底的对数。</span><span class="sxs-lookup"><span data-stu-id="06e8e-105">Computes the base-2 logarithm of a number.</span></span>

```qsharp
function Lg (input : Double) : Double
```


## <a name="input"></a><span data-ttu-id="06e8e-106">输入</span><span class="sxs-lookup"><span data-stu-id="06e8e-106">Input</span></span>

### <a name="input--double"></a><span data-ttu-id="06e8e-107">输入： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="06e8e-107">input : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="06e8e-108">实数 $x $。</span><span class="sxs-lookup"><span data-stu-id="06e8e-108">A real number $x$.</span></span>



## <a name="output--double"></a><span data-ttu-id="06e8e-109">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="06e8e-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="06e8e-110">以2为底的对数 $y = \ log_2 (x) $，$x = 2 ^ y $。</span><span class="sxs-lookup"><span data-stu-id="06e8e-110">The base-2 logarithm $y = \log_2(x)$ such that $x = 2^y$.</span></span>