---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: PauliArrayAsInt 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: f8ec468dd0f0cfd0d868dfc79ff715b3b4fc2f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695654"
---
# <a name="pauliarrayasint-function"></a><span data-ttu-id="7a0fb-102">PauliArrayAsInt 函数</span><span class="sxs-lookup"><span data-stu-id="7a0fb-102">PauliArrayAsInt function</span></span>

<span data-ttu-id="7a0fb-103">命名空间 [：](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="7a0fb-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="7a0fb-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7a0fb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7a0fb-105">将表示为一个 qubit Pauli 运算符数组的多 qubit Pauli 运算符编码为一个整数。</span><span class="sxs-lookup"><span data-stu-id="7a0fb-105">Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.</span></span>

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="7a0fb-106">输入</span><span class="sxs-lookup"><span data-stu-id="7a0fb-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="7a0fb-107">paulis： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="7a0fb-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="7a0fb-108">最多31个 qubit Pauli 运算符的数组。</span><span class="sxs-lookup"><span data-stu-id="7a0fb-108">An array of at most 31 single-qubit Pauli operators.</span></span>



## <a name="output--int"></a><span data-ttu-id="7a0fb-109">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7a0fb-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7a0fb-110">唯一标识的整数 `paulis` ，如下所述。</span><span class="sxs-lookup"><span data-stu-id="7a0fb-110">An integer uniquely identifying `paulis`, as described below.</span></span>

## <a name="remarks"></a><span data-ttu-id="7a0fb-111">注解</span><span class="sxs-lookup"><span data-stu-id="7a0fb-111">Remarks</span></span>

<span data-ttu-id="7a0fb-112">每个 Pauli 运算符都可以使用两个位进行编码： $ $ \begin{align} \boldone \mapsto 00，\quad X \mapsto 01，\quad Y \mapsto 11，\quad Z \mapsto 10。</span><span class="sxs-lookup"><span data-stu-id="7a0fb-112">Each Pauli operator can be encoded using two bits: $$ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span></span>
<span data-ttu-id="7a0fb-113">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="7a0fb-113">\end{align} $$</span></span>

<span data-ttu-id="7a0fb-114">给定一个 Pauli 运算符数组 `[P0, ..., Pn]` ，该函数将返回一个整数，该整数通过以大字节序顺序连接每个 Pauli 运算符的映射来形成二进制展开 `bits(Pn) ... bits(P0)` 。</span><span class="sxs-lookup"><span data-stu-id="7a0fb-114">Given an array of Pauli operators `[P0, ..., Pn]`, this function returns an integer with binary expansion formed by concatenating the mappings of each Pauli operator in big-endian order `bits(Pn) ... bits(P0)`.</span></span>