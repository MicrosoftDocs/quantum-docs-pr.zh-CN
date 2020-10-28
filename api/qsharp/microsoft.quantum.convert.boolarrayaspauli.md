---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: BoolArrayAsPauli 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: c5ef71322dae248fc2c6b1db3adf891de7d72488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695687"
---
# <a name="boolarrayaspauli-function"></a><span data-ttu-id="75484-102">BoolArrayAsPauli 函数</span><span class="sxs-lookup"><span data-stu-id="75484-102">BoolArrayAsPauli function</span></span>

<span data-ttu-id="75484-103">命名空间 [：](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="75484-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="75484-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="75484-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="75484-105">给定位字符串后，将返回一个 qubit Pauli 运算符，该运算符表示为一个 qubit Pauli 运算符的数组。</span><span class="sxs-lookup"><span data-stu-id="75484-105">Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="75484-106">输入</span><span class="sxs-lookup"><span data-stu-id="75484-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="75484-107">pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="75484-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="75484-108">要应用于 qubits 的 Pauli 运算符 `bitsApply == bits[idx]` 。</span><span class="sxs-lookup"><span data-stu-id="75484-108">Pauli operator to apply to qubits where `bitsApply == bits[idx]`.</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="75484-109">bitApply： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="75484-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="75484-110">如果 bit 为此值，则应用 Pauli。</span><span class="sxs-lookup"><span data-stu-id="75484-110">apply Pauli if bit is this value.</span></span>


### <a name="bits--bool"></a><span data-ttu-id="75484-111">bits： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="75484-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="75484-112">布尔数组。</span><span class="sxs-lookup"><span data-stu-id="75484-112">Boolean array.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="75484-113">Output： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="75484-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="75484-114">注解</span><span class="sxs-lookup"><span data-stu-id="75484-114">Remarks</span></span>

<span data-ttu-id="75484-115">布尔数组和量程寄存器的长度必须相等。</span><span class="sxs-lookup"><span data-stu-id="75484-115">The Boolean array and the quantum register must be of equal length.</span></span>