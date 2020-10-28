---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterC
title: ApplyToSubregisterC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterC
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: ba5be1e7e822197eb76aac029be8617a70d51ddb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696173"
---
# <a name="applytosubregisterc-operation"></a><span data-ttu-id="f2d21-102">ApplyToSubregisterC 操作</span><span class="sxs-lookup"><span data-stu-id="f2d21-102">ApplyToSubregisterC operation</span></span>

<span data-ttu-id="f2d21-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f2d21-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f2d21-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f2d21-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f2d21-105">将操作应用于寄存器的 subregister，其 qubits 由其索引数组指定。</span><span class="sxs-lookup"><span data-stu-id="f2d21-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="f2d21-106">修饰符 `C` 指示操作可控制。</span><span class="sxs-lookup"><span data-stu-id="f2d21-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="f2d21-107">输入</span><span class="sxs-lookup"><span data-stu-id="f2d21-107">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="f2d21-108">op： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="f2d21-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="f2d21-109">要应用到 subregister 的操作。</span><span class="sxs-lookup"><span data-stu-id="f2d21-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="f2d21-110">idxs： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f2d21-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f2d21-111">索引数组，指示将应用操作的 qubits。</span><span class="sxs-lookup"><span data-stu-id="f2d21-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="f2d21-112">target： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f2d21-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f2d21-113">注册操作所针对的。</span><span class="sxs-lookup"><span data-stu-id="f2d21-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f2d21-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f2d21-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="f2d21-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2d21-115">See Also</span></span>

- [<span data-ttu-id="f2d21-116">Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="f2d21-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)