---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: ApplyToEachC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 535f815503e20b5cee35f3f273a714203a4baf12
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217775"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="3464f-102">ApplyToEachC 操作</span><span class="sxs-lookup"><span data-stu-id="3464f-102">ApplyToEachC operation</span></span>

<span data-ttu-id="3464f-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3464f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3464f-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3464f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3464f-105">对寄存器中的每个元素应用 qubit 操作。</span><span class="sxs-lookup"><span data-stu-id="3464f-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="3464f-106">修饰符 `C` 指示 qubit 操作可控制。</span><span class="sxs-lookup"><span data-stu-id="3464f-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="3464f-107">输入</span><span class="sxs-lookup"><span data-stu-id="3464f-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-ctl"></a><span data-ttu-id="3464f-108">singleElementOperation： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="3464f-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="3464f-109">要应用到每个 qubit 的操作。</span><span class="sxs-lookup"><span data-stu-id="3464f-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="3464f-110">注册： t []</span><span class="sxs-lookup"><span data-stu-id="3464f-110">register : 'T[]</span></span>

<span data-ttu-id="3464f-111">要在其上应用给定操作的 qubits 数组。</span><span class="sxs-lookup"><span data-stu-id="3464f-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3464f-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3464f-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3464f-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="3464f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3464f-114">找</span><span class="sxs-lookup"><span data-stu-id="3464f-114">'T</span></span>

<span data-ttu-id="3464f-115">操作的目标。</span><span class="sxs-lookup"><span data-stu-id="3464f-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="3464f-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3464f-116">See Also</span></span>

- [<span data-ttu-id="3464f-117">Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="3464f-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)