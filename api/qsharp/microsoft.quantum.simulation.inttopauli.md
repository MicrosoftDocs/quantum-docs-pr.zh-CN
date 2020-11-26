---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: IntToPauli 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: 18edb600f7b5b33c7ad98e78e32903c570082225
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229199"
---
# <a name="inttopauli-function"></a><span data-ttu-id="0d7e0-102">IntToPauli 函数</span><span class="sxs-lookup"><span data-stu-id="0d7e0-102">IntToPauli function</span></span>

<span data-ttu-id="0d7e0-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="0d7e0-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="0d7e0-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0d7e0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0d7e0-105">将整数转换为 qubit Pauli 运算符。</span><span class="sxs-lookup"><span data-stu-id="0d7e0-105">Converts a integer to a single-qubit Pauli operator.</span></span>

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a><span data-ttu-id="0d7e0-106">输入</span><span class="sxs-lookup"><span data-stu-id="0d7e0-106">Input</span></span>

### <a name="idx--int"></a><span data-ttu-id="0d7e0-107">idx： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0d7e0-107">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0d7e0-108">`0..3`要转换为 Pauli 运算符的范围内的整数。</span><span class="sxs-lookup"><span data-stu-id="0d7e0-108">Integer in the range `0..3` to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="0d7e0-109">输出： [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="0d7e0-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="0d7e0-110">`Pauli`给定的运算符 `[PauliI, PauliX, PauliY, PauliZ][idx]` 。</span><span class="sxs-lookup"><span data-stu-id="0d7e0-110">A `Pauli` operator given by `[PauliI, PauliX, PauliY, PauliZ][idx]`.</span></span>