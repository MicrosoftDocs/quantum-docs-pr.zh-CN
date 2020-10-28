---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: AssertMeasurement 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 09024cd8cd6e713360dcf7f42f55941590f35883
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695606"
---
# <a name="assertmeasurement-operation"></a><span data-ttu-id="26978-102">AssertMeasurement 操作</span><span class="sxs-lookup"><span data-stu-id="26978-102">AssertMeasurement operation</span></span>

<span data-ttu-id="26978-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="26978-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="26978-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="26978-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="26978-105">度量给定 Pauli 基础中给定 qubits 的断言将始终具有给定的结果。</span><span class="sxs-lookup"><span data-stu-id="26978-105">Asserts that measuring the given qubits in the given Pauli basis will always have the given result.</span></span>

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="26978-106">输入</span><span class="sxs-lookup"><span data-stu-id="26978-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="26978-107">基： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="26978-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="26978-108">用于断言概率的度量效果，表示为多 qubit Pauli 运算符。</span><span class="sxs-lookup"><span data-stu-id="26978-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="26978-109">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="26978-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="26978-110">要对其进行断言的寄存器。</span><span class="sxs-lookup"><span data-stu-id="26978-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="26978-111">结果： __无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="26978-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="26978-112">的预期结果 `Measure(bases, qubits)` 。</span><span class="sxs-lookup"><span data-stu-id="26978-112">The expected result of `Measure(bases, qubits)`.</span></span>


### <a name="msg--string"></a><span data-ttu-id="26978-113">msg： [String](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="26978-113">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="26978-114">断言失败时要报告的消息。</span><span class="sxs-lookup"><span data-stu-id="26978-114">A message to be reported if the assertion fails.</span></span>



## <a name="output--unit"></a><span data-ttu-id="26978-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="26978-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="26978-116">注解</span><span class="sxs-lookup"><span data-stu-id="26978-116">Remarks</span></span>

<span data-ttu-id="26978-117">请注意，此操作的 Adjoint 和受控版本将不检查该条件。</span><span class="sxs-lookup"><span data-stu-id="26978-117">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="26978-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="26978-118">See Also</span></span>

- [<span data-ttu-id="26978-119">AssertMeasurementProbability。</span><span class="sxs-lookup"><span data-stu-id="26978-119">Microsoft.Quantum.Diagnostics.AssertMeasurementProbability</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)