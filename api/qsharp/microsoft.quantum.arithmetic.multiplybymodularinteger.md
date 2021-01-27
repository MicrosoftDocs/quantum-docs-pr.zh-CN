---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: MultiplyByModularInteger 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: bd4e0ad6c5bad779d9a31139690021fd9fcda210
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846493"
---
# <a name="multiplybymodularinteger-operation"></a><span data-ttu-id="4b807-102">MultiplyByModularInteger 操作</span><span class="sxs-lookup"><span data-stu-id="4b807-102">MultiplyByModularInteger operation</span></span>

<span data-ttu-id="4b807-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4b807-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4b807-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4b807-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4b807-105">对 qubit 寄存器上的整数常量执行模块化乘法运算。</span><span class="sxs-lookup"><span data-stu-id="4b807-105">Performs modular multiplication by an integer constant on a qubit register.</span></span>

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="4b807-106">说明</span><span class="sxs-lookup"><span data-stu-id="4b807-106">Description</span></span>

<span data-ttu-id="4b807-107">让我们 `modulus` 通过 $N $ 和 `constMultiplier` $a $ 来表示。</span><span class="sxs-lookup"><span data-stu-id="4b807-107">Let us denote `modulus` by $N$ and `constMultiplier` by $a$.</span></span>
<span data-ttu-id="4b807-108">然后，此操作实现了以下映射定义的单一操作： $ $ \begin{align} \ket{y} \mapsto \ket{ (\cdot y) \operatorname{mod} N} \end{align} $ $，用于 $0 $ 和 $N-$1 之间的所有 $y $。</span><span class="sxs-lookup"><span data-stu-id="4b807-108">Then this operation implements a unitary operation defined by the following map on the computational basis: $$ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $$ for all $y$ between $0$ and $N - 1$.</span></span>

## <a name="input"></a><span data-ttu-id="4b807-109">输入</span><span class="sxs-lookup"><span data-stu-id="4b807-109">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="4b807-110">constMultiplier： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4b807-110">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4b807-111">乘数相乘的常量。</span><span class="sxs-lookup"><span data-stu-id="4b807-111">Constant by which multiplier is being multiplied.</span></span> <span data-ttu-id="4b807-112">必须与模数共同。</span><span class="sxs-lookup"><span data-stu-id="4b807-112">Must be co-prime to modulus.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="4b807-113">取模： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4b807-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4b807-114">乘法运算执行取模运算 `modulus` 。</span><span class="sxs-lookup"><span data-stu-id="4b807-114">The multiplication operation is performed modulo `modulus`.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="4b807-115">乘法器： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4b807-115">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4b807-116">与常量相乘的数字。</span><span class="sxs-lookup"><span data-stu-id="4b807-116">The number being multiplied by a constant.</span></span>
<span data-ttu-id="4b807-117">这是一个 qubits 编码数组，用小 endian 格式的整数编码。</span><span class="sxs-lookup"><span data-stu-id="4b807-117">This is an array of qubits encoding an integer in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4b807-118">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4b807-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4b807-119">备注</span><span class="sxs-lookup"><span data-stu-id="4b807-119">Remarks</span></span>

- <span data-ttu-id="4b807-120">对于 "线路" 关系图和解释，请参阅 [arXiv 的第8页上的图7： quant/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span><span class="sxs-lookup"><span data-stu-id="4b807-120">For the circuit diagram and explanation see Figure 7 on [Page 8 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span></span>
- <span data-ttu-id="4b807-121">此操作对应于 ArXiv 中的 U ₐ [： quant/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span><span class="sxs-lookup"><span data-stu-id="4b807-121">This operation corresponds to Uₐ in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>