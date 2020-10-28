---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: BlockEncodingByLCU 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 04738aa54ce8b719b05954824e3553388a995df0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700964"
---
# <a name="blockencodingbylcu-function"></a><span data-ttu-id="0a8bc-102">BlockEncodingByLCU 函数</span><span class="sxs-lookup"><span data-stu-id="0a8bc-102">BlockEncodingByLCU function</span></span>

<span data-ttu-id="0a8bc-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="0a8bc-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="0a8bc-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0a8bc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0a8bc-105">将感兴趣的运算符编码为 `BlockEncoding` 。</span><span class="sxs-lookup"><span data-stu-id="0a8bc-105">Encodes an operator of interest into a `BlockEncoding`.</span></span>

<span data-ttu-id="0a8bc-106">这将构造一个 `BlockEncoding` 单一 $U = P\cdot V\cdot P ^ \dagger $，用于对一些运算符进行编码 $H = \ sum_ {j} | \ alpha_j |U_j 是 unitaries 的线性组合。</span><span class="sxs-lookup"><span data-stu-id="0a8bc-106">This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries.</span></span> <span data-ttu-id="0a8bc-107">通常，$P $ 是一种状态准备，因此 $P \ket {0} \_ a = \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ $，$V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $。</span><span class="sxs-lookup"><span data-stu-id="0a8bc-107">Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.</span></span>

```qsharp
function BlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl)) : (('T, 'S) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="0a8bc-108">输入</span><span class="sxs-lookup"><span data-stu-id="0a8bc-108">Input</span></span>

### <a name="statepreparation--t--unit-adj--ctl"></a><span data-ttu-id="0a8bc-109">statePreparation：不等于> [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="0a8bc-109">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="0a8bc-110">准备某些目标状态的单一 $P $。</span><span class="sxs-lookup"><span data-stu-id="0a8bc-110">A unitary $P$ that prepares some target state.</span></span>


### <a name="selector--ts--unit-adj--ctl"></a><span data-ttu-id="0a8bc-111">选择器： ( t，其) => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="0a8bc-111">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="0a8bc-112">一个单一 $V $，它对 $H $ 的组件 unitaries 进行编码。</span><span class="sxs-lookup"><span data-stu-id="0a8bc-112">A unitary $V$ that encodes the component unitaries of $H$.</span></span>



## <a name="output--ts--unit-adj--ctl"></a><span data-ttu-id="0a8bc-113">输出： ( t，其) => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="0a8bc-113">Output : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="0a8bc-114">单一 $U $ 对寄存器进行操作并对其 `a` `s` 进行块编码 $H $，并满足 $U ^ \Dagger = U $。</span><span class="sxs-lookup"><span data-stu-id="0a8bc-114">A unitary $U$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U^\dagger = U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0a8bc-115">类型参数</span><span class="sxs-lookup"><span data-stu-id="0a8bc-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0a8bc-116">找</span><span class="sxs-lookup"><span data-stu-id="0a8bc-116">'T</span></span>


### <a name="s"></a><span data-ttu-id="0a8bc-117">我们</span><span class="sxs-lookup"><span data-stu-id="0a8bc-117">'S</span></span>



## <a name="remarks"></a><span data-ttu-id="0a8bc-118">注解</span><span class="sxs-lookup"><span data-stu-id="0a8bc-118">Remarks</span></span>

<span data-ttu-id="0a8bc-119">此 `BlockEncoding` 实现为它提供了的属性 `BlockEncodingReflection` 。</span><span class="sxs-lookup"><span data-stu-id="0a8bc-119">This `BlockEncoding` implementation gives it the properties of a `BlockEncodingReflection`.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a8bc-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a8bc-120">See Also</span></span>

- [<span data-ttu-id="0a8bc-121">BlockEncoding。</span><span class="sxs-lookup"><span data-stu-id="0a8bc-121">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="0a8bc-122">BlockEncodingReflection。</span><span class="sxs-lookup"><span data-stu-id="0a8bc-122">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)