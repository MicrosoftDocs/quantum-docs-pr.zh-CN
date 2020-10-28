---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: SetToBasisState 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: bb40ddcf6518a30f5d88eec21cf8e2c2d6e0bbaf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700909"
---
# <a name="settobasisstate-operation"></a><span data-ttu-id="3ae89-102">SetToBasisState 操作</span><span class="sxs-lookup"><span data-stu-id="3ae89-102">SetToBasisState operation</span></span>

<span data-ttu-id="3ae89-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="3ae89-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="3ae89-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3ae89-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3ae89-105">通过测量 qubit 并在需要时应用位翻转，将 qubit 设置为给定的计算基础状态。</span><span class="sxs-lookup"><span data-stu-id="3ae89-105">Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.</span></span>

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="3ae89-106">输入</span><span class="sxs-lookup"><span data-stu-id="3ae89-106">Input</span></span>

### <a name="desired--__invalidresult__"></a><span data-ttu-id="3ae89-107">desired： __无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="3ae89-107">desired : __invalid<Result>__</span></span>

<span data-ttu-id="3ae89-108">应将 qubit 设置为的基本状态。</span><span class="sxs-lookup"><span data-stu-id="3ae89-108">The basis state that the qubit should be set to.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="3ae89-109">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3ae89-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3ae89-110">要设置其状态的 qubit。</span><span class="sxs-lookup"><span data-stu-id="3ae89-110">The qubit whose state is to be set.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3ae89-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3ae89-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3ae89-112">注解</span><span class="sxs-lookup"><span data-stu-id="3ae89-112">Remarks</span></span>

<span data-ttu-id="3ae89-113">作为此操作的固定条件， `M(q)` `SetToBasisState(result, q)` 将返回之后立即调用 `result` 。</span><span class="sxs-lookup"><span data-stu-id="3ae89-113">As an invariant of this operation, calling `M(q)` immediately after `SetToBasisState(result, q)` will return `result`.</span></span>