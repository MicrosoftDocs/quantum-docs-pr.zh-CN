---
uid: Microsoft.Quantum.Math.Lg
title: Lg 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Lg
qsharp.summary: Computes the base-2 logarithm of a number.
ms.openlocfilehash: da6548691437ffd9470bc93e6a69c8d38854c984
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851331"
---
# <a name="lg-function"></a><span data-ttu-id="97311-102">Lg 函数</span><span class="sxs-lookup"><span data-stu-id="97311-102">Lg function</span></span>

<span data-ttu-id="97311-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="97311-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="97311-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="97311-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="97311-105">计算数字的以2为底的对数。</span><span class="sxs-lookup"><span data-stu-id="97311-105">Computes the base-2 logarithm of a number.</span></span>

```qsharp
function Lg (input : Double) : Double
```


## <a name="input"></a><span data-ttu-id="97311-106">输入</span><span class="sxs-lookup"><span data-stu-id="97311-106">Input</span></span>

### <a name="input--double"></a><span data-ttu-id="97311-107">输入： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="97311-107">input : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="97311-108">实数 $x $。</span><span class="sxs-lookup"><span data-stu-id="97311-108">A real number $x$.</span></span>



## <a name="output--double"></a><span data-ttu-id="97311-109">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="97311-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="97311-110">以2为底的对数 $y = \ log_2 (x) $，$x = 2 ^ y $。</span><span class="sxs-lookup"><span data-stu-id="97311-110">The base-2 logarithm $y = \log_2(x)$ such that $x = 2^y$.</span></span>