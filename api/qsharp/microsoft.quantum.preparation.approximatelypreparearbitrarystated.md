---
uid: Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryStateD
title: ApproximatelyPrepareArbitraryStateD 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApproximatelyPrepareArbitraryStateD
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.
ms.openlocfilehash: 822efe08e66c43b7a3128d100e3e58a8c2ce3c2e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193584"
---
# <a name="approximatelypreparearbitrarystated-operation"></a><span data-ttu-id="f5d1b-102">ApproximatelyPrepareArbitraryStateD 操作</span><span class="sxs-lookup"><span data-stu-id="f5d1b-102">ApproximatelyPrepareArbitraryStateD operation</span></span>

<span data-ttu-id="f5d1b-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="f5d1b-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="f5d1b-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f5d1b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f5d1b-105">给定一组系数和一个小 endian 编码的量程寄存器，就给定系数所描述的那一寄存器的状态进行准备，直到达到给定的近似值。</span><span class="sxs-lookup"><span data-stu-id="f5d1b-105">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.</span></span>

```qsharp
operation ApproximatelyPrepareArbitraryStateD (tolerance : Double, coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="f5d1b-106">描述</span><span class="sxs-lookup"><span data-stu-id="f5d1b-106">Description</span></span>

<span data-ttu-id="f5d1b-107">此操作将准备一个具有复杂系数的任意量程状态 $ \ket{\psi} $ $r _j e ^ {$n t_j 计算基础状态 $ \ket{0 \cdots 0} $。</span><span class="sxs-lookup"><span data-stu-id="f5d1b-107">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="f5d1b-108">具体而言，此操作的操作可以通过单一转换 $U $ 来模拟，该转换作用于全零状态</span><span class="sxs-lookup"><span data-stu-id="f5d1b-108">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="f5d1b-109">$ $ \begin{align} U\ket {0 ... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}。</span><span class="sxs-lookup"><span data-stu-id="f5d1b-109">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="f5d1b-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="f5d1b-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="f5d1b-111">输入</span><span class="sxs-lookup"><span data-stu-id="f5d1b-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="f5d1b-112">容差： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f5d1b-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f5d1b-113">准备给定状态时要使用的近似值。</span><span class="sxs-lookup"><span data-stu-id="f5d1b-113">The approximation tolerance to be used when preparing the given state.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="f5d1b-114">系数： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="f5d1b-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="f5d1b-115">最多 $ 2 ^ n $ 实系数的数组。</span><span class="sxs-lookup"><span data-stu-id="f5d1b-115">Array of up to $2^n$ real coefficients.</span></span> <span data-ttu-id="f5d1b-116">$J $ th 用于索引以小字节序格式编码的数字状态 $ \ket{j} $。</span><span class="sxs-lookup"><span data-stu-id="f5d1b-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="f5d1b-117">qubits： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f5d1b-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f5d1b-118">Qubit 寄存器编码号状态（以小字节序格式）。</span><span class="sxs-lookup"><span data-stu-id="f5d1b-118">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="f5d1b-119">这应在计算基础状态 $ \ket{0...0} $ 中进行初始化。</span><span class="sxs-lookup"><span data-stu-id="f5d1b-119">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f5d1b-120">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f5d1b-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f5d1b-121">备注</span><span class="sxs-lookup"><span data-stu-id="f5d1b-121">Remarks</span></span>

<span data-ttu-id="f5d1b-122">负的输入系数 $r 将被视为值为 $ | r_j | $ 的 _j < $0。</span><span class="sxs-lookup"><span data-stu-id="f5d1b-122">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="f5d1b-123">`coefficients` 将用元素 $ (r_j，t_j) = (0.0，0.0) $ （如果指定少于 $ 2 ^ n $）。</span><span class="sxs-lookup"><span data-stu-id="f5d1b-123">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="f5d1b-124">参考</span><span class="sxs-lookup"><span data-stu-id="f5d1b-124">References</span></span>

- <span data-ttu-id="f5d1b-125">量程逻辑电路的合成 Vivek Shende、Stephen Bullock、Igor Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="f5d1b-125">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>