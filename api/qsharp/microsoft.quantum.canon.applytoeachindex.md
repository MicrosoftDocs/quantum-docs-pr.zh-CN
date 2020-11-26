---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: ApplyToEachIndex 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 746bc19f7a137ef476a25abdabc4737ed6727ff2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217605"
---
# <a name="applytoeachindex-operation"></a><span data-ttu-id="f0154-102">ApplyToEachIndex 操作</span><span class="sxs-lookup"><span data-stu-id="f0154-102">ApplyToEachIndex operation</span></span>

<span data-ttu-id="f0154-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f0154-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f0154-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f0154-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f0154-105">将单 qubit 操作应用于寄存器中的每个索引元素。</span><span class="sxs-lookup"><span data-stu-id="f0154-105">Applies a single-qubit operation to each indexed element in a register.</span></span>

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="f0154-106">输入</span><span class="sxs-lookup"><span data-stu-id="f0154-106">Input</span></span>

### <a name="singleelementoperation--intt--unit"></a><span data-ttu-id="f0154-107">singleElementOperation： ([Int](xref:microsoft.quantum.lang-ref.int)，t) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f0154-107">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f0154-108">要应用到每个 qubit 的操作。</span><span class="sxs-lookup"><span data-stu-id="f0154-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="f0154-109">注册： t []</span><span class="sxs-lookup"><span data-stu-id="f0154-109">register : 'T[]</span></span>

<span data-ttu-id="f0154-110">要在其上应用给定操作的 qubits 数组。</span><span class="sxs-lookup"><span data-stu-id="f0154-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f0154-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f0154-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f0154-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="f0154-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f0154-113">找</span><span class="sxs-lookup"><span data-stu-id="f0154-113">'T</span></span>

<span data-ttu-id="f0154-114">每个操作操作的目标。</span><span class="sxs-lookup"><span data-stu-id="f0154-114">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="f0154-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f0154-115">See Also</span></span>

- [<span data-ttu-id="f0154-116">Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="f0154-116">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [<span data-ttu-id="f0154-117">Canon. ApplyToEachIndexA</span><span class="sxs-lookup"><span data-stu-id="f0154-117">Microsoft.Quantum.Canon.ApplyToEachIndexA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [<span data-ttu-id="f0154-118">Canon. ApplyToEachIndexC</span><span class="sxs-lookup"><span data-stu-id="f0154-118">Microsoft.Quantum.Canon.ApplyToEachIndexC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [<span data-ttu-id="f0154-119">Canon. ApplyToEachIndexCA</span><span class="sxs-lookup"><span data-stu-id="f0154-119">Microsoft.Quantum.Canon.ApplyToEachIndexCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)