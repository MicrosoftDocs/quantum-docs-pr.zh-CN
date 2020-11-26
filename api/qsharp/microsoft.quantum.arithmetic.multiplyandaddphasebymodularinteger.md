---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: MultiplyAndAddPhaseByModularInteger 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: 1ca20b525d2a76e554d5a2e8d4f40060b5ef51cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223861"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a><span data-ttu-id="4a04d-102">MultiplyAndAddPhaseByModularInteger 操作</span><span class="sxs-lookup"><span data-stu-id="4a04d-102">MultiplyAndAddPhaseByModularInteger operation</span></span>

<span data-ttu-id="4a04d-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4a04d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4a04d-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4a04d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4a04d-105">与 MultiplyAndAddByModularInteger 相同，但假定被加数将整数编码为 QFT。</span><span class="sxs-lookup"><span data-stu-id="4a04d-105">The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.</span></span>

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4a04d-106">输入</span><span class="sxs-lookup"><span data-stu-id="4a04d-106">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="4a04d-107">constMultiplier： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4a04d-107">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4a04d-108">要添加到每个基础状态标签的整数 $a $。</span><span class="sxs-lookup"><span data-stu-id="4a04d-108">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="4a04d-109">取模： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4a04d-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4a04d-110">取模 $N $，将对执行加法和乘法运算。</span><span class="sxs-lookup"><span data-stu-id="4a04d-110">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="4a04d-111">乘法器： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4a04d-111">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4a04d-112">一个量程寄存器，表示其值要添加到的每个基本状态标签的无符号整数 `summand` 。</span><span class="sxs-lookup"><span data-stu-id="4a04d-112">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="phasesummand--phaselittleendian"></a><span data-ttu-id="4a04d-113">phaseSummand： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4a04d-113">phaseSummand : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="4a04d-114">一个量程寄存器，表示要用作此操作的目标的无符号整数。</span><span class="sxs-lookup"><span data-stu-id="4a04d-114">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4a04d-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4a04d-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4a04d-116">备注</span><span class="sxs-lookup"><span data-stu-id="4a04d-116">Remarks</span></span>

<span data-ttu-id="4a04d-117">假定 `phaseSummand` 将最高位设置为0。</span><span class="sxs-lookup"><span data-stu-id="4a04d-117">Assumes that `phaseSummand` has the highest bit set to 0.</span></span>
<span data-ttu-id="4a04d-118">还假定的值 `phaseSummand` 小于 $N $。</span><span class="sxs-lookup"><span data-stu-id="4a04d-118">Also assumes that the value of `phaseSummand` is less than $N$.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a04d-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a04d-119">See Also</span></span>

- [<span data-ttu-id="4a04d-120">MultiplyAndAddByModularInteger。</span><span class="sxs-lookup"><span data-stu-id="4a04d-120">Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)