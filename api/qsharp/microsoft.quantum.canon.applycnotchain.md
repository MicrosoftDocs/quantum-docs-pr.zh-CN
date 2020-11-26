---
uid: Microsoft.Quantum.Canon.ApplyCNOTChain
title: ApplyCNOTChain 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChain
qsharp.summary: Computes the parity of a register of qubits in-place.
ms.openlocfilehash: e237e4424661de816e73b0c78523180b41190cf9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219135"
---
# <a name="applycnotchain-operation"></a><span data-ttu-id="141ac-102">ApplyCNOTChain 操作</span><span class="sxs-lookup"><span data-stu-id="141ac-102">ApplyCNOTChain operation</span></span>

<span data-ttu-id="141ac-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="141ac-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="141ac-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="141ac-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="141ac-105">计算 qubits 的寄存器的奇偶校验。</span><span class="sxs-lookup"><span data-stu-id="141ac-105">Computes the parity of a register of qubits in-place.</span></span>

```qsharp
operation ApplyCNOTChain (qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="141ac-106">描述</span><span class="sxs-lookup"><span data-stu-id="141ac-106">Description</span></span>

<span data-ttu-id="141ac-107">此操作将其输入的状态转换为 $ $ \begin{align} \ket{q_0} \ket{q_1} \cdots \ket{q_ {n-1}} & \mapsto \ket{q_0} \ket{q_0 \oplus q_1} \ket{q_0 \oplus q_1 \oplus q_2} \cdots \ket{q_0 \oplus \cdots \oplus q_ {n-1}}。</span><span class="sxs-lookup"><span data-stu-id="141ac-107">This operation transforms the state of its input as $$ \begin{align} \ket{q_0} \ket{q_1} \cdots \ket{q_{n - 1}} & \mapsto \ket{q_0} \ket{q_0 \oplus q_1} \ket{q_0 \oplus q_1 \oplus q_2} \cdots \ket{q_0 \oplus \cdots \oplus q_{n - 1}}.</span></span>
<span data-ttu-id="141ac-108">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="141ac-108">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="141ac-109">输入</span><span class="sxs-lookup"><span data-stu-id="141ac-109">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="141ac-110">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="141ac-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="141ac-111">要计算和存储其奇偶校验的 qubits 数组。</span><span class="sxs-lookup"><span data-stu-id="141ac-111">Array of qubits whose parity is to be computed and stored.</span></span>



## <a name="output--unit"></a><span data-ttu-id="141ac-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="141ac-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

