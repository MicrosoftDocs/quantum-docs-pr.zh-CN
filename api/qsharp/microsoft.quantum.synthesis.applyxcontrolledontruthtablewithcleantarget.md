---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget
title: ApplyXControlledOnTruthTableWithCleanTarget 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTableWithCleanTarget
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: b43a5351985339bcf7c1f2bbe03ae6dc6dfdd165
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701069"
---
# <a name="applyxcontrolledontruthtablewithcleantarget-operation"></a><span data-ttu-id="55dea-102">ApplyXControlledOnTruthTableWithCleanTarget 操作</span><span class="sxs-lookup"><span data-stu-id="55dea-102">ApplyXControlledOnTruthTableWithCleanTarget operation</span></span>

<span data-ttu-id="55dea-103">命名空间 [：](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="55dea-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="55dea-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="55dea-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="55dea-105">@"microsoft.quantum.intrinsic.x" `target` 如果布尔函数的 `func` 计算结果为 true （对于中的传统分配），则应用操作 `controlRegister` 。</span><span class="sxs-lookup"><span data-stu-id="55dea-105">Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.</span></span>

```qsharp
operation ApplyXControlledOnTruthTableWithCleanTarget (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="55dea-106">说明</span><span class="sxs-lookup"><span data-stu-id="55dea-106">Description</span></span>

<span data-ttu-id="55dea-107">此操作实现了一种特殊情况 @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" ，在这种情况下，已知目标 qubit 为 $ \ket {0} $ 状态。</span><span class="sxs-lookup"><span data-stu-id="55dea-107">This operation implements a special case of @"microsoft.quantum.synthesis.applyxcontrolledontruthtable", in which the target qubit is known to be in the $\ket{0}$ state.</span></span>

<span data-ttu-id="55dea-108">实现利用 @"microsoft.quantum.intrinsic.cnot" 和 @"microsoft.quantum.intrinsic.r1" 入口。</span><span class="sxs-lookup"><span data-stu-id="55dea-108">The implementation makes use of @"microsoft.quantum.intrinsic.cnot" and @"microsoft.quantum.intrinsic.r1" gates.</span></span>  <span data-ttu-id="55dea-109">Adjoint 操作的实现经过了优化，并使用了基于度量值的 uncomputation。</span><span class="sxs-lookup"><span data-stu-id="55dea-109">The implementation of the adjoint operation is optimized and uses measurement-based uncomputation.</span></span>

## <a name="input"></a><span data-ttu-id="55dea-110">输入</span><span class="sxs-lookup"><span data-stu-id="55dea-110">Input</span></span>

### <a name="func--bigint"></a><span data-ttu-id="55dea-111">func： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="55dea-111">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="55dea-112">表示为大整数的布尔事实数据表</span><span class="sxs-lookup"><span data-stu-id="55dea-112">Boolean truth table represented as big integer</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="55dea-113">controlRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="55dea-113">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="55dea-114">注册控制 qubits</span><span class="sxs-lookup"><span data-stu-id="55dea-114">Register of control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="55dea-115">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="55dea-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="55dea-116">目标 qubit (必须处于 $ \ket {0} $ 状态) </span><span class="sxs-lookup"><span data-stu-id="55dea-116">Target qubit (must be in $\ket{0}$ state)</span></span>



## <a name="output--unit"></a><span data-ttu-id="55dea-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="55dea-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="55dea-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55dea-118">See Also</span></span>

- [<span data-ttu-id="55dea-119">ApplyXControlledOnTruthTable。</span><span class="sxs-lookup"><span data-stu-id="55dea-119">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable)