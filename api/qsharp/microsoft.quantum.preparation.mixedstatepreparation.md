---
uid: Microsoft.Quantum.Preparation.MixedStatePreparation
title: MixedStatePreparation 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: MixedStatePreparation
qsharp.summary: Represents a particular mixed state that can be prepared on an index and a garbage register.
ms.openlocfilehash: 94d6483914b5d21bb51a5469c7123f834e9eb5da
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193567"
---
# <a name="mixedstatepreparation-user-defined-type"></a><span data-ttu-id="ee2f2-102">MixedStatePreparation 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="ee2f2-102">MixedStatePreparation user defined type</span></span>

<span data-ttu-id="ee2f2-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="ee2f2-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="ee2f2-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ee2f2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ee2f2-105">表示可对索引和垃圾寄存器准备的特定混合状态。</span><span class="sxs-lookup"><span data-stu-id="ee2f2-105">Represents a particular mixed state that can be prepared on an index and a garbage register.</span></span>

```qsharp

newtype MixedStatePreparation = (Requirements : Microsoft.Quantum.Preparation.MixedStatePreparationRequirements, Norm : Double, Prepare : ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="ee2f2-106">命名项</span><span class="sxs-lookup"><span data-stu-id="ee2f2-106">Named Items</span></span>

### <a name="requirements--mixedstatepreparationrequirements"></a><span data-ttu-id="ee2f2-107">要求： [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)</span><span class="sxs-lookup"><span data-stu-id="ee2f2-107">Requirements : [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)</span></span>


### <a name="norm--double"></a><span data-ttu-id="ee2f2-108">标准： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ee2f2-108">Norm : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>


### <a name="prepare--littleendianqubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="ee2f2-109">Prepare： ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="ee2f2-109">Prepare : ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>



## <a name="see-also"></a><span data-ttu-id="ee2f2-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee2f2-110">See Also</span></span>

- [<span data-ttu-id="ee2f2-111">PurifiedMixedState</span><span class="sxs-lookup"><span data-stu-id="ee2f2-111">Microsoft.Quantum.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.PurifiedMixedState)