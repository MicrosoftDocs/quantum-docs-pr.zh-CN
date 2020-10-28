---
uid: Microsoft.Quantum.Math.ContinuedFractionConvergentL
title: ContinuedFractionConvergentL 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ContinuedFractionConvergentL
qsharp.summary: Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`
ms.openlocfilehash: a02b38fedb5b0025f04e7bba86f2f998493206b3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700668"
---
# <a name="continuedfractionconvergentl-function"></a><span data-ttu-id="7f5ca-102">ContinuedFractionConvergentL 函数</span><span class="sxs-lookup"><span data-stu-id="7f5ca-102">ContinuedFractionConvergentL function</span></span>

<span data-ttu-id="7f5ca-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="7f5ca-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="7f5ca-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7f5ca-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7f5ca-105">查找最接近于 `fraction` 分母小于或等于的连续分数收敛性 `denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="7f5ca-105">Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>

```qsharp
function ContinuedFractionConvergentL (fraction : Microsoft.Quantum.Math.BigFraction, denominatorBound : BigInt) : Microsoft.Quantum.Math.BigFraction
```


## <a name="input"></a><span data-ttu-id="7f5ca-106">输入</span><span class="sxs-lookup"><span data-stu-id="7f5ca-106">Input</span></span>

### <a name="fraction--bigfraction"></a><span data-ttu-id="7f5ca-107">分数： [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span><span class="sxs-lookup"><span data-stu-id="7f5ca-107">fraction : [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span></span>




### <a name="denominatorbound--bigint"></a><span data-ttu-id="7f5ca-108">denominatorBound： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="7f5ca-108">denominatorBound : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigfraction"></a><span data-ttu-id="7f5ca-109">输出： [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span><span class="sxs-lookup"><span data-stu-id="7f5ca-109">Output : [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span></span>

<span data-ttu-id="7f5ca-110">最接近的分数， `fraction` 分母小于或等于 `denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="7f5ca-110">Continued fraction closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>