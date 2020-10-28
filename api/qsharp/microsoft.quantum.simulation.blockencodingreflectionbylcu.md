---
uid: Microsoft.Quantum.Simulation.BlockEncodingReflectionByLCU
title: BlockEncodingReflectionByLCU 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingReflectionByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncodingReflection`.

  This constructs a `BlockEncodingReflection` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: b8eff9d207752213ccdf42a9ad80fefb2da07216
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700693"
---
# <a name="blockencodingreflectionbylcu-function"></a><span data-ttu-id="a827d-102">BlockEncodingReflectionByLCU 函数</span><span class="sxs-lookup"><span data-stu-id="a827d-102">BlockEncodingReflectionByLCU function</span></span>

<span data-ttu-id="a827d-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="a827d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="a827d-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a827d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a827d-105">将感兴趣的运算符编码为 `BlockEncodingReflection` 。</span><span class="sxs-lookup"><span data-stu-id="a827d-105">Encodes an operator of interest into a `BlockEncodingReflection`.</span></span>

<span data-ttu-id="a827d-106">这将构造一个 `BlockEncodingReflection` 单一 $U = P\cdot V\cdot P ^ \dagger $，用于对一些运算符进行编码 $H = \ sum_ {j} | \ alpha_j |U_j 是 unitaries 的线性组合。</span><span class="sxs-lookup"><span data-stu-id="a827d-106">This constructs a `BlockEncodingReflection` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries.</span></span> <span data-ttu-id="a827d-107">通常情况下，$P $ 是一种状态准备，$P \ket {0} \_ a \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ $，$V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $。</span><span class="sxs-lookup"><span data-stu-id="a827d-107">Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.</span></span>

```qsharp
function BlockEncodingReflectionByLCU (statePreparation : (Qubit[] => Unit is Adj + Ctl), selector : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a><span data-ttu-id="a827d-108">输入</span><span class="sxs-lookup"><span data-stu-id="a827d-108">Input</span></span>

### <a name="statepreparation--qubit--unit-adj--ctl"></a><span data-ttu-id="a827d-109">statePreparation： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="a827d-109">statePreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="a827d-110">准备某些目标状态的单一 $P $。</span><span class="sxs-lookup"><span data-stu-id="a827d-110">A unitary $P$ that prepares some target state.</span></span>


### <a name="selector--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="a827d-111">选择器： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[]，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="a827d-111">selector : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="a827d-112">一个单一 $V $，它对 $H $ 的组件 unitaries 进行编码。</span><span class="sxs-lookup"><span data-stu-id="a827d-112">A unitary $V$ that encodes the component unitaries of $H$.</span></span>



## <a name="output--blockencodingreflection"></a><span data-ttu-id="a827d-113">输出： [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="a827d-113">Output : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="a827d-114">单一 $U $ 对寄存器进行操作并对其 `a` `s` 进行块编码 $H $，并满足 $U "^ {-1} = U $。</span><span class="sxs-lookup"><span data-stu-id="a827d-114">A unitary $U$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U'^{-1} = U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="a827d-115">注解</span><span class="sxs-lookup"><span data-stu-id="a827d-115">Remarks</span></span>

<span data-ttu-id="a827d-116">此 `BlockEncoding` 实现为它提供了的属性 `BlockEncodingReflection` 。</span><span class="sxs-lookup"><span data-stu-id="a827d-116">This `BlockEncoding` implementation gives it the properties of a `BlockEncodingReflection`.</span></span>

## <a name="see-also"></a><span data-ttu-id="a827d-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a827d-117">See Also</span></span>

- [<span data-ttu-id="a827d-118">BlockEncoding。</span><span class="sxs-lookup"><span data-stu-id="a827d-118">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="a827d-119">BlockEncodingReflection。</span><span class="sxs-lookup"><span data-stu-id="a827d-119">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)