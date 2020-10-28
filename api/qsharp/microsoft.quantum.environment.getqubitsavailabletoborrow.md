---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: GetQubitsAvailableToBorrow 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow. This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.
ms.openlocfilehash: cb56ce4aefd7a03c0f0827b8d34688ef17988f56
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695542"
---
# <a name="getqubitsavailabletoborrow-operation"></a><span data-ttu-id="db3cb-102">GetQubitsAvailableToBorrow 操作</span><span class="sxs-lookup"><span data-stu-id="db3cb-102">GetQubitsAvailableToBorrow operation</span></span>

<span data-ttu-id="db3cb-103">命名空间 [：](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="db3cb-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="db3cb-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="db3cb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="db3cb-105">返回当前可用于借用的 qubits 的数目。</span><span class="sxs-lookup"><span data-stu-id="db3cb-105">Returns the number of qubits currently available to borrow.</span></span>
<span data-ttu-id="db3cb-106">这包括未使用的 qubits;也就是说，这包括由返回的 qubits `GetQubitsAvailableToUse` 。</span><span class="sxs-lookup"><span data-stu-id="db3cb-106">This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.</span></span>

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a><span data-ttu-id="db3cb-107">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="db3cb-107">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="db3cb-108">可在语句中分配的 qubits 的数目 `borrowing` 。</span><span class="sxs-lookup"><span data-stu-id="db3cb-108">The number of qubits that could be allocated in a `borrowing` statement.</span></span>
<span data-ttu-id="db3cb-109">如果正在使用的目标计算机未提供此信息，则 `-1` 返回。</span><span class="sxs-lookup"><span data-stu-id="db3cb-109">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="db3cb-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db3cb-110">See Also</span></span>

- [<span data-ttu-id="db3cb-111">GetQubitsAvailableToUse。</span><span class="sxs-lookup"><span data-stu-id="db3cb-111">Microsoft.Quantum.Environment.GetQubitsAvailableToUse</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)