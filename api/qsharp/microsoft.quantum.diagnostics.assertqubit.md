---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: AssertQubit 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: fa1f52da5a011cd914a0fda69b78cf5a4fd71e16
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695593"
---
# <a name="assertqubit-operation"></a><span data-ttu-id="e00d8-102">AssertQubit 操作</span><span class="sxs-lookup"><span data-stu-id="e00d8-102">AssertQubit operation</span></span>

<span data-ttu-id="e00d8-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e00d8-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e00d8-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e00d8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e00d8-105">断言 qubit `q` 位于 Pauli Z 运算符所需的 eigenstate 中。</span><span class="sxs-lookup"><span data-stu-id="e00d8-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.</span></span>

```qsharp
operation AssertQubit (expected : Result, q : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="e00d8-106">输入</span><span class="sxs-lookup"><span data-stu-id="e00d8-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="e00d8-107">应为 __： <Result> 无效__</span><span class="sxs-lookup"><span data-stu-id="e00d8-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="e00d8-108">Qubit 应采用的状态： `Zero` 或 `One` 。</span><span class="sxs-lookup"><span data-stu-id="e00d8-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="e00d8-109">问： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e00d8-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e00d8-110">其状态为 "已断言" 的 qubit。</span><span class="sxs-lookup"><span data-stu-id="e00d8-110">The qubit whose state is asserted.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e00d8-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e00d8-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e00d8-112">注解</span><span class="sxs-lookup"><span data-stu-id="e00d8-112">Remarks</span></span>

<span data-ttu-id="e00d8-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> 允许对任意 qubit 的状态进行断言，而不只是 $Z $ eigenstates。</span><span class="sxs-lookup"><span data-stu-id="e00d8-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="e00d8-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e00d8-114">See Also</span></span>

- [<span data-ttu-id="e00d8-115">AssertQubitIsInStateWithinTolerance。</span><span class="sxs-lookup"><span data-stu-id="e00d8-115">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)