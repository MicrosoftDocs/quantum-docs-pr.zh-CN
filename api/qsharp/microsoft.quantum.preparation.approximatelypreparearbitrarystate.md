---
uid: Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState
title: ApproximatelyPrepareArbitraryState 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApproximatelyPrepareArbitraryState
qsharp.summary: >-
  > [!WARNING]

  > ApproximatelyPrepareArbitraryState has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryStateCP> instead.


  Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.
ms.openlocfilehash: 9e1b172258acd0cb09b824a773e7e79d44fec20c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193703"
---
# <a name="approximatelypreparearbitrarystate-operation"></a><span data-ttu-id="190be-102">ApproximatelyPrepareArbitraryState 操作</span><span class="sxs-lookup"><span data-stu-id="190be-102">ApproximatelyPrepareArbitraryState operation</span></span>

<span data-ttu-id="190be-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="190be-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="190be-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="190be-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="190be-105">ApproximatelyPrepareArbitraryState 已被弃用。</span><span class="sxs-lookup"><span data-stu-id="190be-105">ApproximatelyPrepareArbitraryState has been deprecated.</span></span> <span data-ttu-id="190be-106">请改用 <xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryStateCP>。</span><span class="sxs-lookup"><span data-stu-id="190be-106">Please use <xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryStateCP> instead.</span></span>

<span data-ttu-id="190be-107">给定一组系数和一个小 endian 编码的量程寄存器，就给定系数所描述的那一寄存器的状态进行准备，直到达到给定的近似值。</span><span class="sxs-lookup"><span data-stu-id="190be-107">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.</span></span>

```qsharp
operation ApproximatelyPrepareArbitraryState (tolerance : Double, coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="190be-108">描述</span><span class="sxs-lookup"><span data-stu-id="190be-108">Description</span></span>

<span data-ttu-id="190be-109">此操作将准备一个具有复杂系数的任意量程状态 $ \ket{\psi} $ $r _j e ^ {$n t_j 计算基础状态 $ \ket{0 \cdots 0} $。</span><span class="sxs-lookup"><span data-stu-id="190be-109">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="190be-110">具体而言，此操作的操作可以通过单一转换 $U $ 来模拟，该转换作用于全零状态</span><span class="sxs-lookup"><span data-stu-id="190be-110">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="190be-111">$ $ \begin{align} U\ket {0 ... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}。</span><span class="sxs-lookup"><span data-stu-id="190be-111">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="190be-112">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="190be-112">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="190be-113">输入</span><span class="sxs-lookup"><span data-stu-id="190be-113">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="190be-114">容差： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="190be-114">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="190be-115">准备给定状态时要使用的近似值。</span><span class="sxs-lookup"><span data-stu-id="190be-115">The approximation tolerance to be used when preparing the given state.</span></span>


### <a name="coefficients--complexpolar"></a><span data-ttu-id="190be-116">系数： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="190be-116">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="190be-117">由最多 $ 2 ^ n $ 个复数系数表示的数组，其绝对值和阶段 $ (r_j，t_j) $。</span><span class="sxs-lookup"><span data-stu-id="190be-117">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="190be-118">$J $ th 用于索引以小字节序格式编码的数字状态 $ \ket{j} $。</span><span class="sxs-lookup"><span data-stu-id="190be-118">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="190be-119">qubits： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="190be-119">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="190be-120">Qubit 寄存器编码号状态（以小字节序格式）。</span><span class="sxs-lookup"><span data-stu-id="190be-120">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="190be-121">这应在计算基础状态 $ \ket{0...0} $ 中进行初始化。</span><span class="sxs-lookup"><span data-stu-id="190be-121">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="190be-122">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="190be-122">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="190be-123">备注</span><span class="sxs-lookup"><span data-stu-id="190be-123">Remarks</span></span>

<span data-ttu-id="190be-124">负的输入系数 $r 将被视为值为 $ | r_j | $ 的 _j < $0。</span><span class="sxs-lookup"><span data-stu-id="190be-124">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="190be-125">`coefficients` 将用元素 $ (r_j，t_j) = (0.0，0.0) $ （如果指定少于 $ 2 ^ n $）。</span><span class="sxs-lookup"><span data-stu-id="190be-125">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="190be-126">参考</span><span class="sxs-lookup"><span data-stu-id="190be-126">References</span></span>

- <span data-ttu-id="190be-127">量程逻辑电路的合成 Vivek Shende、Stephen Bullock、Igor Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="190be-127">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="190be-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="190be-128">See Also</span></span>

- [<span data-ttu-id="190be-129">ApproximatelyPrepareArbitraryState。</span><span class="sxs-lookup"><span data-stu-id="190be-129">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)