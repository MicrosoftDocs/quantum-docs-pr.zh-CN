---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: AssertMeasurementProbability 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: ff0419706d825442492f82e564f1cce86f1b112f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695598"
---
# <a name="assertmeasurementprobability-operation"></a><span data-ttu-id="6edd6-102">AssertMeasurementProbability 操作</span><span class="sxs-lookup"><span data-stu-id="6edd6-102">AssertMeasurementProbability operation</span></span>

<span data-ttu-id="6edd6-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="6edd6-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="6edd6-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6edd6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6edd6-105">在给定 Pauli 基础上测量给定 qubits 的断言在某种程度上具有给定概率的给定结果。</span><span class="sxs-lookup"><span data-stu-id="6edd6-105">Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.</span></span>

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="6edd6-106">输入</span><span class="sxs-lookup"><span data-stu-id="6edd6-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="6edd6-107">基： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="6edd6-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="6edd6-108">用于断言概率的度量效果，表示为多 qubit Pauli 运算符。</span><span class="sxs-lookup"><span data-stu-id="6edd6-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="6edd6-109">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6edd6-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6edd6-110">要对其进行断言的寄存器。</span><span class="sxs-lookup"><span data-stu-id="6edd6-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="6edd6-111">结果： __无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="6edd6-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="6edd6-112">的预期结果 `Measure(bases, qubits)` 。</span><span class="sxs-lookup"><span data-stu-id="6edd6-112">An expected result of `Measure(bases, qubits)`.</span></span>


### <a name="prob--double"></a><span data-ttu-id="6edd6-113">prob： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6edd6-113">prob : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6edd6-114">给定结果预计的概率。</span><span class="sxs-lookup"><span data-stu-id="6edd6-114">The probability with which the given result is expected.</span></span>


### <a name="msg--string"></a><span data-ttu-id="6edd6-115">msg： [String](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="6edd6-115">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="6edd6-116">断言失败时要报告的消息。</span><span class="sxs-lookup"><span data-stu-id="6edd6-116">A message to be reported if the assertion fails.</span></span>


### <a name="tol--double"></a><span data-ttu-id="6edd6-117">tol： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6edd6-117">tol : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--unit"></a><span data-ttu-id="6edd6-118">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6edd6-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6edd6-119">注解</span><span class="sxs-lookup"><span data-stu-id="6edd6-119">Remarks</span></span>

<span data-ttu-id="6edd6-120">请注意，此操作的 Adjoint 和受控版本将不检查该条件。</span><span class="sxs-lookup"><span data-stu-id="6edd6-120">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="6edd6-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6edd6-121">See Also</span></span>

- [<span data-ttu-id="6edd6-122">AssertMeasurement。</span><span class="sxs-lookup"><span data-stu-id="6edd6-122">Microsoft.Quantum.Diagnostics.AssertMeasurement</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)