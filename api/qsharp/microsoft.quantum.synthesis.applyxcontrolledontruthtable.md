---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable
title: ApplyXControlledOnTruthTable 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTable
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: aa4e1bc0d5058228721728a894b896331ec626d1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203291"
---
# <a name="applyxcontrolledontruthtable-operation"></a><span data-ttu-id="d4ee8-102">ApplyXControlledOnTruthTable 操作</span><span class="sxs-lookup"><span data-stu-id="d4ee8-102">ApplyXControlledOnTruthTable operation</span></span>

<span data-ttu-id="d4ee8-103">命名空间 [：](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="d4ee8-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="d4ee8-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d4ee8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d4ee8-105">@"microsoft.quantum.intrinsic.x" `target` 如果布尔函数的 `func` 计算结果为 true （对于中的传统分配），则应用操作 `controlRegister` 。</span><span class="sxs-lookup"><span data-stu-id="d4ee8-105">Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.</span></span>

```qsharp
operation ApplyXControlledOnTruthTable (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="d4ee8-106">描述</span><span class="sxs-lookup"><span data-stu-id="d4ee8-106">Description</span></span>

<span data-ttu-id="d4ee8-107">此操作实现单一操作 \begin{align} U\ket {x} \ 票证 {y} = \ket{x}\ket{y \oplus f (x) } \end{align}，其中 $x $ 和 $y $ `controlRegister` 分别表示和 `target` 。</span><span class="sxs-lookup"><span data-stu-id="d4ee8-107">The operation implements the unitary operation \begin{align} U\ket{x}\ket{y} = \ket{x}\ket{y \oplus f(x)} \end{align} where $x$ and $y$ represent `controlRegister` and `target`, respectively.</span></span>

<span data-ttu-id="d4ee8-108">$F $ 的布尔函数以大整数表示为事实数据表。</span><span class="sxs-lookup"><span data-stu-id="d4ee8-108">The Boolean function $f$ is represented as a truth table in terms of a big integer.</span></span>
<span data-ttu-id="d4ee8-109">例如，在三个输入中的多数函数由 bitstring 表示 `11101000` ，其中最高有效位 `1` 对应于输入分配 `(1, 1, 1)` ，并且最小有效位对应于 `0` 输入分配 `(0, 0, 0)` 。</span><span class="sxs-lookup"><span data-stu-id="d4ee8-109">For example, the majority function on three inputs is represented by the bitstring `11101000`, where the most significant bit `1` corresponds to the input assignment `(1, 1, 1)`, and the least significant bit `0` corresponds to the input assignment `(0, 0, 0)`.</span></span>
<span data-ttu-id="d4ee8-110">它可以用十六进制表示法中的大整数表示， `0xE8L` 或以 `232L` 十进制表示法表示。</span><span class="sxs-lookup"><span data-stu-id="d4ee8-110">It can be represented by the big integer `0xE8L` in hexadecimal notation or as `232L` in decimal notation.</span></span>  <span data-ttu-id="d4ee8-111">`L`后缀指示常数的类型为 `BigInt` 。</span><span class="sxs-lookup"><span data-stu-id="d4ee8-111">The `L` suffix indicates that the constant is of type `BigInt`.</span></span>
<span data-ttu-id="d4ee8-112">有关此表示形式的更多详细信息，请参阅 [kata 表](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables)。</span><span class="sxs-lookup"><span data-stu-id="d4ee8-112">More details on this representation can also be found in the [truth tables kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables).</span></span>

<span data-ttu-id="d4ee8-113">实现利用 @"microsoft.quantum.intrinsic.cnot" 和 @"microsoft.quantum.intrinsic.r1" 入口。</span><span class="sxs-lookup"><span data-stu-id="d4ee8-113">The implementation makes use of @"microsoft.quantum.intrinsic.cnot" and @"microsoft.quantum.intrinsic.r1" gates.</span></span>

## <a name="input"></a><span data-ttu-id="d4ee8-114">输入</span><span class="sxs-lookup"><span data-stu-id="d4ee8-114">Input</span></span>

### <a name="func--bigint"></a><span data-ttu-id="d4ee8-115">func： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d4ee8-115">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d4ee8-116">表示为大整数的布尔事实数据表</span><span class="sxs-lookup"><span data-stu-id="d4ee8-116">Boolean truth table represented as big integer</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="d4ee8-117">controlRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d4ee8-117">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d4ee8-118">注册控制 qubits</span><span class="sxs-lookup"><span data-stu-id="d4ee8-118">Register of control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="d4ee8-119">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d4ee8-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d4ee8-120">目标 qubit</span><span class="sxs-lookup"><span data-stu-id="d4ee8-120">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="d4ee8-121">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d4ee8-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="d4ee8-122">参考</span><span class="sxs-lookup"><span data-stu-id="d4ee8-122">References</span></span>

- [<span data-ttu-id="d4ee8-123">*Schuch*， *Siewert*，PRL 91，no，027902，2003，arXiv： quant-ph/0303063</span><span class="sxs-lookup"><span data-stu-id="d4ee8-123">*N. Schuch*, *J. Siewert*, PRL 91, no. 027902, 2003, arXiv:quant-ph/0303063</span></span>](https://arxiv.org/abs/quant-ph/0303063)
- [<span data-ttu-id="d4ee8-124">*Mathias Soeken*， *圣马丁 Roetteler*，arXiv：2005.12310</span><span class="sxs-lookup"><span data-stu-id="d4ee8-124">*Mathias Soeken*, *Martin Roetteler*, arXiv:2005.12310</span></span>](https://arxiv.org/abs/2005.12310)

## <a name="see-also"></a><span data-ttu-id="d4ee8-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4ee8-125">See Also</span></span>

- [<span data-ttu-id="d4ee8-126">ApplyXControlledOnTruthTableWithCleanTarget。</span><span class="sxs-lookup"><span data-stu-id="d4ee8-126">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget)