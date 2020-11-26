---
uid: Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator
title: MultiplexOperationsFromGenerator 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsFromGenerator
qsharp.summary: >-
  Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 9fbbd9268d4a6b9f3d5fd203969f4bbeebe81b68
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205943"
---
# <a name="multiplexoperationsfromgenerator-operation"></a><span data-ttu-id="300d9-102">MultiplexOperationsFromGenerator 操作</span><span class="sxs-lookup"><span data-stu-id="300d9-102">MultiplexOperationsFromGenerator operation</span></span>

<span data-ttu-id="300d9-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="300d9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="300d9-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="300d9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="300d9-105">应用 $U $ 的乘法控制的单一操作，该操作将应用单一 $V _j $，由 n qubit number state $ \ket{j} $ 控制。</span><span class="sxs-lookup"><span data-stu-id="300d9-105">Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="300d9-106">$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $。</span><span class="sxs-lookup"><span data-stu-id="300d9-106">$U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperationsFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="300d9-107">输入</span><span class="sxs-lookup"><span data-stu-id="300d9-107">Input</span></span>

### <a name="unitarygenerator--intint---t--unit--is-adj--ctl"></a><span data-ttu-id="300d9-108">unitaryGenerator： ([int](xref:microsoft.quantum.lang-ref.int)，[Int](xref:microsoft.quantum.lang-ref.int) -> t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl) </span><span class="sxs-lookup"><span data-stu-id="300d9-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

<span data-ttu-id="300d9-109">一个元组，其中第一个元素 `Int` 是 unitaries $N $ 的数量，第二个元素 `(Int -> ('T => () is Adj + Ctl))` 是在 $ [0，N-1] $ 中采用整数 $j $ 并输出单一运算 $V _j $ 的函数。</span><span class="sxs-lookup"><span data-stu-id="300d9-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="300d9-110">index： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="300d9-110">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="300d9-111">$n 以小字节序格式编码数字状态 $ \ket{j} $ 的 qubit 控制寄存器。</span><span class="sxs-lookup"><span data-stu-id="300d9-111">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="300d9-112">目标： t</span><span class="sxs-lookup"><span data-stu-id="300d9-112">target : 'T</span></span>

<span data-ttu-id="300d9-113">泛型 qubit 注册 $V _j $ 作用于。</span><span class="sxs-lookup"><span data-stu-id="300d9-113">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="300d9-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="300d9-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="300d9-115">类型参数</span><span class="sxs-lookup"><span data-stu-id="300d9-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="300d9-116">找</span><span class="sxs-lookup"><span data-stu-id="300d9-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="300d9-117">备注</span><span class="sxs-lookup"><span data-stu-id="300d9-117">Remarks</span></span>

<span data-ttu-id="300d9-118">`coefficients` 如果指定少于 $ 2 ^ n $，则将用标识元素填充。</span><span class="sxs-lookup"><span data-stu-id="300d9-118">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="300d9-119">此实现使用 $n-$1 辅助 qubits。</span><span class="sxs-lookup"><span data-stu-id="300d9-119">This implementation uses $n-1$ auxiliary qubits.</span></span>

## <a name="references"></a><span data-ttu-id="300d9-120">参考</span><span class="sxs-lookup"><span data-stu-id="300d9-120">References</span></span>

- [<span data-ttu-id="300d9-121">*Andrew，Childs，Dmitri Maslov，Yunseong，Neil*，Ross，人民币元 Su，arXiv：1711.10980</span><span class="sxs-lookup"><span data-stu-id="300d9-121"> *Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan Su*, arXiv:1711.10980</span></span>](https://arxiv.org/abs/1711.10980)