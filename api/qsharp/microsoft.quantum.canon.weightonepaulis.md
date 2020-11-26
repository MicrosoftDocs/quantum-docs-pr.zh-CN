---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: WeightOnePaulis 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 904c606393131d51eaa44d464ad52bec509eaf72
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204532"
---
# <a name="weightonepaulis-function"></a><span data-ttu-id="97f33-102">WeightOnePaulis 函数</span><span class="sxs-lookup"><span data-stu-id="97f33-102">WeightOnePaulis function</span></span>

<span data-ttu-id="97f33-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="97f33-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="97f33-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="97f33-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="97f33-105">返回给定数量的 qubits 上的所有 Pauli 运算符的数组。</span><span class="sxs-lookup"><span data-stu-id="97f33-105">Returns an array of all weight-1 Pauli operators on a given number of qubits.</span></span>

```qsharp
function WeightOnePaulis (nQubits : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="97f33-106">输入</span><span class="sxs-lookup"><span data-stu-id="97f33-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="97f33-107">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="97f33-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="97f33-108">在其上定义返回的 Pauli 运算符的 qubits 的数目。</span><span class="sxs-lookup"><span data-stu-id="97f33-108">The number of qubits on which the returned Pauli operators are defined.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="97f33-109">Output： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="97f33-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="97f33-110">多 qubit Pauli 运算符的数组，其中每个运算符都表示为长度为的数组 `nQubits` 。</span><span class="sxs-lookup"><span data-stu-id="97f33-110">An array of multi-qubit Pauli operators, each of which is represented as an array with length `nQubits`.</span></span>