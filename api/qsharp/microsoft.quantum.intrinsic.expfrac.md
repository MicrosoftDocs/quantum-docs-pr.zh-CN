---
uid: Microsoft.Quantum.Intrinsic.ExpFrac
title: ExpFrac 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ExpFrac
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.

  \begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 6634caff164c841876fb53e79c3f93254a7d624c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849421"
---
# <a name="expfrac-operation"></a><span data-ttu-id="45d5a-102">ExpFrac 操作</span><span class="sxs-lookup"><span data-stu-id="45d5a-102">ExpFrac operation</span></span>

<span data-ttu-id="45d5a-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="45d5a-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="45d5a-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="45d5a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="45d5a-105">使用由 dyadic 分式给定的自变量对 qubit Pauli 运算符应用指数。</span><span class="sxs-lookup"><span data-stu-id="45d5a-105">Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.</span></span>

<span data-ttu-id="45d5a-106">\begin{align} e ^ {i \pi k [P_0 \otimes P_1 \cdots P_ {N-1}]/2 ^ N}，\end{align} 其中 $P _i $ 是的 $i $ th 元素 `paulis` ，其中 $N = $ `Length(paulis)` 。</span><span class="sxs-lookup"><span data-stu-id="45d5a-106">\begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation ExpFrac (paulis : Pauli[], numerator : Int, power : Int, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="45d5a-107">输入</span><span class="sxs-lookup"><span data-stu-id="45d5a-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="45d5a-108">paulis： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="45d5a-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="45d5a-109">Qubit Pauli 值的数组，用于指示每个 qubit 上的 tensor 产品因素。</span><span class="sxs-lookup"><span data-stu-id="45d5a-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="numerator--int"></a><span data-ttu-id="45d5a-110">分子： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="45d5a-110">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="45d5a-111">分子 ($k $) ，该角度表示 qubit 寄存器要旋转的角度。</span><span class="sxs-lookup"><span data-stu-id="45d5a-111">Numerator ($k$) in the dyadic fraction representation of the angle by which the qubit register is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="45d5a-112">幂： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="45d5a-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="45d5a-113">两个 (的幂 $n $) 指定 qubit 寄存器旋转角度的分母。</span><span class="sxs-lookup"><span data-stu-id="45d5a-113">Power of two ($n$) specifying the denominator of the angle by which the qubit register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="45d5a-114">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="45d5a-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="45d5a-115">注册以应用给定的旋转。</span><span class="sxs-lookup"><span data-stu-id="45d5a-115">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="45d5a-116">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="45d5a-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

