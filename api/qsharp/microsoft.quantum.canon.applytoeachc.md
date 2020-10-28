---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: ApplyToEachC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: dfa18b6eb7a2c42fa2982994a2fc92170b52599c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696253"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="f43ba-102">ApplyToEachC 操作</span><span class="sxs-lookup"><span data-stu-id="f43ba-102">ApplyToEachC operation</span></span>

<span data-ttu-id="f43ba-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f43ba-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f43ba-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f43ba-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f43ba-105">对寄存器中的每个元素应用 qubit 操作。</span><span class="sxs-lookup"><span data-stu-id="f43ba-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="f43ba-106">修饰符 `C` 指示 qubit 操作可控制。</span><span class="sxs-lookup"><span data-stu-id="f43ba-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="f43ba-107">输入</span><span class="sxs-lookup"><span data-stu-id="f43ba-107">Input</span></span>

### <a name="singleelementoperation--t--unit-ctl"></a><span data-ttu-id="f43ba-108">singleElementOperation：不等于> [单元](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="f43ba-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="f43ba-109">要应用到每个 qubit 的操作。</span><span class="sxs-lookup"><span data-stu-id="f43ba-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="f43ba-110">注册： t []</span><span class="sxs-lookup"><span data-stu-id="f43ba-110">register : 'T[]</span></span>

<span data-ttu-id="f43ba-111">要在其上应用给定操作的 qubits 数组。</span><span class="sxs-lookup"><span data-stu-id="f43ba-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f43ba-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f43ba-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f43ba-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="f43ba-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f43ba-114">找</span><span class="sxs-lookup"><span data-stu-id="f43ba-114">'T</span></span>

<span data-ttu-id="f43ba-115">操作的目标。</span><span class="sxs-lookup"><span data-stu-id="f43ba-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="f43ba-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f43ba-116">See Also</span></span>

- [<span data-ttu-id="f43ba-117">Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="f43ba-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)