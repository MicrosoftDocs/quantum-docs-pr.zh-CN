---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: PermuteQubits 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: 0f4d8819d5b08f4d5370f8fdc407b2eb2a3e5f21
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695981"
---
# <a name="permutequbits-operation"></a><span data-ttu-id="64ad8-102">PermuteQubits 操作</span><span class="sxs-lookup"><span data-stu-id="64ad8-102">PermuteQubits operation</span></span>

<span data-ttu-id="64ad8-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="64ad8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="64ad8-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="64ad8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="64ad8-105">使用交换操作 Permutes qubits。</span><span class="sxs-lookup"><span data-stu-id="64ad8-105">Permutes qubits by using the SWAP operation.</span></span>

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="64ad8-106">输入</span><span class="sxs-lookup"><span data-stu-id="64ad8-106">Input</span></span>

### <a name="ordering--int"></a><span data-ttu-id="64ad8-107">排序： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="64ad8-107">ordering : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="64ad8-108">介绍 qubits 的新排序，其中，索引 i 处的 qubit 现在将按顺序 [i] 排序。</span><span class="sxs-lookup"><span data-stu-id="64ad8-108">Describes the new ordering of the qubits, where the qubit at index i will now be at ordering[i].</span></span>


### <a name="register--qubit"></a><span data-ttu-id="64ad8-109">register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="64ad8-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="64ad8-110">要对其进行操作的 Qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="64ad8-110">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="64ad8-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="64ad8-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

