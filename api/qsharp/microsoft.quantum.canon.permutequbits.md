---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: PermuteQubits 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: deb5fa5b0bc0509c957e01bf22e491ad3e2214f3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205595"
---
# <a name="permutequbits-operation"></a><span data-ttu-id="00933-102">PermuteQubits 操作</span><span class="sxs-lookup"><span data-stu-id="00933-102">PermuteQubits operation</span></span>

<span data-ttu-id="00933-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="00933-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="00933-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="00933-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="00933-105">使用交换操作 Permutes qubits。</span><span class="sxs-lookup"><span data-stu-id="00933-105">Permutes qubits by using the SWAP operation.</span></span>

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="00933-106">输入</span><span class="sxs-lookup"><span data-stu-id="00933-106">Input</span></span>

### <a name="ordering--int"></a><span data-ttu-id="00933-107">排序： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="00933-107">ordering : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="00933-108">介绍 qubits 的新排序，其中，索引 i 处的 qubit 现在将按顺序 [i] 排序。</span><span class="sxs-lookup"><span data-stu-id="00933-108">Describes the new ordering of the qubits, where the qubit at index i will now be at ordering[i].</span></span>


### <a name="register--qubit"></a><span data-ttu-id="00933-109">register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="00933-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="00933-110">要对其进行操作的 Qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="00933-110">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="00933-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="00933-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

