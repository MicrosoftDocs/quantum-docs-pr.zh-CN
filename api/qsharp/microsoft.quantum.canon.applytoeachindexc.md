---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexC
title: ApplyToEachIndexC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexC
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 387d7ea24b9251386a71b42a1f51ce70933bf6fc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696248"
---
# <a name="applytoeachindexc-operation"></a><span data-ttu-id="cb405-102">ApplyToEachIndexC 操作</span><span class="sxs-lookup"><span data-stu-id="cb405-102">ApplyToEachIndexC operation</span></span>

<span data-ttu-id="cb405-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cb405-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cb405-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cb405-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cb405-105">将单 qubit 操作应用于寄存器中的每个索引元素。</span><span class="sxs-lookup"><span data-stu-id="cb405-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="cb405-106">修饰符 `C` 指示 qubit 操作可控制。</span><span class="sxs-lookup"><span data-stu-id="cb405-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachIndexC<'T> (singleElementOperation : ((Int, 'T) => Unit is Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="cb405-107">输入</span><span class="sxs-lookup"><span data-stu-id="cb405-107">Input</span></span>

### <a name="singleelementoperation--intt--unit-ctl"></a><span data-ttu-id="cb405-108">singleElementOperation： ([Int](xref:microsoft.quantum.lang-ref.int)，不) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="cb405-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="cb405-109">要应用到每个 qubit 的操作。</span><span class="sxs-lookup"><span data-stu-id="cb405-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="cb405-110">注册： t []</span><span class="sxs-lookup"><span data-stu-id="cb405-110">register : 'T[]</span></span>

<span data-ttu-id="cb405-111">要在其上应用给定操作的 qubits 数组。</span><span class="sxs-lookup"><span data-stu-id="cb405-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cb405-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cb405-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="cb405-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="cb405-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cb405-114">找</span><span class="sxs-lookup"><span data-stu-id="cb405-114">'T</span></span>

<span data-ttu-id="cb405-115">每个操作操作的目标。</span><span class="sxs-lookup"><span data-stu-id="cb405-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb405-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cb405-116">See Also</span></span>

- [<span data-ttu-id="cb405-117">Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="cb405-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)