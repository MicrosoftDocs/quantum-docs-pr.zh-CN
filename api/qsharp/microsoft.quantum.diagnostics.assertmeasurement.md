---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: AssertMeasurement 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 8f5113f1d6b8e4f104af10ca330e244e95793418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853505"
---
# <a name="assertmeasurement-operation"></a><span data-ttu-id="2ccf7-102">AssertMeasurement 操作</span><span class="sxs-lookup"><span data-stu-id="2ccf7-102">AssertMeasurement operation</span></span>

<span data-ttu-id="2ccf7-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2ccf7-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2ccf7-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="2ccf7-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="2ccf7-105">度量给定 Pauli 基础中给定 qubits 的断言将始终具有给定的结果。</span><span class="sxs-lookup"><span data-stu-id="2ccf7-105">Asserts that measuring the given qubits in the given Pauli basis will always have the given result.</span></span>

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2ccf7-106">输入</span><span class="sxs-lookup"><span data-stu-id="2ccf7-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="2ccf7-107">基： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="2ccf7-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="2ccf7-108">用于断言概率的度量效果，表示为多 qubit Pauli 运算符。</span><span class="sxs-lookup"><span data-stu-id="2ccf7-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="2ccf7-109">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2ccf7-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2ccf7-110">要对其进行断言的寄存器。</span><span class="sxs-lookup"><span data-stu-id="2ccf7-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="2ccf7-111">结果：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="2ccf7-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="2ccf7-112">的预期结果 `Measure(bases, qubits)` 。</span><span class="sxs-lookup"><span data-stu-id="2ccf7-112">The expected result of `Measure(bases, qubits)`.</span></span>


### <a name="msg--string"></a><span data-ttu-id="2ccf7-113">msg： [String](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="2ccf7-113">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="2ccf7-114">断言失败时要报告的消息。</span><span class="sxs-lookup"><span data-stu-id="2ccf7-114">A message to be reported if the assertion fails.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2ccf7-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2ccf7-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2ccf7-116">备注</span><span class="sxs-lookup"><span data-stu-id="2ccf7-116">Remarks</span></span>

<span data-ttu-id="2ccf7-117">请注意，此操作的 Adjoint 和受控版本将不检查该条件。</span><span class="sxs-lookup"><span data-stu-id="2ccf7-117">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ccf7-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ccf7-118">See Also</span></span>

- [<span data-ttu-id="2ccf7-119">AssertMeasurementProbability。</span><span class="sxs-lookup"><span data-stu-id="2ccf7-119">Microsoft.Quantum.Diagnostics.AssertMeasurementProbability</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)