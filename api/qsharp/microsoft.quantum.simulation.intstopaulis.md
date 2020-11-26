---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 2333dcbd2988480e2b2b9b217b26705f3578de00
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230525"
---
# <a name="intstopaulis-function"></a><span data-ttu-id="950f1-102">IntsToPaulis 函数</span><span class="sxs-lookup"><span data-stu-id="950f1-102">IntsToPaulis function</span></span>

<span data-ttu-id="950f1-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="950f1-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="950f1-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="950f1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="950f1-105">将整数数组转换为 qubit Pauli 运算符的数组。</span><span class="sxs-lookup"><span data-stu-id="950f1-105">Converts an array of integers to an array of single-qubit Pauli operators.</span></span>

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="950f1-106">输入</span><span class="sxs-lookup"><span data-stu-id="950f1-106">Input</span></span>

### <a name="ints--int"></a><span data-ttu-id="950f1-107">整数： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="950f1-107">ints : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="950f1-108">要转换为 Pauli 运算符的范围内的整数数组 `0..3`  。</span><span class="sxs-lookup"><span data-stu-id="950f1-108">Array of integers in the range `0..3`  to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="950f1-109">Output： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="950f1-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="950f1-110">`paulis`Pauli 运算符的数组 `Pauli[]` ，其长度与给定的的 `ints` `paulis[idxPauli]` 元素相等 `[PauliI, PauliX, PauliY, PauliZ]` `ints[idxPauli]` 。</span><span class="sxs-lookup"><span data-stu-id="950f1-110">An array `paulis` of Pauli operators `Pauli[]` the same length as `ints` such that `paulis[idxPauli]` is equal to the element of `[PauliI, PauliX, PauliY, PauliZ]` given by `ints[idxPauli]`.</span></span>