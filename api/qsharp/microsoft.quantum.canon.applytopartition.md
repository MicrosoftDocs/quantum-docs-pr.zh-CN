---
uid: Microsoft.Quantum.Canon.ApplyToPartition
title: ApplyToPartition 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartition
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts.
ms.openlocfilehash: c1f43e7936fc1c18fb665388e9892dc3b74cdd05
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696193"
---
# <a name="applytopartition-operation"></a><span data-ttu-id="53605-102">ApplyToPartition 操作</span><span class="sxs-lookup"><span data-stu-id="53605-102">ApplyToPartition operation</span></span>

<span data-ttu-id="53605-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="53605-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="53605-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="53605-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="53605-105">将一对操作应用于寄存器的给定分区分为两部分。</span><span class="sxs-lookup"><span data-stu-id="53605-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>

```qsharp
operation ApplyToPartition (op : ((Qubit[], Qubit[]) => Unit), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="53605-106">输入</span><span class="sxs-lookup"><span data-stu-id="53605-106">Input</span></span>

### <a name="op--qubitqubit--unit"></a><span data-ttu-id="53605-107">op： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[]，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) => [单位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="53605-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="53605-108">要应用于给定分区的一对操作。</span><span class="sxs-lookup"><span data-stu-id="53605-108">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="53605-109">numberOfQubitsToFirstArgument： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="53605-109">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="53605-110">要放入分区第一部分中的 qubits 的数目。</span><span class="sxs-lookup"><span data-stu-id="53605-110">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="53605-111">其余的 qubits 构成分区的第二部分。</span><span class="sxs-lookup"><span data-stu-id="53605-111">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="53605-112">target： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="53605-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="53605-113">给定的两个操作正在进行分区和操作的 qubits 的寄存器。</span><span class="sxs-lookup"><span data-stu-id="53605-113">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="53605-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="53605-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="53605-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53605-115">See Also</span></span>

- [<span data-ttu-id="53605-116">Canon. ApplyToPartitionA</span><span class="sxs-lookup"><span data-stu-id="53605-116">Microsoft.Quantum.Canon.ApplyToPartitionA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionA)
- [<span data-ttu-id="53605-117">Canon. ApplyToPartitionC</span><span class="sxs-lookup"><span data-stu-id="53605-117">Microsoft.Quantum.Canon.ApplyToPartitionC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionC)
- [<span data-ttu-id="53605-118">Canon. ApplyToPartitionCA</span><span class="sxs-lookup"><span data-stu-id="53605-118">Microsoft.Quantum.Canon.ApplyToPartitionCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionCA)