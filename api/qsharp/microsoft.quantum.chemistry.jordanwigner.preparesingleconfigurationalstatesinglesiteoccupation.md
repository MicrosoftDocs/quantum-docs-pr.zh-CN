---
uid: Microsoft.Quantum.Chemistry.JordanWigner.PrepareSingleConfigurationalStateSingleSiteOccupation
title: PrepareSingleConfigurationalStateSingleSiteOccupation 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: PrepareSingleConfigurationalStateSingleSiteOccupation
qsharp.summary: Simple state preparation of trial state by occupying spin-orbitals
ms.openlocfilehash: de385b7ffd76c1deaa41cf0cd3338d3243feb1fd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695725"
---
# <a name="preparesingleconfigurationalstatesinglesiteoccupation-operation"></a><span data-ttu-id="8da7d-102">PrepareSingleConfigurationalStateSingleSiteOccupation 操作</span><span class="sxs-lookup"><span data-stu-id="8da7d-102">PrepareSingleConfigurationalStateSingleSiteOccupation operation</span></span>

<span data-ttu-id="8da7d-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="8da7d-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="8da7d-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8da7d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8da7d-105">通过使用 orbitals 来准备试验状态的简单状态</span><span class="sxs-lookup"><span data-stu-id="8da7d-105">Simple state preparation of trial state by occupying spin-orbitals</span></span>

```qsharp
operation PrepareSingleConfigurationalStateSingleSiteOccupation (qubitIndices : Int[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="8da7d-106">输入</span><span class="sxs-lookup"><span data-stu-id="8da7d-106">Input</span></span>

### <a name="qubitindices--int"></a><span data-ttu-id="8da7d-107">qubitIndices： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8da7d-107">qubitIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="8da7d-108">要由电子占用的 qubits 的索引。</span><span class="sxs-lookup"><span data-stu-id="8da7d-108">Indices of qubits to be occupied by electrons.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="8da7d-109">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8da7d-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8da7d-110">Hamiltonian 的 Qubits。</span><span class="sxs-lookup"><span data-stu-id="8da7d-110">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8da7d-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8da7d-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

