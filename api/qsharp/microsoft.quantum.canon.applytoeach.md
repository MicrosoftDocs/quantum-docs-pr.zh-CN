---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: ApplyToEach 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: e1625829e2e9efd9d39fe0692f01c1cbbffc651c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696257"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="ae291-102">ApplyToEach 操作</span><span class="sxs-lookup"><span data-stu-id="ae291-102">ApplyToEach operation</span></span>

<span data-ttu-id="ae291-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ae291-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ae291-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ae291-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ae291-105">对寄存器中的每个元素应用 qubit 操作。</span><span class="sxs-lookup"><span data-stu-id="ae291-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="ae291-106">输入</span><span class="sxs-lookup"><span data-stu-id="ae291-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="ae291-107">singleElementOperation：不等于> [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ae291-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ae291-108">要应用到每个 qubit 的操作。</span><span class="sxs-lookup"><span data-stu-id="ae291-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="ae291-109">注册： t []</span><span class="sxs-lookup"><span data-stu-id="ae291-109">register : 'T[]</span></span>

<span data-ttu-id="ae291-110">要在其上应用给定操作的 qubits 数组。</span><span class="sxs-lookup"><span data-stu-id="ae291-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ae291-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ae291-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ae291-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="ae291-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ae291-113">找</span><span class="sxs-lookup"><span data-stu-id="ae291-113">'T</span></span>

<span data-ttu-id="ae291-114">操作的目标。</span><span class="sxs-lookup"><span data-stu-id="ae291-114">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae291-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae291-115">See Also</span></span>

- [<span data-ttu-id="ae291-116">Canon. ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="ae291-116">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="ae291-117">Canon. ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="ae291-117">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="ae291-118">Canon. ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="ae291-118">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)