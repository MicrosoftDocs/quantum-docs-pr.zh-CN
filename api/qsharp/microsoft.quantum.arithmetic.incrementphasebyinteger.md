---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: IncrementPhaseByInteger 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: fb67455dadbc7a2f38880581f0e413a747faa8ef
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699852"
---
# <a name="incrementphasebyinteger-operation"></a><span data-ttu-id="fab48-102">IncrementPhaseByInteger 操作</span><span class="sxs-lookup"><span data-stu-id="fab48-102">IncrementPhaseByInteger operation</span></span>

<span data-ttu-id="fab48-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="fab48-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="fab48-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fab48-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fab48-105">使用阶段旋转，将未签名的量程寄存器增加一个传统整数。</span><span class="sxs-lookup"><span data-stu-id="fab48-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="fab48-106">说明</span><span class="sxs-lookup"><span data-stu-id="fab48-106">Description</span></span>

<span data-ttu-id="fab48-107">假定将 `target` 无符号整数编码 $x $ in 小字节序编码，并且 `increment` 等于 $a $。</span><span class="sxs-lookup"><span data-stu-id="fab48-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="fab48-108">然后，此操作实现一个单一 $ \ket{x} \mapsto \ket{x + a} $，其中添加操作执行取模 $ 2 ^ n $，其中 $n = \texttt{Length (target！ ) } $。</span><span class="sxs-lookup"><span data-stu-id="fab48-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="fab48-109">输入</span><span class="sxs-lookup"><span data-stu-id="fab48-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="fab48-110">增量： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fab48-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fab48-111">的整数，该整数用于 `target` 递增。</span><span class="sxs-lookup"><span data-stu-id="fab48-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="fab48-112">目标： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="fab48-112">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="fab48-113">在双 (QFT) 基础上，量程寄存器使用小字节序编码对无符号整数进行编码。</span><span class="sxs-lookup"><span data-stu-id="fab48-113">A quantum register encoding an unsigned integer using little-endian encoding in the dual (QFT) basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fab48-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fab48-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="fab48-115">注解</span><span class="sxs-lookup"><span data-stu-id="fab48-115">Remarks</span></span>

<span data-ttu-id="fab48-116">请注意，我们已简化了此线路，因为增量为传统常量，而不是量程寄存器。</span><span class="sxs-lookup"><span data-stu-id="fab48-116">Note that we have simplified the circuit because the increment is a classical constant, not a quantum register.</span></span>

<span data-ttu-id="fab48-117">请参阅 [ arXiv： quant/0008033v1 的第6页 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) 上的图和说明。</span><span class="sxs-lookup"><span data-stu-id="fab48-117">See the figure on [ Page 6 of arXiv:quant-ph/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) for the circuit diagram and explanation.</span></span>

## <a name="references"></a><span data-ttu-id="fab48-118">参考</span><span class="sxs-lookup"><span data-stu-id="fab48-118">References</span></span>

- [<span data-ttu-id="fab48-119">*Thomas Draper* ，arXiv： quant/0008033</span><span class="sxs-lookup"><span data-stu-id="fab48-119"> *Thomas G. Draper* , arXiv:quant-ph/0008033</span></span>](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a><span data-ttu-id="fab48-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fab48-120">See Also</span></span>

- [<span data-ttu-id="fab48-121">IncrementByInteger。</span><span class="sxs-lookup"><span data-stu-id="fab48-121">Microsoft.Quantum.Arithmetic.IncrementByInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)