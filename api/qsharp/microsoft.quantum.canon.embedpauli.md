---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: e9042ca9eac4b8791057037dc5698eb14deadd31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207031"
---
# <a name="embedpauli-function"></a><span data-ttu-id="49a79-102">EmbedPauli 函数</span><span class="sxs-lookup"><span data-stu-id="49a79-102">EmbedPauli function</span></span>

<span data-ttu-id="49a79-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="49a79-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="49a79-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="49a79-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="49a79-105">给定 qubit Pauli 运算符和 qubit 的索引后，将返回一个多 qubit Pauli 运算符，该运算符具有给定的单一 qubit 运算符，位于该索引处和 `PauliI` 其他每个索引处。</span><span class="sxs-lookup"><span data-stu-id="49a79-105">Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.</span></span>

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="49a79-106">输入</span><span class="sxs-lookup"><span data-stu-id="49a79-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="49a79-107">pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="49a79-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="49a79-108">要放在给定位置的 qubit Pauli 运算符。</span><span class="sxs-lookup"><span data-stu-id="49a79-108">A single-qubit Pauli operator to be placed at the given location.</span></span>


### <a name="location--int"></a><span data-ttu-id="49a79-109">位置： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="49a79-109">location : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="49a79-110">一个索引 `output[location] == pauli` ，其中， `output` 是此函数的输出。</span><span class="sxs-lookup"><span data-stu-id="49a79-110">An index such that `output[location] == pauli`, where `output` is the output of this function.</span></span>


### <a name="n--int"></a><span data-ttu-id="49a79-111">n： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="49a79-111">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="49a79-112">要返回的数组的长度。</span><span class="sxs-lookup"><span data-stu-id="49a79-112">Length of the array to be returned.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="49a79-113">Output： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="49a79-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

