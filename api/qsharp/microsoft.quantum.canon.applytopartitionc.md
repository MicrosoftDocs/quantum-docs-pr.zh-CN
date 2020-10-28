---
uid: Microsoft.Quantum.Canon.ApplyToPartitionC
title: ApplyToPartitionC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionC
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 840c93c653d71af1a82fb0dc51d9e056176ba88b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696189"
---
# <a name="applytopartitionc-operation"></a><span data-ttu-id="6e078-102">ApplyToPartitionC 操作</span><span class="sxs-lookup"><span data-stu-id="6e078-102">ApplyToPartitionC operation</span></span>

<span data-ttu-id="6e078-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6e078-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6e078-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6e078-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6e078-105">将一对操作应用于寄存器的给定分区分为两部分。</span><span class="sxs-lookup"><span data-stu-id="6e078-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>
<span data-ttu-id="6e078-106">修饰符 `C` 指示操作可控制。</span><span class="sxs-lookup"><span data-stu-id="6e078-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToPartitionC (op : ((Qubit[], Qubit[]) => Unit is Ctl), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="6e078-107">输入</span><span class="sxs-lookup"><span data-stu-id="6e078-107">Input</span></span>

### <a name="op--qubitqubit--unit-ctl"></a><span data-ttu-id="6e078-108">op： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[]，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="6e078-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="6e078-109">要应用于给定分区的一对操作。</span><span class="sxs-lookup"><span data-stu-id="6e078-109">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="6e078-110">numberOfQubitsToFirstArgument： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6e078-110">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6e078-111">要放入分区第一部分中的 qubits 的数目。</span><span class="sxs-lookup"><span data-stu-id="6e078-111">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="6e078-112">其余的 qubits 构成分区的第二部分。</span><span class="sxs-lookup"><span data-stu-id="6e078-112">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="6e078-113">target： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6e078-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6e078-114">给定的两个操作正在进行分区和操作的 qubits 的寄存器。</span><span class="sxs-lookup"><span data-stu-id="6e078-114">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6e078-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6e078-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="6e078-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e078-116">See Also</span></span>

- [<span data-ttu-id="6e078-117">Canon. ApplyToPartition</span><span class="sxs-lookup"><span data-stu-id="6e078-117">Microsoft.Quantum.Canon.ApplyToPartition</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartition)