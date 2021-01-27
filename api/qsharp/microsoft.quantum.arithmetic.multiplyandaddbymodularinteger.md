---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger
title: MultiplyAndAddByModularInteger 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddByModularInteger
qsharp.summary: Performs a modular multiply-and-add by integer constants on a qubit register.
ms.openlocfilehash: e4de934a5776e80dbf5f0d8334bf806e6a84b743
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846511"
---
# <a name="multiplyandaddbymodularinteger-operation"></a><span data-ttu-id="03546-102">MultiplyAndAddByModularInteger 操作</span><span class="sxs-lookup"><span data-stu-id="03546-102">MultiplyAndAddByModularInteger operation</span></span>

<span data-ttu-id="03546-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="03546-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="03546-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="03546-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="03546-105">对 qubit 寄存器上的整数常量执行模块化乘法和-add。</span><span class="sxs-lookup"><span data-stu-id="03546-105">Performs a modular multiply-and-add by integer constants on a qubit register.</span></span>

```qsharp
operation MultiplyAndAddByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, summand : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="03546-106">说明</span><span class="sxs-lookup"><span data-stu-id="03546-106">Description</span></span>

<span data-ttu-id="03546-107">为给定的取模实现 map $ $ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{ (b + a \cdot x) \operatorname{mod} N} \end{align} $ $ $N $，恒定乘数 $a $，被加数 $y $。</span><span class="sxs-lookup"><span data-stu-id="03546-107">Implements the map $$ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{align} $$ for a given modulus $N$, constant multiplier $a$, and summand $y$.</span></span>

## <a name="input"></a><span data-ttu-id="03546-108">输入</span><span class="sxs-lookup"><span data-stu-id="03546-108">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="03546-109">constMultiplier： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="03546-109">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="03546-110">要添加到每个基础状态标签的整数 $a $。</span><span class="sxs-lookup"><span data-stu-id="03546-110">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="03546-111">取模： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="03546-111">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="03546-112">取模 $N $，将对执行加法和乘法运算。</span><span class="sxs-lookup"><span data-stu-id="03546-112">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="03546-113">乘法器： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="03546-113">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="03546-114">一个量程寄存器，表示其值要添加到的每个基本状态标签的无符号整数 `summand` 。</span><span class="sxs-lookup"><span data-stu-id="03546-114">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="summand--littleendian"></a><span data-ttu-id="03546-115">被加数： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="03546-115">summand : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="03546-116">一个量程寄存器，表示要用作此操作的目标的无符号整数。</span><span class="sxs-lookup"><span data-stu-id="03546-116">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="03546-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="03546-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="03546-118">备注</span><span class="sxs-lookup"><span data-stu-id="03546-118">Remarks</span></span>

- <span data-ttu-id="03546-119">有关线路和说明，请参阅[arXiv： quant/0205095V3 第7页](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)上的图6</span><span class="sxs-lookup"><span data-stu-id="03546-119">For the circuit diagram and explanation see Figure 6 on [Page 7 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)</span></span>
- <span data-ttu-id="03546-120">此操作对应于 ArXiv 中的 CMULT () MOD (N) [： quant/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span><span class="sxs-lookup"><span data-stu-id="03546-120">This operation corresponds to CMULT(a)MOD(N) in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>

## <a name="see-also"></a><span data-ttu-id="03546-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="03546-121">See Also</span></span>

- [<span data-ttu-id="03546-122">MultiplyAndAddPhaseByModularInteger。</span><span class="sxs-lookup"><span data-stu-id="03546-122">Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger)