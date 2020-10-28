---
uid: Microsoft.Quantum.Canon.ApplyPauliFromBitString
title: ApplyPauliFromBitString 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauliFromBitString
qsharp.summary: Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.
ms.openlocfilehash: 09754accb92c1339b781003e5722e3c8f5884e6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696288"
---
# <a name="applypaulifrombitstring-operation"></a><span data-ttu-id="e07ca-102">ApplyPauliFromBitString 操作</span><span class="sxs-lookup"><span data-stu-id="e07ca-102">ApplyPauliFromBitString operation</span></span>

<span data-ttu-id="e07ca-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e07ca-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e07ca-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e07ca-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e07ca-105">如果布尔数组的相应位与给定的输入相匹配，则对数组中的每个 qubit 应用 Pauli 运算符。</span><span class="sxs-lookup"><span data-stu-id="e07ca-105">Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.</span></span>

```qsharp
operation ApplyPauliFromBitString (pauli : Pauli, bitApply : Bool, bits : Bool[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="e07ca-106">输入</span><span class="sxs-lookup"><span data-stu-id="e07ca-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="e07ca-107">pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="e07ca-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="e07ca-108">要应用于 `qubits[idx]` where 的 Pauli 运算符 `bitsApply == bits[idx]`</span><span class="sxs-lookup"><span data-stu-id="e07ca-108">Pauli operator to apply to `qubits[idx]` where `bitsApply == bits[idx]`</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="e07ca-109">bitApply： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e07ca-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e07ca-110">如果 bit 为此值，则应用 Pauli</span><span class="sxs-lookup"><span data-stu-id="e07ca-110">apply Pauli if bit is this value</span></span>


### <a name="bits--bool"></a><span data-ttu-id="e07ca-111">bits： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="e07ca-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="e07ca-112">指定应操作的相应 qubit 的布尔型寄存器 `qubits`</span><span class="sxs-lookup"><span data-stu-id="e07ca-112">Boolean register specifying which corresponding qubit in `qubits` should be operated on</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="e07ca-113">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e07ca-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e07ca-114">量程注册，可以选择应用指定的 Pauli 运算符</span><span class="sxs-lookup"><span data-stu-id="e07ca-114">Quantum register on which to selectively apply the specified Pauli operator</span></span>



## <a name="output--unit"></a><span data-ttu-id="e07ca-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e07ca-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e07ca-116">注解</span><span class="sxs-lookup"><span data-stu-id="e07ca-116">Remarks</span></span>

<span data-ttu-id="e07ca-117">布尔数组和量程寄存器的长度必须相等。</span><span class="sxs-lookup"><span data-stu-id="e07ca-117">The Boolean array and the quantum register must be of equal length.</span></span>