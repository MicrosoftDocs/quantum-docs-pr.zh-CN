---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: BoolArrayAsPauli 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: 8e7088ec3918165d7b2afb1056a8319c6fb17796
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214273"
---
# <a name="boolarrayaspauli-function"></a><span data-ttu-id="c5ca9-102">BoolArrayAsPauli 函数</span><span class="sxs-lookup"><span data-stu-id="c5ca9-102">BoolArrayAsPauli function</span></span>

<span data-ttu-id="c5ca9-103">命名空间 [：](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="c5ca9-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="c5ca9-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c5ca9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c5ca9-105">给定位字符串后，将返回一个 qubit Pauli 运算符，该运算符表示为一个 qubit Pauli 运算符的数组。</span><span class="sxs-lookup"><span data-stu-id="c5ca9-105">Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="c5ca9-106">输入</span><span class="sxs-lookup"><span data-stu-id="c5ca9-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="c5ca9-107">pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="c5ca9-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="c5ca9-108">要应用于 qubits 的 Pauli 运算符 `bitsApply == bits[idx]` 。</span><span class="sxs-lookup"><span data-stu-id="c5ca9-108">Pauli operator to apply to qubits where `bitsApply == bits[idx]`.</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="c5ca9-109">bitApply： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c5ca9-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c5ca9-110">如果 bit 为此值，则应用 Pauli。</span><span class="sxs-lookup"><span data-stu-id="c5ca9-110">apply Pauli if bit is this value.</span></span>


### <a name="bits--bool"></a><span data-ttu-id="c5ca9-111">bits： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="c5ca9-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="c5ca9-112">布尔数组。</span><span class="sxs-lookup"><span data-stu-id="c5ca9-112">Boolean array.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="c5ca9-113">Output： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="c5ca9-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="c5ca9-114">备注</span><span class="sxs-lookup"><span data-stu-id="c5ca9-114">Remarks</span></span>

<span data-ttu-id="c5ca9-115">布尔数组和量程寄存器的长度必须相等。</span><span class="sxs-lookup"><span data-stu-id="c5ca9-115">The Boolean array and the quantum register must be of equal length.</span></span>