---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: AssertProbInt 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: 85ff04bbad9dc2ed0f803db65508fdfbb0d22c56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843410"
---
# <a name="assertprobint-operation"></a><span data-ttu-id="4e9e1-102">AssertProbInt 操作</span><span class="sxs-lookup"><span data-stu-id="4e9e1-102">AssertProbInt operation</span></span>

<span data-ttu-id="4e9e1-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4e9e1-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4e9e1-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4e9e1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4e9e1-105">断言量程寄存器的特定状态的概率具有预期值。</span><span class="sxs-lookup"><span data-stu-id="4e9e1-105">Asserts that the probability of a specific state of a quantum register has the expected value.</span></span>

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="4e9e1-106">说明</span><span class="sxs-lookup"><span data-stu-id="4e9e1-106">Description</span></span>

<span data-ttu-id="4e9e1-107">如果给定 $n $-qubit 量程状态 $ \ket{\psi} = \sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $，则断言 $ $j 索引的状态 $ \ket{j} $ 的概率 $ | \ alpha_j | ^ 2 $ 具有预期值。</span><span class="sxs-lookup"><span data-stu-id="4e9e1-107">Given an $n$-qubit quantum state $\ket{\psi}=\sum^{2^n-1}_{j=0}\alpha_j \ket{j}$, asserts that the probability $|\alpha_j|^2$ of the state $\ket{j}$ indexed by $j$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="4e9e1-108">输入</span><span class="sxs-lookup"><span data-stu-id="4e9e1-108">Input</span></span>

### <a name="stateindex--int"></a><span data-ttu-id="4e9e1-109">stateIndex： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4e9e1-109">stateIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4e9e1-110">由寄存器表示的状态 $ \ket{j} $ 的索引 $j $ `LittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="4e9e1-110">The index $j$ of the state $\ket{j}$ represented by a `LittleEndian` register.</span></span>


### <a name="expected--double"></a><span data-ttu-id="4e9e1-111">应为： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4e9e1-111">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4e9e1-112">$ | \ Alpha_j | ^ 2 $ 的预期值。</span><span class="sxs-lookup"><span data-stu-id="4e9e1-112">The expected value of $|\alpha_j|^2$.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="4e9e1-113">qubits： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4e9e1-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4e9e1-114">以小字节序格式存储 $ \ket{\psi} $ 的 qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="4e9e1-114">The qubit register that stores $\ket{\psi}$ in little-endian format.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="4e9e1-115">容差： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4e9e1-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4e9e1-116">实际值与预期值的绝对容差。</span><span class="sxs-lookup"><span data-stu-id="4e9e1-116">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4e9e1-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4e9e1-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="4e9e1-118">示例</span><span class="sxs-lookup"><span data-stu-id="4e9e1-118">Example</span></span>

<span data-ttu-id="4e9e1-119">假设注册将 `qubits` qubit 的量程状态 $ \ket{\psi} = \ sqrt {1/8} \ 票证 {0} + \ sqrt {7/8} \ 票证 $ 编码为 {6} 小 endian 格式。</span><span class="sxs-lookup"><span data-stu-id="4e9e1-119">Suppose that the `qubits` register encodes a 3-qubit quantum state $\ket{\psi}=\sqrt{1/8}\ket{0}+\sqrt{7/8}\ket{6}$ in little-endian format.</span></span>
<span data-ttu-id="4e9e1-120">这意味着数字状态 $ \ket {0} \equiv\ket {0} \ket {0} \ket {0} $ 和 $ \ket \equiv\ket \ket {6} {0} {1} \ket {1} $。</span><span class="sxs-lookup"><span data-stu-id="4e9e1-120">This means that the number states $\ket{0}\equiv\ket{0}\ket{0}\ket{0}$ and $\ket{6}\equiv\ket{0}\ket{1}\ket{1}$.</span></span> <span data-ttu-id="4e9e1-121">以下断言成功：</span><span class="sxs-lookup"><span data-stu-id="4e9e1-121">Then the following asserts succeed:</span></span>

```qsharp
AssertProbInt(0, 0.125, qubits, 10e-10);
AssertProbInt(6, 0.875, qubits, 10e-10);
```