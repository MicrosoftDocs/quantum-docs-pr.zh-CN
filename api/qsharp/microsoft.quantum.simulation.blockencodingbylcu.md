---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: BlockEncodingByLCU 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 1d7890e96513817c127ef768f49c0b915ea22fa1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858166"
---
# <a name="blockencodingbylcu-function"></a><span data-ttu-id="fa46c-102">BlockEncodingByLCU 函数</span><span class="sxs-lookup"><span data-stu-id="fa46c-102">BlockEncodingByLCU function</span></span>

<span data-ttu-id="fa46c-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="fa46c-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="fa46c-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fa46c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fa46c-105">将感兴趣的运算符编码为 `BlockEncoding` 。</span><span class="sxs-lookup"><span data-stu-id="fa46c-105">Encodes an operator of interest into a `BlockEncoding`.</span></span>

<span data-ttu-id="fa46c-106">这将构造一个 `BlockEncoding` 单一 $U = P\cdot V\cdot P ^ \dagger $，用于对一些运算符进行编码 $H = \ sum_ {j} | \ alpha_j |U_j 是 unitaries 的线性组合。</span><span class="sxs-lookup"><span data-stu-id="fa46c-106">This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries.</span></span> <span data-ttu-id="fa46c-107">通常，$P $ 是一种状态准备，因此 $P \ket {0} \_ a = \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ $，$V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $。</span><span class="sxs-lookup"><span data-stu-id="fa46c-107">Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.</span></span>

```qsharp
function BlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl)) : (('T, 'S) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="fa46c-108">输入</span><span class="sxs-lookup"><span data-stu-id="fa46c-108">Input</span></span>

### <a name="statepreparation--t--unit--is-adj--ctl"></a><span data-ttu-id="fa46c-109">statePreparation： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="fa46c-109">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="fa46c-110">准备某些目标状态的单一 $P $。</span><span class="sxs-lookup"><span data-stu-id="fa46c-110">A unitary $P$ that prepares some target state.</span></span>


### <a name="selector--ts--unit--is-adj--ctl"></a><span data-ttu-id="fa46c-111">选择器： ( t，其) => [单位](xref:microsoft.quantum.lang-ref.unit)  为调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="fa46c-111">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="fa46c-112">一个单一 $V $，它对 $H $ 的组件 unitaries 进行编码。</span><span class="sxs-lookup"><span data-stu-id="fa46c-112">A unitary $V$ that encodes the component unitaries of $H$.</span></span>



## <a name="output--ts--unit--is-adj--ctl"></a><span data-ttu-id="fa46c-113">输出： ( t，其) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="fa46c-113">Output : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="fa46c-114">单一 $U $ 对寄存器进行操作并对其 `a` `s` 进行块编码 $H $，并满足 $U ^ \Dagger = U $。</span><span class="sxs-lookup"><span data-stu-id="fa46c-114">A unitary $U$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U^\dagger = U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fa46c-115">类型参数</span><span class="sxs-lookup"><span data-stu-id="fa46c-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fa46c-116">找</span><span class="sxs-lookup"><span data-stu-id="fa46c-116">'T</span></span>


### <a name="s"></a><span data-ttu-id="fa46c-117">我们</span><span class="sxs-lookup"><span data-stu-id="fa46c-117">'S</span></span>



## <a name="remarks"></a><span data-ttu-id="fa46c-118">备注</span><span class="sxs-lookup"><span data-stu-id="fa46c-118">Remarks</span></span>

<span data-ttu-id="fa46c-119">此 `BlockEncoding` 实现为它提供了的属性 `BlockEncodingReflection` 。</span><span class="sxs-lookup"><span data-stu-id="fa46c-119">This `BlockEncoding` implementation gives it the properties of a `BlockEncodingReflection`.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa46c-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa46c-120">See Also</span></span>

- [<span data-ttu-id="fa46c-121">BlockEncoding。</span><span class="sxs-lookup"><span data-stu-id="fa46c-121">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="fa46c-122">BlockEncodingReflection。</span><span class="sxs-lookup"><span data-stu-id="fa46c-122">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)