---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: MeasureStabilizerGenerators 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: a3f48ff24a39d13a57f7a144e21d4e41bb8a8b49
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695496"
---
# <a name="measurestabilizergenerators-operation"></a><span data-ttu-id="3ed72-102">MeasureStabilizerGenerators 操作</span><span class="sxs-lookup"><span data-stu-id="3ed72-102">MeasureStabilizerGenerators operation</span></span>

<span data-ttu-id="3ed72-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="3ed72-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="3ed72-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3ed72-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3ed72-105">度量稳定组的给定生成器集。</span><span class="sxs-lookup"><span data-stu-id="3ed72-105">Measures the given set of generators of a stabilizer group.</span></span>

```qsharp
operation MeasureStabilizerGenerators (stabilizerGroup : Pauli[][], logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister, gadget : ((Pauli[], Qubit[]) => Result)) : Microsoft.Quantum.ErrorCorrection.Syndrome
```


## <a name="input"></a><span data-ttu-id="3ed72-106">输入</span><span class="sxs-lookup"><span data-stu-id="3ed72-106">Input</span></span>

### <a name="stabilizergroup--pauli"></a><span data-ttu-id="3ed72-107">stabilizerGroup： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="3ed72-107">stabilizerGroup : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="3ed72-108">Multiqubit Pauli 运算符的数组。</span><span class="sxs-lookup"><span data-stu-id="3ed72-108">An array of multiqubit Pauli operators.</span></span>
<span data-ttu-id="3ed72-109">例如， `stabilizerGroup[0]` 是一个 Qubit Pauli 矩阵列表，其中的 tensor 产品是一个稳定的生成器。</span><span class="sxs-lookup"><span data-stu-id="3ed72-109">For example, `stabilizerGroup[0]` is a list of single-qubit Pauli matrices, the tensor product of which is a stabilizer generator.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="3ed72-110">logicalRegister： [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="3ed72-110">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="3ed72-111">定义了稳定程序代码的 qubits 的数组。</span><span class="sxs-lookup"><span data-stu-id="3ed72-111">An array of qubits where the stabilizer code is defined.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="3ed72-112">小工具： ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]、 [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) => __无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="3ed72-112">gadget : ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="3ed72-113">一个操作，指定如何度量 multiqubit Pauli 运算符。</span><span class="sxs-lookup"><span data-stu-id="3ed72-113">An operation that specifies how to measure a multiqubit Pauli operator.</span></span>



## <a name="output--syndrome"></a><span data-ttu-id="3ed72-114">输出： [症状](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="3ed72-114">Output : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="3ed72-115">度量值的结果。</span><span class="sxs-lookup"><span data-stu-id="3ed72-115">The result of measurements.</span></span>

## <a name="remarks"></a><span data-ttu-id="3ed72-116">注解</span><span class="sxs-lookup"><span data-stu-id="3ed72-116">Remarks</span></span>

<span data-ttu-id="3ed72-117">这不会检查给定的生成器集是否上下班途中。</span><span class="sxs-lookup"><span data-stu-id="3ed72-117">This does not check if the given set of generators are commuting.</span></span>
<span data-ttu-id="3ed72-118">如果没有上下班途中，则测量结果可能是任意的。</span><span class="sxs-lookup"><span data-stu-id="3ed72-118">If they are not commuting, the result of measurements may be arbitrary.</span></span>