---
uid: Microsoft.Quantum.Intrinsic.Exp
title: Exp 运算
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Exp
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator.

  \begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 7aa6974e83e917125b63ef91fb5c3b1238f6e856
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98819011"
---
# <a name="exp-operation"></a><span data-ttu-id="7c52c-102">Exp 运算</span><span class="sxs-lookup"><span data-stu-id="7c52c-102">Exp operation</span></span>

<span data-ttu-id="7c52c-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="7c52c-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="7c52c-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="7c52c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="7c52c-105">应用多 qubit Pauli 运算符的幂。</span><span class="sxs-lookup"><span data-stu-id="7c52c-105">Applies the exponential of a multi-qubit Pauli operator.</span></span>

<span data-ttu-id="7c52c-106">\begin{align} e ^ {i \theta [P_0 \otimes P_1 \cdots P_ {N-1}]}，\end{align}，其中 $P _i $ 是的 $i $ th 元素 `paulis` ，其中 $N = $ `Length(paulis)` 。</span><span class="sxs-lookup"><span data-stu-id="7c52c-106">\begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation Exp (paulis : Pauli[], theta : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7c52c-107">输入</span><span class="sxs-lookup"><span data-stu-id="7c52c-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="7c52c-108">paulis： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="7c52c-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="7c52c-109">Qubit Pauli 值的数组，用于指示每个 qubit 上的 tensor 产品因素。</span><span class="sxs-lookup"><span data-stu-id="7c52c-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="theta--double"></a><span data-ttu-id="7c52c-110">theta： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7c52c-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7c52c-111">用于旋转目标寄存器的给定多 qubit Pauli 运算符的角度。</span><span class="sxs-lookup"><span data-stu-id="7c52c-111">Angle about the given multi-qubit Pauli operator by which the target register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="7c52c-112">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7c52c-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7c52c-113">注册以应用给定的旋转。</span><span class="sxs-lookup"><span data-stu-id="7c52c-113">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7c52c-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7c52c-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

