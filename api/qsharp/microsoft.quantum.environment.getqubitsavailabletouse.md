---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: GetQubitsAvailableToUse 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 25d43d369193fc7453fd5ce9c50769c438a69afb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695541"
---
# <a name="getqubitsavailabletouse-operation"></a><span data-ttu-id="d26c2-102">GetQubitsAvailableToUse 操作</span><span class="sxs-lookup"><span data-stu-id="d26c2-102">GetQubitsAvailableToUse operation</span></span>

<span data-ttu-id="d26c2-103">命名空间 [：](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="d26c2-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="d26c2-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d26c2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d26c2-105">返回当前可供使用的 qubits 的数目。</span><span class="sxs-lookup"><span data-stu-id="d26c2-105">Returns the number of qubits currently available to use.</span></span>

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a><span data-ttu-id="d26c2-106">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d26c2-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d26c2-107">可在语句中分配的 qubits 的数目 `using` 。</span><span class="sxs-lookup"><span data-stu-id="d26c2-107">The number of qubits that could be allocated in a `using` statement.</span></span>
<span data-ttu-id="d26c2-108">如果正在使用的目标计算机未提供此信息，则 `-1` 返回。</span><span class="sxs-lookup"><span data-stu-id="d26c2-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="d26c2-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d26c2-109">See Also</span></span>

- [<span data-ttu-id="d26c2-110">GetQubitsAvailableToBorrow。</span><span class="sxs-lookup"><span data-stu-id="d26c2-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)