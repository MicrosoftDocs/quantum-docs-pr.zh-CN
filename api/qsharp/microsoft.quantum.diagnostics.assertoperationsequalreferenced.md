---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced
title: AssertOperationsEqualReferenced 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers. Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated. This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.
ms.openlocfilehash: 045f00a720e9f4d2e6993c66ace44a81e192ff30
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853466"
---
# <a name="assertoperationsequalreferenced-operation"></a><span data-ttu-id="f3692-102">AssertOperationsEqualReferenced 操作</span><span class="sxs-lookup"><span data-stu-id="f3692-102">AssertOperationsEqualReferenced operation</span></span>

<span data-ttu-id="f3692-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="f3692-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="f3692-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f3692-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="f3692-105">假设有两个运算，则断言它们对于所有输入状态都是相同的。</span><span class="sxs-lookup"><span data-stu-id="f3692-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="f3692-106">通过使用 Choi – Jamiołkowski isomorphism 将断言降低到两个放大寄存器上的某个 qubit 状态断言，实现此断言。</span><span class="sxs-lookup"><span data-stu-id="f3692-106">This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers.</span></span>
<span data-ttu-id="f3692-107">因此，此操作只需对正在测试的每个操作进行一次调用，而需要分配两个要分配的 qubits。</span><span class="sxs-lookup"><span data-stu-id="f3692-107">Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated.</span></span>
<span data-ttu-id="f3692-108">例如，可以使用这种断言来确保操作的优化版本与其简单的实现完全相同，或者对非量程输入进行操作的操作与已知情况有关。</span><span class="sxs-lookup"><span data-stu-id="f3692-108">This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.</span></span>

```qsharp
operation AssertOperationsEqualReferenced (nQubits : Int, actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="f3692-109">输入</span><span class="sxs-lookup"><span data-stu-id="f3692-109">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="f3692-110">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f3692-110">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f3692-111">要传递给每个操作的 qubits 数。</span><span class="sxs-lookup"><span data-stu-id="f3692-111">Number of qubits to pass to each operation.</span></span>


### <a name="actual--qubit--unit"></a><span data-ttu-id="f3692-112">实际： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f3692-112">actual : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f3692-113">要测试的操作。</span><span class="sxs-lookup"><span data-stu-id="f3692-113">Operation to be tested.</span></span>


### <a name="expected--qubit--unit--is-adj"></a><span data-ttu-id="f3692-114">应为： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="f3692-114">expected : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="f3692-115">定义要测试的操作的预期行为的操作。</span><span class="sxs-lookup"><span data-stu-id="f3692-115">Operation defining the expected behavior for the operation under test.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f3692-116">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f3692-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f3692-117">备注</span><span class="sxs-lookup"><span data-stu-id="f3692-117">Remarks</span></span>

<span data-ttu-id="f3692-118">此操作要求对预期行为进行建模的操作为 adjointable，以便可以在目标寄存器上单独执行相反的操作。</span><span class="sxs-lookup"><span data-stu-id="f3692-118">This operation requires that the operation modeling the expected behavior is adjointable, so that the inverse can be performed on the target register alone.</span></span>
<span data-ttu-id="f3692-119">正式，可以指定换位操作，该操作放宽此要求，但换位操作并不是对任意量程操作以物理 realizable 的形式进行的，因此不作为选项包含在此处。</span><span class="sxs-lookup"><span data-stu-id="f3692-119">Formally, one can specify a transpose operation, which relaxes this requirement, but the transpose operation is not in general physically realizable for arbitrary quantum operations and thus is not included here as an option.</span></span>