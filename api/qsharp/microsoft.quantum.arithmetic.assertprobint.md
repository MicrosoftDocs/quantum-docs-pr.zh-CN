---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: AssertProbInt 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: b95c2c6294dd5a95b7215c22bd6c50a41635f432
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223691"
---
# <a name="assertprobint-operation"></a><span data-ttu-id="b5764-102">AssertProbInt 操作</span><span class="sxs-lookup"><span data-stu-id="b5764-102">AssertProbInt operation</span></span>

<span data-ttu-id="b5764-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b5764-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b5764-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b5764-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b5764-105">断言量程寄存器的特定状态的概率具有预期值。</span><span class="sxs-lookup"><span data-stu-id="b5764-105">Asserts that the probability of a specific state of a quantum register has the expected value.</span></span>

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="b5764-106">描述</span><span class="sxs-lookup"><span data-stu-id="b5764-106">Description</span></span>

<span data-ttu-id="b5764-107">如果给定 $n $-qubit 量程状态 $ \ket{\psi} = \sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $，则断言 $ $j 索引的状态 $ \ket{j} $ 的概率 $ | \ alpha_j | ^ 2 $ 具有预期值。</span><span class="sxs-lookup"><span data-stu-id="b5764-107">Given an $n$-qubit quantum state $\ket{\psi}=\sum^{2^n-1}_{j=0}\alpha_j \ket{j}$, asserts that the probability $|\alpha_j|^2$ of the state $\ket{j}$ indexed by $j$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="b5764-108">输入</span><span class="sxs-lookup"><span data-stu-id="b5764-108">Input</span></span>

### <a name="stateindex--int"></a><span data-ttu-id="b5764-109">stateIndex： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b5764-109">stateIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b5764-110">由寄存器表示的状态 $ \ket{j} $ 的索引 $j $ `LittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="b5764-110">The index $j$ of the state $\ket{j}$ represented by a `LittleEndian` register.</span></span>


### <a name="expected--double"></a><span data-ttu-id="b5764-111">应为： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b5764-111">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b5764-112">$ | \ Alpha_j | ^ 2 $ 的预期值。</span><span class="sxs-lookup"><span data-stu-id="b5764-112">The expected value of $|\alpha_j|^2$.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="b5764-113">qubits： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b5764-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b5764-114">以小字节序格式存储 $ \ket{\psi} $ 的 qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="b5764-114">The qubit register that stores $\ket{\psi}$ in little-endian format.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="b5764-115">容差： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b5764-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b5764-116">实际值与预期值的绝对容差。</span><span class="sxs-lookup"><span data-stu-id="b5764-116">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b5764-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b5764-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

