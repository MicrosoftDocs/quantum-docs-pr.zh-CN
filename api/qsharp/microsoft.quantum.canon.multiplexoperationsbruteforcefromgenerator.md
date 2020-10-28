---
uid: Microsoft.Quantum.Canon.MultiplexOperationsBruteForceFromGenerator
title: MultiplexOperationsBruteForceFromGenerator 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsBruteForceFromGenerator
qsharp.summary: >-
  Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 2a9bb083b121745bd556aac692d5dc85ffec3791
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696004"
---
# <a name="multiplexoperationsbruteforcefromgenerator-operation"></a><span data-ttu-id="a3e5e-102">MultiplexOperationsBruteForceFromGenerator 操作</span><span class="sxs-lookup"><span data-stu-id="a3e5e-102">MultiplexOperationsBruteForceFromGenerator operation</span></span>

<span data-ttu-id="a3e5e-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a3e5e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a3e5e-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a3e5e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a3e5e-105">应用 $U $ 的乘法控制的单一操作，该操作将应用单一 $V _j $，由 n qubit number state $ \ket{j} $ 控制。</span><span class="sxs-lookup"><span data-stu-id="a3e5e-105">Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="a3e5e-106">$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $。</span><span class="sxs-lookup"><span data-stu-id="a3e5e-106">$U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperationsBruteForceFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="a3e5e-107">输入</span><span class="sxs-lookup"><span data-stu-id="a3e5e-107">Input</span></span>

### <a name="unitarygenerator--intint---t--unit-adj--ctl"></a><span data-ttu-id="a3e5e-108">unitaryGenerator： ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int) -> = => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词 + Ctl) </span><span class="sxs-lookup"><span data-stu-id="a3e5e-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)</span></span>

<span data-ttu-id="a3e5e-109">一个元组，其中第一个元素 `Int` 是 unitaries $N $ 的数量，第二个元素 `(Int -> ('T => () is Adj + Ctl))` 是在 $ [0，N-1] $ 中采用整数 $j $ 并输出单一运算 $V _j $ 的函数。</span><span class="sxs-lookup"><span data-stu-id="a3e5e-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="a3e5e-110">index： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a3e5e-110">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a3e5e-111">$n 以小字节序格式编码数字状态 $ \ket{j} $ 的 qubit 控制寄存器。</span><span class="sxs-lookup"><span data-stu-id="a3e5e-111">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="a3e5e-112">目标： t</span><span class="sxs-lookup"><span data-stu-id="a3e5e-112">target : 'T</span></span>

<span data-ttu-id="a3e5e-113">泛型 qubit 注册 $V _j $ 作用于。</span><span class="sxs-lookup"><span data-stu-id="a3e5e-113">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a3e5e-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a3e5e-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a3e5e-115">类型参数</span><span class="sxs-lookup"><span data-stu-id="a3e5e-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a3e5e-116">找</span><span class="sxs-lookup"><span data-stu-id="a3e5e-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="a3e5e-117">注解</span><span class="sxs-lookup"><span data-stu-id="a3e5e-117">Remarks</span></span>

<span data-ttu-id="a3e5e-118">`coefficients` 如果指定少于 $ 2 ^ n $，则将用标识元素填充。</span><span class="sxs-lookup"><span data-stu-id="a3e5e-118">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="a3e5e-119">此版本通过通过 n 个控制的单一运算符循环直接实现。</span><span class="sxs-lookup"><span data-stu-id="a3e5e-119">This version is implemented directly by looping through n-controlled unitary operators.</span></span>