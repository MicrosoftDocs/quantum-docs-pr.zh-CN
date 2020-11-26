---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: SetToBasisState 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: 2612bfe488c830abd835be89b2f8ea6795abf675
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194145"
---
# <a name="settobasisstate-operation"></a><span data-ttu-id="e90ef-102">SetToBasisState 操作</span><span class="sxs-lookup"><span data-stu-id="e90ef-102">SetToBasisState operation</span></span>

<span data-ttu-id="e90ef-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="e90ef-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="e90ef-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e90ef-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e90ef-105">通过测量 qubit 并在需要时应用位翻转，将 qubit 设置为给定的计算基础状态。</span><span class="sxs-lookup"><span data-stu-id="e90ef-105">Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.</span></span>

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="e90ef-106">输入</span><span class="sxs-lookup"><span data-stu-id="e90ef-106">Input</span></span>

### <a name="desired--__invalidresult__"></a><span data-ttu-id="e90ef-107">desired：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="e90ef-107">desired : __invalid<Result>__</span></span>

<span data-ttu-id="e90ef-108">应将 qubit 设置为的基本状态。</span><span class="sxs-lookup"><span data-stu-id="e90ef-108">The basis state that the qubit should be set to.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="e90ef-109">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e90ef-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e90ef-110">要设置其状态的 qubit。</span><span class="sxs-lookup"><span data-stu-id="e90ef-110">The qubit whose state is to be set.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e90ef-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e90ef-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e90ef-112">备注</span><span class="sxs-lookup"><span data-stu-id="e90ef-112">Remarks</span></span>

<span data-ttu-id="e90ef-113">作为此操作的固定条件， `M(q)` `SetToBasisState(result, q)` 将返回之后立即调用 `result` 。</span><span class="sxs-lookup"><span data-stu-id="e90ef-113">As an invariant of this operation, calling `M(q)` immediately after `SetToBasisState(result, q)` will return `result`.</span></span>