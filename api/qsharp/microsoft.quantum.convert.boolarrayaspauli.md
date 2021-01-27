---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: BoolArrayAsPauli 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: c11ca05ad8a939d704547c65a8e8a6537d0df4b7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834234"
---
# <a name="boolarrayaspauli-function"></a><span data-ttu-id="2a979-102">BoolArrayAsPauli 函数</span><span class="sxs-lookup"><span data-stu-id="2a979-102">BoolArrayAsPauli function</span></span>

<span data-ttu-id="2a979-103">命名空间 [：](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="2a979-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="2a979-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2a979-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2a979-105">给定位字符串后，将返回一个 qubit Pauli 运算符，该运算符表示为一个 qubit Pauli 运算符的数组。</span><span class="sxs-lookup"><span data-stu-id="2a979-105">Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="2a979-106">输入</span><span class="sxs-lookup"><span data-stu-id="2a979-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="2a979-107">pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="2a979-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="2a979-108">要应用于 qubits 的 Pauli 运算符 `bitsApply == bits[idx]` 。</span><span class="sxs-lookup"><span data-stu-id="2a979-108">Pauli operator to apply to qubits where `bitsApply == bits[idx]`.</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="2a979-109">bitApply： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2a979-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2a979-110">如果 bit 为此值，则应用 Pauli。</span><span class="sxs-lookup"><span data-stu-id="2a979-110">apply Pauli if bit is this value.</span></span>


### <a name="bits--bool"></a><span data-ttu-id="2a979-111">bits： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="2a979-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="2a979-112">布尔数组。</span><span class="sxs-lookup"><span data-stu-id="2a979-112">Boolean array.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="2a979-113">Output： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="2a979-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="2a979-114">备注</span><span class="sxs-lookup"><span data-stu-id="2a979-114">Remarks</span></span>

<span data-ttu-id="2a979-115">布尔数组和量程寄存器的长度必须相等。</span><span class="sxs-lookup"><span data-stu-id="2a979-115">The Boolean array and the quantum register must be of equal length.</span></span>