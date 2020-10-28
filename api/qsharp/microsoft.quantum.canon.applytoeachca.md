---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: ApplyToEachCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: b24fbb8c7a1a55c0a7750c5d096a61f4824dadfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696251"
---
# <a name="applytoeachca-operation"></a><span data-ttu-id="a0ee4-102">ApplyToEachCA 操作</span><span class="sxs-lookup"><span data-stu-id="a0ee4-102">ApplyToEachCA operation</span></span>

<span data-ttu-id="a0ee4-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a0ee4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a0ee4-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a0ee4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a0ee4-105">对寄存器中的每个元素应用 qubit 操作。</span><span class="sxs-lookup"><span data-stu-id="a0ee4-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="a0ee4-106">修饰符 `CA` 指示 qubit 操作可控制和 adjointable。</span><span class="sxs-lookup"><span data-stu-id="a0ee4-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a0ee4-107">输入</span><span class="sxs-lookup"><span data-stu-id="a0ee4-107">Input</span></span>

### <a name="singleelementoperation--t--unit-adj--ctl"></a><span data-ttu-id="a0ee4-108">singleElementOperation：不等于> [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="a0ee4-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="a0ee4-109">要应用到每个 qubit 的操作。</span><span class="sxs-lookup"><span data-stu-id="a0ee4-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="a0ee4-110">注册： t []</span><span class="sxs-lookup"><span data-stu-id="a0ee4-110">register : 'T[]</span></span>

<span data-ttu-id="a0ee4-111">要在其上应用给定操作的 qubits 数组。</span><span class="sxs-lookup"><span data-stu-id="a0ee4-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a0ee4-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a0ee4-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a0ee4-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="a0ee4-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a0ee4-114">找</span><span class="sxs-lookup"><span data-stu-id="a0ee4-114">'T</span></span>

<span data-ttu-id="a0ee4-115">操作的目标。</span><span class="sxs-lookup"><span data-stu-id="a0ee4-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="a0ee4-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0ee4-116">See Also</span></span>

- [<span data-ttu-id="a0ee4-117">Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="a0ee4-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)