---
uid: Microsoft.Quantum.Simulation.PauliStringFromGenIdx
title: PauliStringFromGenIdx 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliStringFromGenIdx
qsharp.summary: Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: 33da4bc3d7e58b87aef75b453b6af09a51214923
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695250"
---
# <a name="paulistringfromgenidx-function"></a><span data-ttu-id="8ec32-102">PauliStringFromGenIdx 函数</span><span class="sxs-lookup"><span data-stu-id="8ec32-102">PauliStringFromGenIdx function</span></span>

<span data-ttu-id="8ec32-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="8ec32-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="8ec32-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8ec32-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8ec32-105">提取 Pauli 字符串及其 qubit 的 Pauli 术语的索引 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="8ec32-105">Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliStringFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : (Pauli[], Int[])
```


## <a name="input"></a><span data-ttu-id="8ec32-106">输入</span><span class="sxs-lookup"><span data-stu-id="8ec32-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="8ec32-107">generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="8ec32-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="8ec32-108">`GeneratorIndex` 对 Pauli 术语进行编码的类型。</span><span class="sxs-lookup"><span data-stu-id="8ec32-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--pauliint"></a><span data-ttu-id="8ec32-109">Output： ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[]，[Int](xref:microsoft.quantum.lang-ref.int)[] ) </span><span class="sxs-lookup"><span data-stu-id="8ec32-109">Output : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

<span data-ttu-id="8ec32-110">由描述的术语的 Pauli 字符串 `GeneratorIndex` ，以及它处理的 qubits 的索引。</span><span class="sxs-lookup"><span data-stu-id="8ec32-110">The Pauli string of the term described by a `GeneratorIndex`, and indices to the qubits it acts on.</span></span>