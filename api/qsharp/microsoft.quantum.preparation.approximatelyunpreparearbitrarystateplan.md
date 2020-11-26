---
uid: Microsoft.Quantum.Preparation.ApproximatelyUnprepareArbitraryStatePlan
title: ApproximatelyUnprepareArbitraryStatePlan 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApproximatelyUnprepareArbitraryStatePlan
qsharp.summary: Implementation step of arbitrary state preparation procedure.
ms.openlocfilehash: 2aab8b7a21ded729e90695c82709901bfacc18e7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226496"
---
# <a name="approximatelyunpreparearbitrarystateplan-function"></a><span data-ttu-id="7e9a0-102">ApproximatelyUnprepareArbitraryStatePlan 函数</span><span class="sxs-lookup"><span data-stu-id="7e9a0-102">ApproximatelyUnprepareArbitraryStatePlan function</span></span>

<span data-ttu-id="7e9a0-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="7e9a0-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="7e9a0-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7e9a0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7e9a0-105">任意状态准备过程的实现步骤。</span><span class="sxs-lookup"><span data-stu-id="7e9a0-105">Implementation step of arbitrary state preparation procedure.</span></span>

```qsharp
function ApproximatelyUnprepareArbitraryStatePlan (tolerance : Double, coefficients : Microsoft.Quantum.Math.ComplexPolar[], (rngControl : Range, idxTarget : Int)) : (Qubit[] => Unit is Adj + Ctl)[]
```


## <a name="input"></a><span data-ttu-id="7e9a0-106">输入</span><span class="sxs-lookup"><span data-stu-id="7e9a0-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="7e9a0-107">容差： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7e9a0-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="coefficients--complexpolar"></a><span data-ttu-id="7e9a0-108">系数： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="7e9a0-108">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>




### <a name="rngcontrol--range"></a><span data-ttu-id="7e9a0-109">rngControl： [Range](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="7e9a0-109">rngControl : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>




### <a name="idxtarget--int"></a><span data-ttu-id="7e9a0-110">idxTarget： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7e9a0-110">idxTarget : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="7e9a0-111">Output： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl []</span><span class="sxs-lookup"><span data-stu-id="7e9a0-111">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>



## <a name="see-also"></a><span data-ttu-id="7e9a0-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e9a0-112">See Also</span></span>

- [<span data-ttu-id="7e9a0-113">PrepareArbitraryState。</span><span class="sxs-lookup"><span data-stu-id="7e9a0-113">Microsoft.Quantum.Preparation.PrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.PrepareArbitraryState)
- [<span data-ttu-id="7e9a0-114">Canon. MultiplexPauli</span><span class="sxs-lookup"><span data-stu-id="7e9a0-114">Microsoft.Quantum.Canon.MultiplexPauli</span></span>](xref:Microsoft.Quantum.Canon.MultiplexPauli)