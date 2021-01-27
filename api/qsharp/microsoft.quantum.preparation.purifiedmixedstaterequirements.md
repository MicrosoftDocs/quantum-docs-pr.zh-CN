---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements
title: PurifiedMixedStateRequirements 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateRequirements
qsharp.summary: Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".
ms.openlocfilehash: 6ddb48ba66eea87a07d515ff791bfb34f2d98b76
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856835"
---
# <a name="purifiedmixedstaterequirements-function"></a><span data-ttu-id="cfe81-102">PurifiedMixedStateRequirements 函数</span><span class="sxs-lookup"><span data-stu-id="cfe81-102">PurifiedMixedStateRequirements function</span></span>

<span data-ttu-id="cfe81-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="cfe81-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="cfe81-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cfe81-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cfe81-105">返回必须分配的 qubits 总数，以应用返回的操作 @"microsoft.quantum.preparation.purifiedmixedstate" 。</span><span class="sxs-lookup"><span data-stu-id="cfe81-105">Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".</span></span>

```qsharp
function PurifiedMixedStateRequirements (targetError : Double, nCoefficients : Int) : Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
```


## <a name="input"></a><span data-ttu-id="cfe81-106">输入</span><span class="sxs-lookup"><span data-stu-id="cfe81-106">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="cfe81-107">targetError： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cfe81-107">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cfe81-108">目标错误 $ \epsilon $。</span><span class="sxs-lookup"><span data-stu-id="cfe81-108">The target error $\epsilon$.</span></span>


### <a name="ncoefficients--int"></a><span data-ttu-id="cfe81-109">nCoefficients： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cfe81-109">nCoefficients : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cfe81-110">准备混合状态时要指定的系数数。</span><span class="sxs-lookup"><span data-stu-id="cfe81-110">The number of coefficients to be specified in preparing a mixed state.</span></span>



## <a name="output--mixedstatepreparationrequirements"></a><span data-ttu-id="cfe81-111">输出： [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)</span><span class="sxs-lookup"><span data-stu-id="cfe81-111">Output : [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)</span></span>

<span data-ttu-id="cfe81-112">描述对每个函数所使用的 qubits 和每个索引和垃圾寄存器的总计 @"microsoft.quantum.preparation.purifiedmixedstate" 。</span><span class="sxs-lookup"><span data-stu-id="cfe81-112">A description of how many qubits are required in total, and for each of the index and garbage registers used by the @"microsoft.quantum.preparation.purifiedmixedstate" function.</span></span>

## <a name="see-also"></a><span data-ttu-id="cfe81-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cfe81-113">See Also</span></span>

- [<span data-ttu-id="cfe81-114">PurifiedMixedState。</span><span class="sxs-lookup"><span data-stu-id="cfe81-114">Microsoft.Quantum.Preparation.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)