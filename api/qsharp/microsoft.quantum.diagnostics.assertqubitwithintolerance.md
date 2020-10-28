---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: AssertQubitWithinTolerance 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 3fe4aa739c5e15199401aecb76ef551e52f6dcff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695584"
---
# <a name="assertqubitwithintolerance-operation"></a><span data-ttu-id="fce12-102">AssertQubitWithinTolerance 操作</span><span class="sxs-lookup"><span data-stu-id="fce12-102">AssertQubitWithinTolerance operation</span></span>

<span data-ttu-id="fce12-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="fce12-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="fce12-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fce12-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fce12-105">断言 qubit `q` 位于 Pauli Z 运算符的预期 eigenstate 中，直到达到给定的容差。</span><span class="sxs-lookup"><span data-stu-id="fce12-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.</span></span>

```qsharp
operation AssertQubitWithinTolerance (expected : Result, q : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="fce12-106">输入</span><span class="sxs-lookup"><span data-stu-id="fce12-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="fce12-107">应为 __： <Result> 无效__</span><span class="sxs-lookup"><span data-stu-id="fce12-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="fce12-108">Qubit 应采用的状态： `Zero` 或 `One` 。</span><span class="sxs-lookup"><span data-stu-id="fce12-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="fce12-109">问： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fce12-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fce12-110">其状态为 "已断言" 的 qubit。</span><span class="sxs-lookup"><span data-stu-id="fce12-110">The qubit whose state is asserted.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="fce12-111">容差： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fce12-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fce12-112">对 qubit 测量返回预期结果的概率的公差。</span><span class="sxs-lookup"><span data-stu-id="fce12-112">Tolerance on the probability of a measurement of the qubit returning the expected result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fce12-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fce12-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="fce12-114">注解</span><span class="sxs-lookup"><span data-stu-id="fce12-114">Remarks</span></span>

<span data-ttu-id="fce12-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> 允许对任意 qubit 的状态进行断言，而不只是 $Z $ eigenstates。</span><span class="sxs-lookup"><span data-stu-id="fce12-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="fce12-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fce12-116">See Also</span></span>

- [<span data-ttu-id="fce12-117">AssertQubitIsInStateWithinTolerance。</span><span class="sxs-lookup"><span data-stu-id="fce12-117">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)