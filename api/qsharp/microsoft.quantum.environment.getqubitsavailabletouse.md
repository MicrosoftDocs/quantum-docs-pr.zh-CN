---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: GetQubitsAvailableToUse 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: ce461b03a08b4c83b9de142c957ce5c590fe9659
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201404"
---
# <a name="getqubitsavailabletouse-operation"></a><span data-ttu-id="139ed-102">GetQubitsAvailableToUse 操作</span><span class="sxs-lookup"><span data-stu-id="139ed-102">GetQubitsAvailableToUse operation</span></span>

<span data-ttu-id="139ed-103">命名空间 [：](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="139ed-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="139ed-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="139ed-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="139ed-105">返回当前可供使用的 qubits 的数目。</span><span class="sxs-lookup"><span data-stu-id="139ed-105">Returns the number of qubits currently available to use.</span></span>

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a><span data-ttu-id="139ed-106">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="139ed-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="139ed-107">可在语句中分配的 qubits 的数目 `using` 。</span><span class="sxs-lookup"><span data-stu-id="139ed-107">The number of qubits that could be allocated in a `using` statement.</span></span>
<span data-ttu-id="139ed-108">如果正在使用的目标计算机未提供此信息，则 `-1` 返回。</span><span class="sxs-lookup"><span data-stu-id="139ed-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="139ed-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="139ed-109">See Also</span></span>

- [<span data-ttu-id="139ed-110">GetQubitsAvailableToBorrow。</span><span class="sxs-lookup"><span data-stu-id="139ed-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)