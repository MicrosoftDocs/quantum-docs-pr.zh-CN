---
uid: Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
title: MixedStatePreparationRequirements 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: MixedStatePreparationRequirements
qsharp.summary: Represents the number of qubits required in order to prepare a given mixed state.
ms.openlocfilehash: 3ea4757f6aa5125418b1e81db9f32e7b668eb359
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228689"
---
# <a name="mixedstatepreparationrequirements-user-defined-type"></a><span data-ttu-id="71d01-102">MixedStatePreparationRequirements 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="71d01-102">MixedStatePreparationRequirements user defined type</span></span>

<span data-ttu-id="71d01-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="71d01-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="71d01-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="71d01-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="71d01-105">表示准备给定混合状态所需的 qubits 的数目。</span><span class="sxs-lookup"><span data-stu-id="71d01-105">Represents the number of qubits required in order to prepare a given mixed state.</span></span>

```qsharp

newtype MixedStatePreparationRequirements = (NTotalQubits : Int, (NIndexQubits : Int, NGarbageQubits : Int));
```



## <a name="named-items"></a><span data-ttu-id="71d01-106">命名项</span><span class="sxs-lookup"><span data-stu-id="71d01-106">Named Items</span></span>

### <a name="ntotalqubits--int"></a><span data-ttu-id="71d01-107">NTotalQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="71d01-107">NTotalQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


### <a name="nindexqubits--int"></a><span data-ttu-id="71d01-108">NIndexQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="71d01-108">NIndexQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


### <a name="ngarbagequbits--int"></a><span data-ttu-id="71d01-109">NGarbageQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="71d01-109">NGarbageQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="see-also"></a><span data-ttu-id="71d01-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="71d01-110">See Also</span></span>

- [<span data-ttu-id="71d01-111">PurifiedMixedState</span><span class="sxs-lookup"><span data-stu-id="71d01-111">Microsoft.Quantum.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.PurifiedMixedState)