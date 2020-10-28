---
uid: Microsoft.Quantum.Math.ContinuedFractionConvergentI
title: ContinuedFractionConvergentI 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ContinuedFractionConvergentI
qsharp.summary: Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`
ms.openlocfilehash: 2322e005a5afb73d9719eb65d9ebf50740f1c9fc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700484"
---
# <a name="continuedfractionconvergenti-function"></a><span data-ttu-id="10976-102">ContinuedFractionConvergentI 函数</span><span class="sxs-lookup"><span data-stu-id="10976-102">ContinuedFractionConvergentI function</span></span>

<span data-ttu-id="10976-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="10976-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="10976-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="10976-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="10976-105">查找最接近于 `fraction` 分母小于或等于的连续分数收敛性 `denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="10976-105">Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>

```qsharp
function ContinuedFractionConvergentI (fraction : Microsoft.Quantum.Math.Fraction, denominatorBound : Int) : Microsoft.Quantum.Math.Fraction
```


## <a name="input"></a><span data-ttu-id="10976-106">输入</span><span class="sxs-lookup"><span data-stu-id="10976-106">Input</span></span>

### <a name="fraction--fraction"></a><span data-ttu-id="10976-107">分式： [分数](xref:Microsoft.Quantum.Math.Fraction)</span><span class="sxs-lookup"><span data-stu-id="10976-107">fraction : [Fraction](xref:Microsoft.Quantum.Math.Fraction)</span></span>




### <a name="denominatorbound--int"></a><span data-ttu-id="10976-108">denominatorBound： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="10976-108">denominatorBound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--fraction"></a><span data-ttu-id="10976-109">输出： [分数](xref:Microsoft.Quantum.Math.Fraction)</span><span class="sxs-lookup"><span data-stu-id="10976-109">Output : [Fraction](xref:Microsoft.Quantum.Math.Fraction)</span></span>

<span data-ttu-id="10976-110">最接近的分数， `fraction` 分母小于或等于 `denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="10976-110">Continued fraction closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>