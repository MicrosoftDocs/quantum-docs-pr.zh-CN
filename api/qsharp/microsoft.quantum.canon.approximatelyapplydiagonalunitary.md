---
uid: Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary
title: ApproximatelyApplyDiagonalUnitary 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 9d9b1ced320b142aef2a2cd8f3335f855d37048f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696147"
---
# <a name="approximatelyapplydiagonalunitary-operation"></a><span data-ttu-id="2ad64-102">ApproximatelyApplyDiagonalUnitary 操作</span><span class="sxs-lookup"><span data-stu-id="2ad64-102">ApproximatelyApplyDiagonalUnitary operation</span></span>

<span data-ttu-id="2ad64-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2ad64-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2ad64-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2ad64-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2ad64-105">将一个复杂阶段数组应用于 qubits 寄存器的数字基础状态，根据给定的公差截断小旋转角度。</span><span class="sxs-lookup"><span data-stu-id="2ad64-105">Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyApplyDiagonalUnitary (tolerance : Double, coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="2ad64-106">说明</span><span class="sxs-lookup"><span data-stu-id="2ad64-106">Description</span></span>

<span data-ttu-id="2ad64-107">此操作实现在 $n $-qubit number state $ \ket{j} $ 上应用复杂阶段 $e ^ {i \ theta_j} $ 的对角线。</span><span class="sxs-lookup"><span data-stu-id="2ad64-107">This operation implements a diagonal unitary that applies a complex phase $e^{i \theta_j}$ on the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="2ad64-108">具体而言，此操作可由单一</span><span class="sxs-lookup"><span data-stu-id="2ad64-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="2ad64-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} e ^ {i \ theta_j} \ket{j}\bra{j}。</span><span class="sxs-lookup"><span data-stu-id="2ad64-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}e^{i\theta_j}\ket{j}\bra{j}.</span></span>
<span data-ttu-id="2ad64-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="2ad64-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="2ad64-111">输入</span><span class="sxs-lookup"><span data-stu-id="2ad64-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="2ad64-112">容差： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2ad64-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2ad64-113">小于其小系数的公差将被截断。</span><span class="sxs-lookup"><span data-stu-id="2ad64-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="2ad64-114">系数： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="2ad64-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="2ad64-115">最多 $ 2 ^ n $ 系数 $ \ theta_j $ 的数组。</span><span class="sxs-lookup"><span data-stu-id="2ad64-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="2ad64-116">$J $ th 用于索引以小字节序格式编码的数字状态 $ \ket{j} $。</span><span class="sxs-lookup"><span data-stu-id="2ad64-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="2ad64-117">qubits： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2ad64-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2ad64-118">$n 以小字节序格式编码数字状态 $ \ket{j} $ 的 qubit 控制寄存器。</span><span class="sxs-lookup"><span data-stu-id="2ad64-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2ad64-119">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2ad64-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2ad64-120">注解</span><span class="sxs-lookup"><span data-stu-id="2ad64-120">Remarks</span></span>

<span data-ttu-id="2ad64-121">`coefficients` 如果指定少于 $ 2 ^ n $，则将用元素 $ \ theta_j = $0.0 填充。</span><span class="sxs-lookup"><span data-stu-id="2ad64-121">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="2ad64-122">参考</span><span class="sxs-lookup"><span data-stu-id="2ad64-122">References</span></span>

- <span data-ttu-id="2ad64-123">量程逻辑电路的合成 Vivek Shende、Stephen Bullock、Igor Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="2ad64-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="2ad64-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ad64-124">See Also</span></span>

- [<span data-ttu-id="2ad64-125">Canon. ApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="2ad64-125">Microsoft.Quantum.Canon.ApplyDiagonalUnitary</span></span>](xref:Microsoft.Quantum.Canon.ApplyDiagonalUnitary)