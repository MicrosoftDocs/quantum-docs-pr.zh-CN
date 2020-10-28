---
uid: Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState
title: ApproximatelyPrepareArbitraryState 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApproximatelyPrepareArbitraryState
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.
ms.openlocfilehash: 2561b098c5faf2d24bb9ab348fb052025808e441
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700741"
---
# <a name="approximatelypreparearbitrarystate-operation"></a><span data-ttu-id="eec73-102">ApproximatelyPrepareArbitraryState 操作</span><span class="sxs-lookup"><span data-stu-id="eec73-102">ApproximatelyPrepareArbitraryState operation</span></span>

<span data-ttu-id="eec73-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="eec73-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="eec73-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eec73-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eec73-105">给定一组系数和一个小 endian 编码的量程寄存器，就给定系数所描述的那一寄存器的状态进行准备，直到达到给定的近似值。</span><span class="sxs-lookup"><span data-stu-id="eec73-105">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.</span></span>

```qsharp
operation ApproximatelyPrepareArbitraryState (tolerance : Double, coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="eec73-106">说明</span><span class="sxs-lookup"><span data-stu-id="eec73-106">Description</span></span>

<span data-ttu-id="eec73-107">此操作将准备一个具有复杂系数的任意量程状态 $ \ket{\psi} $ $r _j e ^ {$n t_j 计算基础状态 $ \ket{0 \cdots 0} $。</span><span class="sxs-lookup"><span data-stu-id="eec73-107">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="eec73-108">具体而言，此操作的操作可以通过单一转换 $U $ 来模拟，该转换作用于全零状态</span><span class="sxs-lookup"><span data-stu-id="eec73-108">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="eec73-109">$ $ \begin{align} U\ket {0 ... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}。</span><span class="sxs-lookup"><span data-stu-id="eec73-109">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="eec73-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="eec73-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="eec73-111">输入</span><span class="sxs-lookup"><span data-stu-id="eec73-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="eec73-112">容差： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="eec73-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="eec73-113">准备给定状态时要使用的近似值。</span><span class="sxs-lookup"><span data-stu-id="eec73-113">The approximation tolerance to be used when preparing the given state.</span></span>


### <a name="coefficients--complexpolar"></a><span data-ttu-id="eec73-114">系数： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="eec73-114">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="eec73-115">由最多 $ 2 ^ n $ 个复数系数表示的数组，其绝对值和阶段 $ (r_j，t_j) $。</span><span class="sxs-lookup"><span data-stu-id="eec73-115">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="eec73-116">$J $ th 用于索引以小字节序格式编码的数字状态 $ \ket{j} $。</span><span class="sxs-lookup"><span data-stu-id="eec73-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="eec73-117">qubits： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="eec73-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="eec73-118">Qubit 寄存器编码号状态（以小字节序格式）。</span><span class="sxs-lookup"><span data-stu-id="eec73-118">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="eec73-119">这应在计算基础状态 $ \ket{0...0} $ 中进行初始化。</span><span class="sxs-lookup"><span data-stu-id="eec73-119">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eec73-120">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eec73-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="eec73-121">注解</span><span class="sxs-lookup"><span data-stu-id="eec73-121">Remarks</span></span>

<span data-ttu-id="eec73-122">负的输入系数 $r 将被视为值为 $ | r_j | $ 的 _j < $0。</span><span class="sxs-lookup"><span data-stu-id="eec73-122">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="eec73-123">`coefficients` 将用元素 $ (r_j，t_j) = (0.0，0.0) $ （如果指定少于 $ 2 ^ n $）。</span><span class="sxs-lookup"><span data-stu-id="eec73-123">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="eec73-124">参考</span><span class="sxs-lookup"><span data-stu-id="eec73-124">References</span></span>

- <span data-ttu-id="eec73-125">量程逻辑电路的合成 Vivek Shende、Stephen Bullock、Igor Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="eec73-125">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="eec73-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eec73-126">See Also</span></span>

- [<span data-ttu-id="eec73-127">ApproximatelyPrepareArbitraryState。</span><span class="sxs-lookup"><span data-stu-id="eec73-127">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)