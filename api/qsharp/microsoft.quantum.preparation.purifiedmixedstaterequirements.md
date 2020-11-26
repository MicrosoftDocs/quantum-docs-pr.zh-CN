---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements
title: PurifiedMixedStateRequirements 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateRequirements
qsharp.summary: Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".
ms.openlocfilehash: 9b8861a4112c4e6c9db994339353c771a3de81a6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229981"
---
# <a name="purifiedmixedstaterequirements-function"></a><span data-ttu-id="60aa8-102">PurifiedMixedStateRequirements 函数</span><span class="sxs-lookup"><span data-stu-id="60aa8-102">PurifiedMixedStateRequirements function</span></span>

<span data-ttu-id="60aa8-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="60aa8-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="60aa8-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="60aa8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="60aa8-105">返回必须分配的 qubits 总数，以应用返回的操作 @"microsoft.quantum.preparation.purifiedmixedstate" 。</span><span class="sxs-lookup"><span data-stu-id="60aa8-105">Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".</span></span>

```qsharp
function PurifiedMixedStateRequirements (targetError : Double, nCoefficients : Int) : Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
```


## <a name="input"></a><span data-ttu-id="60aa8-106">输入</span><span class="sxs-lookup"><span data-stu-id="60aa8-106">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="60aa8-107">targetError： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="60aa8-107">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="60aa8-108">目标错误 $ \epsilon $。</span><span class="sxs-lookup"><span data-stu-id="60aa8-108">The target error $\epsilon$.</span></span>


### <a name="ncoefficients--int"></a><span data-ttu-id="60aa8-109">nCoefficients： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="60aa8-109">nCoefficients : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="60aa8-110">准备混合状态时要指定的系数数。</span><span class="sxs-lookup"><span data-stu-id="60aa8-110">The number of coefficients to be specified in preparing a mixed state.</span></span>



## <a name="output--mixedstatepreparationrequirements"></a><span data-ttu-id="60aa8-111">输出： [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)</span><span class="sxs-lookup"><span data-stu-id="60aa8-111">Output : [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)</span></span>

<span data-ttu-id="60aa8-112">描述对每个函数所使用的 qubits 和每个索引和垃圾寄存器的总计 @"microsoft.quantum.preparation.purifiedmixedstate" 。</span><span class="sxs-lookup"><span data-stu-id="60aa8-112">A description of how many qubits are required in total, and for each of the index and garbage registers used by the @"microsoft.quantum.preparation.purifiedmixedstate" function.</span></span>

## <a name="see-also"></a><span data-ttu-id="60aa8-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60aa8-113">See Also</span></span>

- [<span data-ttu-id="60aa8-114">PurifiedMixedState。</span><span class="sxs-lookup"><span data-stu-id="60aa8-114">Microsoft.Quantum.Preparation.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)