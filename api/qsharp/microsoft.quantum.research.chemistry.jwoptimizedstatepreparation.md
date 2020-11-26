---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedStatePreparation
title: JWOptimizedStatePreparation 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedStatePreparation
qsharp.summary: Simple state preparation of trial state by occupying spin-orbitals
ms.openlocfilehash: a2e0c24eaa1f5326f2d531b4e7e55b2c440bc795
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229845"
---
# <a name="jwoptimizedstatepreparation-operation"></a><span data-ttu-id="fed33-102">JWOptimizedStatePreparation 操作</span><span class="sxs-lookup"><span data-stu-id="fed33-102">JWOptimizedStatePreparation operation</span></span>

<span data-ttu-id="fed33-103">命名空间： [...](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="fed33-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="fed33-104">包： [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="fed33-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="fed33-105">通过使用 orbitals 来准备试验状态的简单状态</span><span class="sxs-lookup"><span data-stu-id="fed33-105">Simple state preparation of trial state by occupying spin-orbitals</span></span>

```qsharp
operation JWOptimizedStatePreparation (qubitIndices : Int[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="fed33-106">输入</span><span class="sxs-lookup"><span data-stu-id="fed33-106">Input</span></span>

### <a name="qubitindices--int"></a><span data-ttu-id="fed33-107">qubitIndices： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="fed33-107">qubitIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="fed33-108">要由电子占用的 qubits 的索引。</span><span class="sxs-lookup"><span data-stu-id="fed33-108">Indices of qubits to be occupied by electrons.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="fed33-109">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="fed33-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="fed33-110">Hamiltonian 的 Qubits。</span><span class="sxs-lookup"><span data-stu-id="fed33-110">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fed33-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fed33-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

