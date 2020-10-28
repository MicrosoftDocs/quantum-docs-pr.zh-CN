---
uid: Microsoft.Quantum.Canon.MultiplexZ
title: MultiplexZ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits.
ms.openlocfilehash: f7b1973e18ad396ebe892ad63ae47374a7cafbd5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695998"
---
# <a name="multiplexz-operation"></a><span data-ttu-id="c4707-102">MultiplexZ 操作</span><span class="sxs-lookup"><span data-stu-id="c4707-102">MultiplexZ operation</span></span>

<span data-ttu-id="c4707-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c4707-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c4707-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c4707-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c4707-105">对 qubits 数组应用 Pauli Z 旋转。</span><span class="sxs-lookup"><span data-stu-id="c4707-105">Applies a Pauli Z rotation conditioned on an array of qubits.</span></span>

```qsharp
operation MultiplexZ (coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="c4707-106">说明</span><span class="sxs-lookup"><span data-stu-id="c4707-106">Description</span></span>

<span data-ttu-id="c4707-107">这将应用按角度 $ \ theta_j $ 来执行循环的多次控制的单一操作，该操作将由 $n $-qubit 号 state $ \ket{j} $ 控制，按角度 $ \ qubit Pauli operator $Z $ 进行旋转。</span><span class="sxs-lookup"><span data-stu-id="c4707-107">This applies the multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $Z$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="c4707-108">具体而言，此操作可由单一</span><span class="sxs-lookup"><span data-stu-id="c4707-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="c4707-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i Z \ theta_j}。</span><span class="sxs-lookup"><span data-stu-id="c4707-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0} \ket{j}\bra{j} \otimes e^{i Z \theta_j}.</span></span>
<span data-ttu-id="c4707-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="c4707-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="c4707-111">输入</span><span class="sxs-lookup"><span data-stu-id="c4707-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="c4707-112">系数： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="c4707-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="c4707-113">最多 $ 2 ^ n $ 系数 $ \ theta_j $ 的数组。</span><span class="sxs-lookup"><span data-stu-id="c4707-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="c4707-114">$J $ th 用于索引以小字节序格式编码的数字状态 $ \ket{j} $。</span><span class="sxs-lookup"><span data-stu-id="c4707-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="c4707-115">控件： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c4707-115">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c4707-116">$n 以小字节序格式编码数字状态 $ \ket{j} $ 的 qubit 控制寄存器。</span><span class="sxs-lookup"><span data-stu-id="c4707-116">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="c4707-117">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c4707-117">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c4707-118">通过 $e ^ {i P \ theta_j} $ 旋转的单个 qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="c4707-118">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c4707-119">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c4707-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c4707-120">注解</span><span class="sxs-lookup"><span data-stu-id="c4707-120">Remarks</span></span>

<span data-ttu-id="c4707-121">`coefficients` 如果指定少于 $ 2 ^ n $，则将用元素 $ \ theta_j = $0.0 填充。</span><span class="sxs-lookup"><span data-stu-id="c4707-121">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="c4707-122">参考</span><span class="sxs-lookup"><span data-stu-id="c4707-122">References</span></span>

- <span data-ttu-id="c4707-123">量程逻辑电路的合成 Vivek Shende、Stephen Bullock、Igor Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="c4707-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="c4707-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4707-124">See Also</span></span>

- [<span data-ttu-id="c4707-125">Canon. ApproximatelyMultiplexZ</span><span class="sxs-lookup"><span data-stu-id="c4707-125">Microsoft.Quantum.Canon.ApproximatelyMultiplexZ</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyMultiplexZ)