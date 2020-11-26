---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: AssertQubitWithinTolerance 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 56b7f93f33ae18146c1fb13d404fc1d119eee72e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202186"
---
# <a name="assertqubitwithintolerance-operation"></a><span data-ttu-id="a3193-102">AssertQubitWithinTolerance 操作</span><span class="sxs-lookup"><span data-stu-id="a3193-102">AssertQubitWithinTolerance operation</span></span>

<span data-ttu-id="a3193-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="a3193-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="a3193-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a3193-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a3193-105">断言 qubit `q` 位于 Pauli Z 运算符的预期 eigenstate 中，直到达到给定的容差。</span><span class="sxs-lookup"><span data-stu-id="a3193-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.</span></span>

```qsharp
operation AssertQubitWithinTolerance (expected : Result, q : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="a3193-106">输入</span><span class="sxs-lookup"><span data-stu-id="a3193-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="a3193-107">应为 __： <Result> 无效__</span><span class="sxs-lookup"><span data-stu-id="a3193-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="a3193-108">Qubit 应采用的状态： `Zero` 或 `One` 。</span><span class="sxs-lookup"><span data-stu-id="a3193-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="a3193-109">问： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a3193-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a3193-110">其状态为 "已断言" 的 qubit。</span><span class="sxs-lookup"><span data-stu-id="a3193-110">The qubit whose state is asserted.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="a3193-111">容差： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a3193-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a3193-112">对 qubit 测量返回预期结果的概率的公差。</span><span class="sxs-lookup"><span data-stu-id="a3193-112">Tolerance on the probability of a measurement of the qubit returning the expected result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a3193-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a3193-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a3193-114">备注</span><span class="sxs-lookup"><span data-stu-id="a3193-114">Remarks</span></span>

<span data-ttu-id="a3193-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> 允许对任意 qubit 的状态进行断言，而不只是 $Z $ eigenstates。</span><span class="sxs-lookup"><span data-stu-id="a3193-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="a3193-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3193-116">See Also</span></span>

- [<span data-ttu-id="a3193-117">AssertQubitIsInStateWithinTolerance。</span><span class="sxs-lookup"><span data-stu-id="a3193-117">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)