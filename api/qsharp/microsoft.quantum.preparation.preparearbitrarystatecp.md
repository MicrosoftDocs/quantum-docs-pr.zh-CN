---
uid: Microsoft.Quantum.Preparation.PrepareArbitraryStateCP
title: PrepareArbitraryStateCP 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareArbitraryStateCP
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.
ms.openlocfilehash: 21a632c003da16fb5cb20ab97fc0d251a897892b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210635"
---
# <a name="preparearbitrarystatecp-operation"></a><span data-ttu-id="3ffdb-102">PrepareArbitraryStateCP 操作</span><span class="sxs-lookup"><span data-stu-id="3ffdb-102">PrepareArbitraryStateCP operation</span></span>

<span data-ttu-id="3ffdb-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="3ffdb-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="3ffdb-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3ffdb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3ffdb-105">给定一组系数和一个小 endian 编码的量程寄存器，就给定的系数所描述的那个寄存器的状态进行准备。</span><span class="sxs-lookup"><span data-stu-id="3ffdb-105">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.</span></span>

```qsharp
operation PrepareArbitraryStateCP (coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="3ffdb-106">描述</span><span class="sxs-lookup"><span data-stu-id="3ffdb-106">Description</span></span>

<span data-ttu-id="3ffdb-107">此操作将准备一个具有复杂系数的任意量程状态 $ \ket{\psi} $ $r _j e ^ {$n t_j 计算基础状态 $ \ket{0 \cdots 0} $。</span><span class="sxs-lookup"><span data-stu-id="3ffdb-107">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="3ffdb-108">具体而言，此操作的操作可以通过单一转换 $U $ 来模拟，该转换作用于全零状态</span><span class="sxs-lookup"><span data-stu-id="3ffdb-108">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="3ffdb-109">$ $ \begin{align} U\ket {0 ... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}。</span><span class="sxs-lookup"><span data-stu-id="3ffdb-109">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="3ffdb-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="3ffdb-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="3ffdb-111">输入</span><span class="sxs-lookup"><span data-stu-id="3ffdb-111">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="3ffdb-112">系数： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="3ffdb-112">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="3ffdb-113">由最多 $ 2 ^ n $ 个复数系数表示的数组，其绝对值和阶段 $ (r_j，t_j) $。</span><span class="sxs-lookup"><span data-stu-id="3ffdb-113">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="3ffdb-114">$J $ th 用于索引以小字节序格式编码的数字状态 $ \ket{j} $。</span><span class="sxs-lookup"><span data-stu-id="3ffdb-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="3ffdb-115">qubits： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3ffdb-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3ffdb-116">Qubit 寄存器编码号状态（以小字节序格式）。</span><span class="sxs-lookup"><span data-stu-id="3ffdb-116">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="3ffdb-117">这应在计算基础状态 $ \ket{0...0} $ 中进行初始化。</span><span class="sxs-lookup"><span data-stu-id="3ffdb-117">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3ffdb-118">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3ffdb-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3ffdb-119">备注</span><span class="sxs-lookup"><span data-stu-id="3ffdb-119">Remarks</span></span>

<span data-ttu-id="3ffdb-120">负的输入系数 $r 将被视为值为 $ | r_j | $ 的 _j < $0。</span><span class="sxs-lookup"><span data-stu-id="3ffdb-120">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="3ffdb-121">`coefficients` 将用元素 $ (r_j，t_j) = (0.0，0.0) $ （如果指定少于 $ 2 ^ n $）。</span><span class="sxs-lookup"><span data-stu-id="3ffdb-121">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="3ffdb-122">参考</span><span class="sxs-lookup"><span data-stu-id="3ffdb-122">References</span></span>

- <span data-ttu-id="3ffdb-123">量程逻辑电路的合成 Vivek Shende、Stephen Bullock、Igor Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="3ffdb-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="3ffdb-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ffdb-124">See Also</span></span>

- [<span data-ttu-id="3ffdb-125">ApproximatelyPrepareArbitraryState。</span><span class="sxs-lookup"><span data-stu-id="3ffdb-125">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)