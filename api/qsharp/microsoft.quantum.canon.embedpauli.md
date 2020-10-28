---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: c78406aa4557834ac2bb40cf1847696d075e5135
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696058"
---
# <a name="embedpauli-function"></a><span data-ttu-id="6cb44-102">EmbedPauli 函数</span><span class="sxs-lookup"><span data-stu-id="6cb44-102">EmbedPauli function</span></span>

<span data-ttu-id="6cb44-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6cb44-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6cb44-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6cb44-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6cb44-105">给定 qubit Pauli 运算符和 qubit 的索引后，将返回一个多 qubit Pauli 运算符，该运算符具有给定的单一 qubit 运算符，位于该索引处和 `PauliI` 其他每个索引处。</span><span class="sxs-lookup"><span data-stu-id="6cb44-105">Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.</span></span>

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="6cb44-106">输入</span><span class="sxs-lookup"><span data-stu-id="6cb44-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="6cb44-107">pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="6cb44-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="6cb44-108">要放在给定位置的 qubit Pauli 运算符。</span><span class="sxs-lookup"><span data-stu-id="6cb44-108">A single-qubit Pauli operator to be placed at the given location.</span></span>


### <a name="location--int"></a><span data-ttu-id="6cb44-109">位置： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6cb44-109">location : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6cb44-110">一个索引 `output[location] == pauli` ，其中， `output` 是此函数的输出。</span><span class="sxs-lookup"><span data-stu-id="6cb44-110">An index such that `output[location] == pauli`, where `output` is the output of this function.</span></span>


### <a name="n--int"></a><span data-ttu-id="6cb44-111">n： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6cb44-111">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6cb44-112">要返回的数组的长度。</span><span class="sxs-lookup"><span data-stu-id="6cb44-112">Length of the array to be returned.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="6cb44-113">Output： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="6cb44-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

