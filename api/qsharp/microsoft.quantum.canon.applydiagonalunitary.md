---
uid: Microsoft.Quantum.Canon.ApplyDiagonalUnitary
title: ApplyDiagonalUnitary 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits.
ms.openlocfilehash: 6ecacf6e4fe2c505036de208c8aeb5350e479e3c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696358"
---
# <a name="applydiagonalunitary-operation"></a><span data-ttu-id="fdd17-102">ApplyDiagonalUnitary 操作</span><span class="sxs-lookup"><span data-stu-id="fdd17-102">ApplyDiagonalUnitary operation</span></span>

<span data-ttu-id="fdd17-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fdd17-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fdd17-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fdd17-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fdd17-105">将复杂阶段数组应用于 qubits 寄存器的数字基础状态。</span><span class="sxs-lookup"><span data-stu-id="fdd17-105">Applies an array of complex phases to numeric basis states of a register of qubits.</span></span>

```qsharp
operation ApplyDiagonalUnitary (coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="fdd17-106">说明</span><span class="sxs-lookup"><span data-stu-id="fdd17-106">Description</span></span>

<span data-ttu-id="fdd17-107">此操作实现在 $n $-qubit number state $ \ket{j} $ 上应用复杂阶段 $e ^ {i \ theta_j} $ 的对角线。</span><span class="sxs-lookup"><span data-stu-id="fdd17-107">This operation implements a diagonal unitary that applies a complex phase $e^{i \theta_j}$ on the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="fdd17-108">具体而言，此操作可由单一</span><span class="sxs-lookup"><span data-stu-id="fdd17-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="fdd17-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} e ^ {i \ theta_j} \ket{j}\bra{j}。</span><span class="sxs-lookup"><span data-stu-id="fdd17-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}e^{i\theta_j}\ket{j}\bra{j}.</span></span>
<span data-ttu-id="fdd17-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="fdd17-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="fdd17-111">输入</span><span class="sxs-lookup"><span data-stu-id="fdd17-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="fdd17-112">系数： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="fdd17-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="fdd17-113">最多 $ 2 ^ n $ 系数 $ \ theta_j $ 的数组。</span><span class="sxs-lookup"><span data-stu-id="fdd17-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="fdd17-114">$J $ th 用于索引以小字节序格式编码的数字状态 $ \ket{j} $。</span><span class="sxs-lookup"><span data-stu-id="fdd17-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="fdd17-115">qubits： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="fdd17-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="fdd17-116">$n 以小字节序格式编码数字状态 $ \ket{j} $ 的 qubit 控制寄存器。</span><span class="sxs-lookup"><span data-stu-id="fdd17-116">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fdd17-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fdd17-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="fdd17-118">注解</span><span class="sxs-lookup"><span data-stu-id="fdd17-118">Remarks</span></span>

<span data-ttu-id="fdd17-119">`coefficients` 如果指定少于 $ 2 ^ n $，则将用元素 $ \ theta_j = $0.0 填充。</span><span class="sxs-lookup"><span data-stu-id="fdd17-119">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="fdd17-120">参考</span><span class="sxs-lookup"><span data-stu-id="fdd17-120">References</span></span>

- <span data-ttu-id="fdd17-121">量程逻辑电路的合成 Vivek Shende、Stephen Bullock、Igor Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="fdd17-121">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="fdd17-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fdd17-122">See Also</span></span>

- [<span data-ttu-id="fdd17-123">Canon. ApproximatelyApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="fdd17-123">Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary)