---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: MeasureStabilizerGenerators 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: d7c8df079e49b2ce0a5106e430ef4060df85cdc4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825755"
---
# <a name="measurestabilizergenerators-operation"></a><span data-ttu-id="31b50-102">MeasureStabilizerGenerators 操作</span><span class="sxs-lookup"><span data-stu-id="31b50-102">MeasureStabilizerGenerators operation</span></span>

<span data-ttu-id="31b50-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="31b50-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="31b50-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="31b50-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="31b50-105">度量稳定组的给定生成器集。</span><span class="sxs-lookup"><span data-stu-id="31b50-105">Measures the given set of generators of a stabilizer group.</span></span>

```qsharp
operation MeasureStabilizerGenerators (stabilizerGroup : Pauli[][], logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister, gadget : ((Pauli[], Qubit[]) => Result)) : Microsoft.Quantum.ErrorCorrection.Syndrome
```


## <a name="input"></a><span data-ttu-id="31b50-106">输入</span><span class="sxs-lookup"><span data-stu-id="31b50-106">Input</span></span>

### <a name="stabilizergroup--pauli"></a><span data-ttu-id="31b50-107">stabilizerGroup： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="31b50-107">stabilizerGroup : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="31b50-108">Multiqubit Pauli 运算符的数组。</span><span class="sxs-lookup"><span data-stu-id="31b50-108">An array of multiqubit Pauli operators.</span></span>
<span data-ttu-id="31b50-109">例如， `stabilizerGroup[0]` 是一个 Qubit Pauli 矩阵列表，其中的 tensor 产品是一个稳定的生成器。</span><span class="sxs-lookup"><span data-stu-id="31b50-109">For example, `stabilizerGroup[0]` is a list of single-qubit Pauli matrices, the tensor product of which is a stabilizer generator.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="31b50-110">logicalRegister： [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="31b50-110">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="31b50-111">定义了稳定程序代码的 qubits 的数组。</span><span class="sxs-lookup"><span data-stu-id="31b50-111">An array of qubits where the stabilizer code is defined.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="31b50-112">小工具： ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[]、[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) =>__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="31b50-112">gadget : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="31b50-113">一个操作，指定如何度量 multiqubit Pauli 运算符。</span><span class="sxs-lookup"><span data-stu-id="31b50-113">An operation that specifies how to measure a multiqubit Pauli operator.</span></span>



## <a name="output--syndrome"></a><span data-ttu-id="31b50-114">输出： [症状](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="31b50-114">Output : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="31b50-115">度量值的结果。</span><span class="sxs-lookup"><span data-stu-id="31b50-115">The result of measurements.</span></span>

## <a name="remarks"></a><span data-ttu-id="31b50-116">备注</span><span class="sxs-lookup"><span data-stu-id="31b50-116">Remarks</span></span>

<span data-ttu-id="31b50-117">这不会检查给定的生成器集是否上下班途中。</span><span class="sxs-lookup"><span data-stu-id="31b50-117">This does not check if the given set of generators are commuting.</span></span>
<span data-ttu-id="31b50-118">如果没有上下班途中，则测量结果可能是任意的。</span><span class="sxs-lookup"><span data-stu-id="31b50-118">If they are not commuting, the result of measurements may be arbitrary.</span></span>