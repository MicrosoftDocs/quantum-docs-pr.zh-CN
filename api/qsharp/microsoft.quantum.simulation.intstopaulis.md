---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 6904054bb1aff3a57c80882694b4c217812b2b81
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842224"
---
# <a name="intstopaulis-function"></a><span data-ttu-id="38ee0-102">IntsToPaulis 函数</span><span class="sxs-lookup"><span data-stu-id="38ee0-102">IntsToPaulis function</span></span>

<span data-ttu-id="38ee0-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="38ee0-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="38ee0-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="38ee0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="38ee0-105">将整数数组转换为 qubit Pauli 运算符的数组。</span><span class="sxs-lookup"><span data-stu-id="38ee0-105">Converts an array of integers to an array of single-qubit Pauli operators.</span></span>

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="38ee0-106">输入</span><span class="sxs-lookup"><span data-stu-id="38ee0-106">Input</span></span>

### <a name="ints--int"></a><span data-ttu-id="38ee0-107">整数： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="38ee0-107">ints : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="38ee0-108">要转换为 Pauli 运算符的范围内的整数数组 `0..3`  。</span><span class="sxs-lookup"><span data-stu-id="38ee0-108">Array of integers in the range `0..3`  to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="38ee0-109">Output： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="38ee0-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="38ee0-110">`paulis`Pauli 运算符的数组 `Pauli[]` ，其长度与给定的的 `ints` `paulis[idxPauli]` 元素相等 `[PauliI, PauliX, PauliY, PauliZ]` `ints[idxPauli]` 。</span><span class="sxs-lookup"><span data-stu-id="38ee0-110">An array `paulis` of Pauli operators `Pauli[]` the same length as `ints` such that `paulis[idxPauli]` is equal to the element of `[PauliI, PauliX, PauliY, PauliZ]` given by `ints[idxPauli]`.</span></span>