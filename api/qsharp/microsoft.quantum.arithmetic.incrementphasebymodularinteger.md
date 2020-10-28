---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger
title: IncrementPhaseByModularInteger 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 52309c056a3eae25ffdfbfa848f94bf744c71132
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699845"
---
# <a name="incrementphasebymodularinteger-operation"></a><span data-ttu-id="9dfb6-102">IncrementPhaseByModularInteger 操作</span><span class="sxs-lookup"><span data-stu-id="9dfb6-102">IncrementPhaseByModularInteger operation</span></span>

<span data-ttu-id="9dfb6-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9dfb6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9dfb6-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9dfb6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9dfb6-105">按整数常量执行 qubit 寄存器的模块化增量。</span><span class="sxs-lookup"><span data-stu-id="9dfb6-105">Performs a modular increment of a qubit register by an integer constant.</span></span>

```qsharp
operation IncrementPhaseByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="9dfb6-106">说明</span><span class="sxs-lookup"><span data-stu-id="9dfb6-106">Description</span></span>

<span data-ttu-id="9dfb6-107">通过 `increment` `modulus` $y $ $N $ 和在中编码的整数，让我们以 $a $ 表示。 `target`</span><span class="sxs-lookup"><span data-stu-id="9dfb6-107">Let us denote `increment` by $a$, `modulus` by $N$ and integer encoded in `target` by $y$.</span></span>
<span data-ttu-id="9dfb6-108">然后，该操作将执行以下转换： \begin{align} \ket{y} \mapsto \ket{ (y + a) \operatorname{mod} N} \end{align} 将以小字节序格式编码。</span><span class="sxs-lookup"><span data-stu-id="9dfb6-108">Then the operation performs the following transformation: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Integers are encoded in little-endian format in QFT basis.</span></span>

## <a name="input"></a><span data-ttu-id="9dfb6-109">输入</span><span class="sxs-lookup"><span data-stu-id="9dfb6-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="9dfb6-110">增量： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9dfb6-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9dfb6-111">要添加到 $y $ $a $ 的整数增量。</span><span class="sxs-lookup"><span data-stu-id="9dfb6-111">Integer increment $a$ to be added to $y$.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="9dfb6-112">取模： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9dfb6-112">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9dfb6-113">整数 $N $ mods $y + a $。</span><span class="sxs-lookup"><span data-stu-id="9dfb6-113">Integer $N$ that mods $y + a$.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="9dfb6-114">目标： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9dfb6-114">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="9dfb6-115">$A $ 添加到的、阶段编码的小字节序格式的整数 $y $ `increment` 。</span><span class="sxs-lookup"><span data-stu-id="9dfb6-115">Integer $y$ in phase-encoded little-endian format that `increment` $a$ is added to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9dfb6-116">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9dfb6-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9dfb6-117">注解</span><span class="sxs-lookup"><span data-stu-id="9dfb6-117">Remarks</span></span>

<span data-ttu-id="9dfb6-118">假定 `target` 将最高位设置为0。</span><span class="sxs-lookup"><span data-stu-id="9dfb6-118">Assumes that `target` has the highest bit set to 0.</span></span>
<span data-ttu-id="9dfb6-119">还假定目标值小于 $N $。</span><span class="sxs-lookup"><span data-stu-id="9dfb6-119">Also assumes that the value of target is less than $N$.</span></span>

<span data-ttu-id="9dfb6-120">对于 "线路" 关系图和说明，请参阅 [arXiv： quant/0205095V3 第5页](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5)上的图5。</span><span class="sxs-lookup"><span data-stu-id="9dfb6-120">For the circuit diagram and explanation see Figure 5 on [Page 5 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5).</span></span>

## <a name="see-also"></a><span data-ttu-id="9dfb6-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9dfb6-121">See Also</span></span>

- [<span data-ttu-id="9dfb6-122">IncrementByModularInteger。</span><span class="sxs-lookup"><span data-stu-id="9dfb6-122">Microsoft.Quantum.Arithmetic.IncrementByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByModularInteger)