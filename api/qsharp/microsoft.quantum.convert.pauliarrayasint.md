---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: PauliArrayAsInt 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: 6077110cc07c8626b22eb404c1de096ed43efcc3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224235"
---
# <a name="pauliarrayasint-function"></a><span data-ttu-id="434e4-102">PauliArrayAsInt 函数</span><span class="sxs-lookup"><span data-stu-id="434e4-102">PauliArrayAsInt function</span></span>

<span data-ttu-id="434e4-103">命名空间 [：](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="434e4-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="434e4-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="434e4-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="434e4-105">将表示为一个 qubit Pauli 运算符数组的多 qubit Pauli 运算符编码为一个整数。</span><span class="sxs-lookup"><span data-stu-id="434e4-105">Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.</span></span>

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="434e4-106">输入</span><span class="sxs-lookup"><span data-stu-id="434e4-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="434e4-107">paulis： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="434e4-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="434e4-108">最多31个 qubit Pauli 运算符的数组。</span><span class="sxs-lookup"><span data-stu-id="434e4-108">An array of at most 31 single-qubit Pauli operators.</span></span>



## <a name="output--int"></a><span data-ttu-id="434e4-109">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="434e4-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="434e4-110">唯一标识的整数 `paulis` ，如下所述。</span><span class="sxs-lookup"><span data-stu-id="434e4-110">An integer uniquely identifying `paulis`, as described below.</span></span>

## <a name="remarks"></a><span data-ttu-id="434e4-111">备注</span><span class="sxs-lookup"><span data-stu-id="434e4-111">Remarks</span></span>

<span data-ttu-id="434e4-112">每个 Pauli 运算符都可以使用两个位进行编码： $ $ \begin{align} \boldone \mapsto 00，\quad X \mapsto 01，\quad Y \mapsto 11，\quad Z \mapsto 10。</span><span class="sxs-lookup"><span data-stu-id="434e4-112">Each Pauli operator can be encoded using two bits: $$ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span></span>
<span data-ttu-id="434e4-113">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="434e4-113">\end{align} $$</span></span>

<span data-ttu-id="434e4-114">给定一个 Pauli 运算符数组 `[P0, ..., Pn]` ，该函数将返回一个整数，该整数通过以大字节序顺序连接每个 Pauli 运算符的映射来形成二进制展开 `bits(Pn) ... bits(P0)` 。</span><span class="sxs-lookup"><span data-stu-id="434e4-114">Given an array of Pauli operators `[P0, ..., Pn]`, this function returns an integer with binary expansion formed by concatenating the mappings of each Pauli operator in big-endian order `bits(Pn) ... bits(P0)`.</span></span>