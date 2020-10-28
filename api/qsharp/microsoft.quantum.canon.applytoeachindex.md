---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: ApplyToEachIndex 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 4ce184b34add9238e26f9b35b40ec0bddb23ccf9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696250"
---
# <a name="applytoeachindex-operation"></a><span data-ttu-id="19a64-102">ApplyToEachIndex 操作</span><span class="sxs-lookup"><span data-stu-id="19a64-102">ApplyToEachIndex operation</span></span>

<span data-ttu-id="19a64-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="19a64-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="19a64-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="19a64-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="19a64-105">将单 qubit 操作应用于寄存器中的每个索引元素。</span><span class="sxs-lookup"><span data-stu-id="19a64-105">Applies a single-qubit operation to each indexed element in a register.</span></span>

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="19a64-106">输入</span><span class="sxs-lookup"><span data-stu-id="19a64-106">Input</span></span>

### <a name="singleelementoperation--intt--unit"></a><span data-ttu-id="19a64-107">singleElementOperation： ([Int](xref:microsoft.quantum.lang-ref.int)，t) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="19a64-107">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="19a64-108">要应用到每个 qubit 的操作。</span><span class="sxs-lookup"><span data-stu-id="19a64-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="19a64-109">注册： t []</span><span class="sxs-lookup"><span data-stu-id="19a64-109">register : 'T[]</span></span>

<span data-ttu-id="19a64-110">要在其上应用给定操作的 qubits 数组。</span><span class="sxs-lookup"><span data-stu-id="19a64-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="19a64-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="19a64-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="19a64-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="19a64-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="19a64-113">找</span><span class="sxs-lookup"><span data-stu-id="19a64-113">'T</span></span>

<span data-ttu-id="19a64-114">每个操作操作的目标。</span><span class="sxs-lookup"><span data-stu-id="19a64-114">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="19a64-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19a64-115">See Also</span></span>

- [<span data-ttu-id="19a64-116">Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="19a64-116">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [<span data-ttu-id="19a64-117">Canon. ApplyToEachIndexA</span><span class="sxs-lookup"><span data-stu-id="19a64-117">Microsoft.Quantum.Canon.ApplyToEachIndexA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [<span data-ttu-id="19a64-118">Canon. ApplyToEachIndexC</span><span class="sxs-lookup"><span data-stu-id="19a64-118">Microsoft.Quantum.Canon.ApplyToEachIndexC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [<span data-ttu-id="19a64-119">Canon. ApplyToEachIndexCA</span><span class="sxs-lookup"><span data-stu-id="19a64-119">Microsoft.Quantum.Canon.ApplyToEachIndexCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)