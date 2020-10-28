---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexZ
title: ApproximatelyMultiplexZ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: ac5195b8b3afaad4d41fe50d45652644e2397e1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696143"
---
# <a name="approximatelymultiplexz-operation"></a><span data-ttu-id="5cf7d-102">ApproximatelyMultiplexZ 操作</span><span class="sxs-lookup"><span data-stu-id="5cf7d-102">ApproximatelyMultiplexZ operation</span></span>

<span data-ttu-id="5cf7d-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5cf7d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5cf7d-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5cf7d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5cf7d-105">对 qubits 数组应用 Pauli Z 旋转，根据给定的公差截断小旋转角度。</span><span class="sxs-lookup"><span data-stu-id="5cf7d-105">Applies a Pauli Z rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyMultiplexZ (tolerance : Double, coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="5cf7d-106">说明</span><span class="sxs-lookup"><span data-stu-id="5cf7d-106">Description</span></span>

<span data-ttu-id="5cf7d-107">这将应用按角度 $ \ theta_j $ 来执行循环的多次控制的单一操作，该操作将由 $n $-qubit 号 state $ \ket{j} $ 控制，按角度 $ \ qubit Pauli operator $Z $ 进行旋转。</span><span class="sxs-lookup"><span data-stu-id="5cf7d-107">This applies the multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $Z$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="5cf7d-108">具体而言，此操作可由单一</span><span class="sxs-lookup"><span data-stu-id="5cf7d-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="5cf7d-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i Z \ theta_j}。</span><span class="sxs-lookup"><span data-stu-id="5cf7d-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0} \ket{j}\bra{j} \otimes e^{i Z \theta_j}.</span></span>
<span data-ttu-id="5cf7d-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="5cf7d-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="5cf7d-111">输入</span><span class="sxs-lookup"><span data-stu-id="5cf7d-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="5cf7d-112">容差： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5cf7d-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5cf7d-113">小于其小系数的公差将被截断。</span><span class="sxs-lookup"><span data-stu-id="5cf7d-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="5cf7d-114">系数： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="5cf7d-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="5cf7d-115">最多 $ 2 ^ n $ 系数 $ \ theta_j $ 的数组。</span><span class="sxs-lookup"><span data-stu-id="5cf7d-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="5cf7d-116">$J $ th 用于索引以小字节序格式编码的数字状态 $ \ket{j} $。</span><span class="sxs-lookup"><span data-stu-id="5cf7d-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="5cf7d-117">控件： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5cf7d-117">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5cf7d-118">$n 以小字节序格式编码数字状态 $ \ket{j} $ 的 qubit 控制寄存器。</span><span class="sxs-lookup"><span data-stu-id="5cf7d-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="5cf7d-119">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5cf7d-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5cf7d-120">通过 $e ^ {i P \ theta_j} $ 旋转的单个 qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="5cf7d-120">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5cf7d-121">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5cf7d-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5cf7d-122">注解</span><span class="sxs-lookup"><span data-stu-id="5cf7d-122">Remarks</span></span>

<span data-ttu-id="5cf7d-123">`coefficients` 如果指定少于 $ 2 ^ n $，则将用元素 $ \ theta_j = $0.0 填充。</span><span class="sxs-lookup"><span data-stu-id="5cf7d-123">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="5cf7d-124">参考</span><span class="sxs-lookup"><span data-stu-id="5cf7d-124">References</span></span>

- <span data-ttu-id="5cf7d-125">量程逻辑电路的合成 Vivek Shende、Stephen Bullock、Igor Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="5cf7d-125">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="5cf7d-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5cf7d-126">See Also</span></span>

- [<span data-ttu-id="5cf7d-127">Canon. MultiplexZ</span><span class="sxs-lookup"><span data-stu-id="5cf7d-127">Microsoft.Quantum.Canon.MultiplexZ</span></span>](xref:Microsoft.Quantum.Canon.MultiplexZ)