---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterA
title: ApplyToSubregisterA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterA
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: e0c546b768320ce43e7b44242d15838194e1089d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696176"
---
# <a name="applytosubregistera-operation"></a><span data-ttu-id="05759-102">ApplyToSubregisterA 操作</span><span class="sxs-lookup"><span data-stu-id="05759-102">ApplyToSubregisterA operation</span></span>

<span data-ttu-id="05759-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="05759-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="05759-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="05759-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="05759-105">将操作应用于寄存器的 subregister，其 qubits 由其索引数组指定。</span><span class="sxs-lookup"><span data-stu-id="05759-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="05759-106">修饰符 `A` 指示操作为 adjointable。</span><span class="sxs-lookup"><span data-stu-id="05759-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToSubregisterA (op : (Qubit[] => Unit is Adj), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="05759-107">输入</span><span class="sxs-lookup"><span data-stu-id="05759-107">Input</span></span>

### <a name="op--qubit--unit-adj"></a><span data-ttu-id="05759-108">op： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="05759-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="05759-109">要应用到 subregister 的操作。</span><span class="sxs-lookup"><span data-stu-id="05759-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="05759-110">idxs： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="05759-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="05759-111">索引数组，指示将应用操作的 qubits。</span><span class="sxs-lookup"><span data-stu-id="05759-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="05759-112">target： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="05759-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="05759-113">注册操作所针对的。</span><span class="sxs-lookup"><span data-stu-id="05759-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="05759-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="05759-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="05759-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05759-115">See Also</span></span>

- [<span data-ttu-id="05759-116">Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="05759-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)