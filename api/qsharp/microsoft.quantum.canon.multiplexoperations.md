---
uid: Microsoft.Quantum.Canon.MultiplexOperations
title: MultiplexOperations 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperations
qsharp.summary: >-
  Applies an array of operations controlled by an array of number states.

  That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: ad66b39fcfacbe5231ec3b9ba96989d6d5d449c1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206096"
---
# <a name="multiplexoperations-operation"></a><span data-ttu-id="c79e2-102">MultiplexOperations 操作</span><span class="sxs-lookup"><span data-stu-id="c79e2-102">MultiplexOperations operation</span></span>

<span data-ttu-id="c79e2-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c79e2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c79e2-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c79e2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c79e2-105">应用由数值状态数组控制的操作的数组。</span><span class="sxs-lookup"><span data-stu-id="c79e2-105">Applies an array of operations controlled by an array of number states.</span></span>

<span data-ttu-id="c79e2-106">也就是说，应用 $U $ 的乘法控制的单一操作，该操作在通过 $n $-qubit number state $ \ket{j} $ 控制时应用单一 $V _j $。</span><span class="sxs-lookup"><span data-stu-id="c79e2-106">That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="c79e2-107">$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $。</span><span class="sxs-lookup"><span data-stu-id="c79e2-107">$U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperations<'T> (unitaries : ('T => Unit is Adj + Ctl)[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c79e2-108">输入</span><span class="sxs-lookup"><span data-stu-id="c79e2-108">Input</span></span>

### <a name="unitaries--t--unit--is-adj--ctl"></a><span data-ttu-id="c79e2-109">unitaries： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl []</span><span class="sxs-lookup"><span data-stu-id="c79e2-109">unitaries : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="c79e2-110">最多 $ 2 ^ n $ 单一操作的数组。</span><span class="sxs-lookup"><span data-stu-id="c79e2-110">Array of up to $2^n$ unitary operations.</span></span> <span data-ttu-id="c79e2-111">$J $ th 操作由以小字节序格式编码的数字状态 $ \ket{j} $ 进行索引。</span><span class="sxs-lookup"><span data-stu-id="c79e2-111">The $j$th operation is indexed by the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="c79e2-112">index： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c79e2-112">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c79e2-113">$n 以小字节序格式编码数字状态 $ \ket{j} $ 的 qubit 控制寄存器。</span><span class="sxs-lookup"><span data-stu-id="c79e2-113">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="c79e2-114">目标： t</span><span class="sxs-lookup"><span data-stu-id="c79e2-114">target : 'T</span></span>

<span data-ttu-id="c79e2-115">泛型 qubit 注册 $V _j $ 作用于。</span><span class="sxs-lookup"><span data-stu-id="c79e2-115">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c79e2-116">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c79e2-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c79e2-117">类型参数</span><span class="sxs-lookup"><span data-stu-id="c79e2-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c79e2-118">找</span><span class="sxs-lookup"><span data-stu-id="c79e2-118">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="c79e2-119">备注</span><span class="sxs-lookup"><span data-stu-id="c79e2-119">Remarks</span></span>

<span data-ttu-id="c79e2-120">`coefficients` 如果指定少于 $ 2 ^ n $，则将用标识元素填充。</span><span class="sxs-lookup"><span data-stu-id="c79e2-120">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="c79e2-121">此实现使用 $n-$1 辅助 qubits。</span><span class="sxs-lookup"><span data-stu-id="c79e2-121">This implementation uses $n - 1$ auxiliary qubits.</span></span>

## <a name="references"></a><span data-ttu-id="c79e2-122">参考</span><span class="sxs-lookup"><span data-stu-id="c79e2-122">References</span></span>

- <span data-ttu-id="c79e2-123">对于具有量程加速的第一个量子模拟，Andrew Childs，Dmitri Maslov，Yunseong，Neil，Ross，人民币元 Su https://arxiv.org/abs/1711.10980</span><span class="sxs-lookup"><span data-stu-id="c79e2-123">Toward the first quantum simulation with quantum speedup Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan Su https://arxiv.org/abs/1711.10980</span></span>