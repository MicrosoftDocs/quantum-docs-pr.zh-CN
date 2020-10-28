---
uid: Microsoft.Quantum.Canon.MultiplexPauli
title: MultiplexPauli 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexPauli
qsharp.summary: Applies a Pauli rotation conditioned on an array of qubits.
ms.openlocfilehash: 0714e796c1e5ad097814bcf507f49f59a844e9ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695999"
---
# <a name="multiplexpauli-operation"></a><span data-ttu-id="8532b-102">MultiplexPauli 操作</span><span class="sxs-lookup"><span data-stu-id="8532b-102">MultiplexPauli operation</span></span>

<span data-ttu-id="8532b-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8532b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8532b-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8532b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8532b-105">对 qubits 数组应用 Pauli 旋转。</span><span class="sxs-lookup"><span data-stu-id="8532b-105">Applies a Pauli rotation conditioned on an array of qubits.</span></span>

```qsharp
operation MultiplexPauli (coefficients : Double[], pauli : Pauli, control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="8532b-106">说明</span><span class="sxs-lookup"><span data-stu-id="8532b-106">Description</span></span>

<span data-ttu-id="8532b-107">这会应用一次受控的单一操作，该操作会按角度 $ theta_j \ qubit Pauli operator $P $ （由 $n $-qubit 号 state $ \ket{j} $ 控制）执行旋转。</span><span class="sxs-lookup"><span data-stu-id="8532b-107">This applies a multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $P$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="8532b-108">特别是，此操作的操作由单一</span><span class="sxs-lookup"><span data-stu-id="8532b-108">In particular, the action of this operation is represented by the unitary</span></span>

<span data-ttu-id="8532b-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i P \ theta_j}。</span><span class="sxs-lookup"><span data-stu-id="8532b-109">$$ \begin{align} U = \sum^{2^n - 1}_{j=0} \ket{j}\bra{j} \otimes e^{i P \theta_j}.</span></span>
<span data-ttu-id="8532b-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="8532b-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="8532b-111">输入</span><span class="sxs-lookup"><span data-stu-id="8532b-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="8532b-112">系数： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="8532b-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="8532b-113">最多 $ 2 ^ n $ 系数 $ \ theta_j $ 的数组。</span><span class="sxs-lookup"><span data-stu-id="8532b-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="8532b-114">$J $ th 用于索引以小字节序格式编码的数字状态 $ \ket{j} $。</span><span class="sxs-lookup"><span data-stu-id="8532b-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="pauli--pauli"></a><span data-ttu-id="8532b-115">pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="8532b-115">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="8532b-116">Pauli 运算符 $P $，它确定旋转的轴。</span><span class="sxs-lookup"><span data-stu-id="8532b-116">Pauli operator $P$ that determines axis of rotation.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="8532b-117">控件： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8532b-117">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="8532b-118">$n 以小字节序格式编码数字状态 $ \ket{j} $ 的 qubit 控制寄存器。</span><span class="sxs-lookup"><span data-stu-id="8532b-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="8532b-119">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8532b-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8532b-120">通过 $e ^ {i P \ theta_j} $ 旋转的单个 qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="8532b-120">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8532b-121">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8532b-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8532b-122">注解</span><span class="sxs-lookup"><span data-stu-id="8532b-122">Remarks</span></span>

<span data-ttu-id="8532b-123">`coefficients` 如果指定少于 $ 2 ^ n $，则将用元素 $ \ theta_j = $0.0 填充。</span><span class="sxs-lookup"><span data-stu-id="8532b-123">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="see-also"></a><span data-ttu-id="8532b-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8532b-124">See Also</span></span>

- [<span data-ttu-id="8532b-125">Canon. ApproximatelyMultiplexPauli</span><span class="sxs-lookup"><span data-stu-id="8532b-125">Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli)