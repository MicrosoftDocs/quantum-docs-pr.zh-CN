---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli
title: ApproximatelyMultiplexPauli 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexPauli
qsharp.summary: Applies a Pauli rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: c91937d9e82a2a1514d81529adb35a5f804a0e13
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696146"
---
# <a name="approximatelymultiplexpauli-operation"></a><span data-ttu-id="923f2-102">ApproximatelyMultiplexPauli 操作</span><span class="sxs-lookup"><span data-stu-id="923f2-102">ApproximatelyMultiplexPauli operation</span></span>

<span data-ttu-id="923f2-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="923f2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="923f2-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="923f2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="923f2-105">应用对 qubits 数组使用的 Pauli 旋转，根据给定的公差截断小旋转角度。</span><span class="sxs-lookup"><span data-stu-id="923f2-105">Applies a Pauli rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyMultiplexPauli (tolerance : Double, coefficients : Double[], pauli : Pauli, control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="923f2-106">说明</span><span class="sxs-lookup"><span data-stu-id="923f2-106">Description</span></span>

<span data-ttu-id="923f2-107">这会应用一次受控的单一操作，该操作会按角度 $ theta_j \ qubit Pauli operator $P $ （由 $n $-qubit 号 state $ \ket{j} $ 控制）执行旋转。</span><span class="sxs-lookup"><span data-stu-id="923f2-107">This applies a multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $P$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="923f2-108">特别是，此操作的操作由单一</span><span class="sxs-lookup"><span data-stu-id="923f2-108">In particular, the action of this operation is represented by the unitary</span></span>

<span data-ttu-id="923f2-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i P \ theta_j}。</span><span class="sxs-lookup"><span data-stu-id="923f2-109">$$ \begin{align} U = \sum^{2^n - 1}_{j=0} \ket{j}\bra{j} \otimes e^{i P \theta_j}.</span></span>
<span data-ttu-id="923f2-110">\end{align}</span><span class="sxs-lookup"><span data-stu-id="923f2-110">\end{align}</span></span>

##

## <a name="input"></a><span data-ttu-id="923f2-111">输入</span><span class="sxs-lookup"><span data-stu-id="923f2-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="923f2-112">容差： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="923f2-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="923f2-113">小于其小系数的公差将被截断。</span><span class="sxs-lookup"><span data-stu-id="923f2-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="923f2-114">系数： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="923f2-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="923f2-115">最多 $ 2 ^ n $ 系数 $ \ theta_j $ 的数组。</span><span class="sxs-lookup"><span data-stu-id="923f2-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="923f2-116">$J $ th 用于索引以小字节序格式编码的数字状态 $ \ket{j} $。</span><span class="sxs-lookup"><span data-stu-id="923f2-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="pauli--pauli"></a><span data-ttu-id="923f2-117">pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="923f2-117">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="923f2-118">Pauli 运算符 $P $，它确定旋转的轴。</span><span class="sxs-lookup"><span data-stu-id="923f2-118">Pauli operator $P$ that determines axis of rotation.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="923f2-119">控件： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="923f2-119">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="923f2-120">$n 以小字节序格式编码数字状态 $ \ket{j} $ 的 qubit 控制寄存器。</span><span class="sxs-lookup"><span data-stu-id="923f2-120">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="923f2-121">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="923f2-121">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="923f2-122">通过 $e ^ {i P \ theta_j} $ 旋转的单个 qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="923f2-122">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="923f2-123">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="923f2-123">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="923f2-124">注解</span><span class="sxs-lookup"><span data-stu-id="923f2-124">Remarks</span></span>

<span data-ttu-id="923f2-125">`coefficients` 如果指定少于 $ 2 ^ n $，则将用元素 $ \ theta_j = $0.0 填充。</span><span class="sxs-lookup"><span data-stu-id="923f2-125">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="see-also"></a><span data-ttu-id="923f2-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="923f2-126">See Also</span></span>

- [<span data-ttu-id="923f2-127">Canon. MultiplexPauli</span><span class="sxs-lookup"><span data-stu-id="923f2-127">Microsoft.Quantum.Canon.MultiplexPauli</span></span>](xref:Microsoft.Quantum.Canon.MultiplexPauli)