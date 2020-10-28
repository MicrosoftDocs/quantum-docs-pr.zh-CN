---
uid: Microsoft.Quantum.Canon.ApplyToPartitionA
title: ApplyToPartitionA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionA
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 6ff3bf8b5a4344ee5a7a054c6285a5492260068d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696191"
---
# <a name="applytopartitiona-operation"></a><span data-ttu-id="92d78-102">ApplyToPartitionA 操作</span><span class="sxs-lookup"><span data-stu-id="92d78-102">ApplyToPartitionA operation</span></span>

<span data-ttu-id="92d78-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="92d78-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="92d78-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="92d78-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="92d78-105">将一对操作应用于寄存器的给定分区分为两部分。</span><span class="sxs-lookup"><span data-stu-id="92d78-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>
<span data-ttu-id="92d78-106">修饰符 `A` 指示操作为 adjointable。</span><span class="sxs-lookup"><span data-stu-id="92d78-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToPartitionA (op : ((Qubit[], Qubit[]) => Unit is Adj), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="92d78-107">输入</span><span class="sxs-lookup"><span data-stu-id="92d78-107">Input</span></span>

### <a name="op--qubitqubit--unit-adj"></a><span data-ttu-id="92d78-108">op： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[]，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="92d78-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="92d78-109">要应用于给定分区的一对操作。</span><span class="sxs-lookup"><span data-stu-id="92d78-109">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="92d78-110">numberOfQubitsToFirstArgument： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="92d78-110">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="92d78-111">要放入分区第一部分中的 qubits 的数目。</span><span class="sxs-lookup"><span data-stu-id="92d78-111">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="92d78-112">其余的 qubits 构成分区的第二部分。</span><span class="sxs-lookup"><span data-stu-id="92d78-112">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="92d78-113">target： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="92d78-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="92d78-114">给定的两个操作正在进行分区和操作的 qubits 的寄存器。</span><span class="sxs-lookup"><span data-stu-id="92d78-114">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="92d78-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="92d78-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="92d78-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92d78-116">See Also</span></span>

- [<span data-ttu-id="92d78-117">Canon. ApplyToPartition</span><span class="sxs-lookup"><span data-stu-id="92d78-117">Microsoft.Quantum.Canon.ApplyToPartition</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartition)