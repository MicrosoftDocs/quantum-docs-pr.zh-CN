---
uid: Microsoft.Quantum.Simulation.PauliStringFromGenIdx
title: PauliStringFromGenIdx 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliStringFromGenIdx
qsharp.summary: Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: a937dc648c5de5a5f6de7da996448af497b92185
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230304"
---
# <a name="paulistringfromgenidx-function"></a><span data-ttu-id="b6c66-102">PauliStringFromGenIdx 函数</span><span class="sxs-lookup"><span data-stu-id="b6c66-102">PauliStringFromGenIdx function</span></span>

<span data-ttu-id="b6c66-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="b6c66-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="b6c66-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b6c66-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b6c66-105">提取 Pauli 字符串及其 qubit 的 Pauli 术语的索引 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="b6c66-105">Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliStringFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : (Pauli[], Int[])
```


## <a name="input"></a><span data-ttu-id="b6c66-106">输入</span><span class="sxs-lookup"><span data-stu-id="b6c66-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="b6c66-107">generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="b6c66-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="b6c66-108">`GeneratorIndex` 对 Pauli 术语进行编码的类型。</span><span class="sxs-lookup"><span data-stu-id="b6c66-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--pauliint"></a><span data-ttu-id="b6c66-109">Output： ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[]，[Int](xref:microsoft.quantum.lang-ref.int)[] ) </span><span class="sxs-lookup"><span data-stu-id="b6c66-109">Output : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

<span data-ttu-id="b6c66-110">由描述的术语的 Pauli 字符串 `GeneratorIndex` ，以及它处理的 qubits 的索引。</span><span class="sxs-lookup"><span data-stu-id="b6c66-110">The Pauli string of the term described by a `GeneratorIndex`, and indices to the qubits it acts on.</span></span>