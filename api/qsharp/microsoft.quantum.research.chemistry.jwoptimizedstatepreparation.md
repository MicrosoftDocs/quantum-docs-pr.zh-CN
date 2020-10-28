---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedStatePreparation
title: JWOptimizedStatePreparation 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedStatePreparation
qsharp.summary: Simple state preparation of trial state by occupying spin-orbitals
ms.openlocfilehash: 70154eeb5477c474acbb47d7f6417e42b515371e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695283"
---
# <a name="jwoptimizedstatepreparation-operation"></a><span data-ttu-id="f337c-102">JWOptimizedStatePreparation 操作</span><span class="sxs-lookup"><span data-stu-id="f337c-102">JWOptimizedStatePreparation operation</span></span>

<span data-ttu-id="f337c-103">命名空间： [...](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f337c-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="f337c-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f337c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f337c-105">通过使用 orbitals 来准备试验状态的简单状态</span><span class="sxs-lookup"><span data-stu-id="f337c-105">Simple state preparation of trial state by occupying spin-orbitals</span></span>

```qsharp
operation JWOptimizedStatePreparation (qubitIndices : Int[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="f337c-106">输入</span><span class="sxs-lookup"><span data-stu-id="f337c-106">Input</span></span>

### <a name="qubitindices--int"></a><span data-ttu-id="f337c-107">qubitIndices： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f337c-107">qubitIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f337c-108">要由电子占用的 qubits 的索引。</span><span class="sxs-lookup"><span data-stu-id="f337c-108">Indices of qubits to be occupied by electrons.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="f337c-109">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f337c-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f337c-110">Hamiltonian 的 Qubits。</span><span class="sxs-lookup"><span data-stu-id="f337c-110">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f337c-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f337c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

