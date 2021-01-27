---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: PauliArrayAsInt 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: 4c3c51813ef509fdc52773b15a956c0a99500603
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832707"
---
# <a name="pauliarrayasint-function"></a><span data-ttu-id="53bc5-102">PauliArrayAsInt 函数</span><span class="sxs-lookup"><span data-stu-id="53bc5-102">PauliArrayAsInt function</span></span>

<span data-ttu-id="53bc5-103">命名空间 [：](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="53bc5-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="53bc5-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="53bc5-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="53bc5-105">将表示为一个 qubit Pauli 运算符数组的多 qubit Pauli 运算符编码为一个整数。</span><span class="sxs-lookup"><span data-stu-id="53bc5-105">Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.</span></span>

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="53bc5-106">输入</span><span class="sxs-lookup"><span data-stu-id="53bc5-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="53bc5-107">paulis： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="53bc5-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="53bc5-108">最多31个 qubit Pauli 运算符的数组。</span><span class="sxs-lookup"><span data-stu-id="53bc5-108">An array of at most 31 single-qubit Pauli operators.</span></span>



## <a name="output--int"></a><span data-ttu-id="53bc5-109">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="53bc5-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="53bc5-110">唯一标识的整数 `paulis` ，如下所述。</span><span class="sxs-lookup"><span data-stu-id="53bc5-110">An integer uniquely identifying `paulis`, as described below.</span></span>

## <a name="remarks"></a><span data-ttu-id="53bc5-111">备注</span><span class="sxs-lookup"><span data-stu-id="53bc5-111">Remarks</span></span>

<span data-ttu-id="53bc5-112">每个 Pauli 运算符都可以使用两个位进行编码： $ $ \begin{align} \boldone \mapsto 00，\quad X \mapsto 01，\quad Y \mapsto 11，\quad Z \mapsto 10。</span><span class="sxs-lookup"><span data-stu-id="53bc5-112">Each Pauli operator can be encoded using two bits: $$ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span></span>
<span data-ttu-id="53bc5-113">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="53bc5-113">\end{align} $$</span></span>

<span data-ttu-id="53bc5-114">给定一个 Pauli 运算符数组 `[P0, ..., Pn]` ，该函数将返回一个整数，该整数通过以大字节序顺序连接每个 Pauli 运算符的映射来形成二进制展开 `bits(Pn) ... bits(P0)` 。</span><span class="sxs-lookup"><span data-stu-id="53bc5-114">Given an array of Pauli operators `[P0, ..., Pn]`, this function returns an integer with binary expansion formed by concatenating the mappings of each Pauli operator in big-endian order `bits(Pn) ... bits(P0)`.</span></span>