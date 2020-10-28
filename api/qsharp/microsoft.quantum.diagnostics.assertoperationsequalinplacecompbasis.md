---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlaceCompBasis
title: AssertOperationsEqualInPlaceCompBasis 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlaceCompBasis
qsharp.summary: Checks if the operation `givenU` is equal to the operation `expectedU` on the given input size  by checking the action of the operations only on the vectors from the computational basis. This is a necessary, but not sufficient, condition for the equality of two unitaries.
ms.openlocfilehash: 3275680f86ca2a178c7f044b97d226fe41c3186c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695596"
---
# <a name="assertoperationsequalinplacecompbasis-operation"></a><span data-ttu-id="d0e04-102">AssertOperationsEqualInPlaceCompBasis 操作</span><span class="sxs-lookup"><span data-stu-id="d0e04-102">AssertOperationsEqualInPlaceCompBasis operation</span></span>

<span data-ttu-id="d0e04-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="d0e04-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="d0e04-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d0e04-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d0e04-105">`givenU` `expectedU` 通过从计算基础上检查矢量上操作的操作，检查操作是否等于给定输入大小的操作。</span><span class="sxs-lookup"><span data-stu-id="d0e04-105">Checks if the operation `givenU` is equal to the operation `expectedU` on the given input size  by checking the action of the operations only on the vectors from the computational basis.</span></span>
<span data-ttu-id="d0e04-106">这对于两个 unitaries 的相等性是必需的，但并不足够。</span><span class="sxs-lookup"><span data-stu-id="d0e04-106">This is a necessary, but not sufficient, condition for the equality of two unitaries.</span></span>

```qsharp
operation AssertOperationsEqualInPlaceCompBasis (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="d0e04-107">输入</span><span class="sxs-lookup"><span data-stu-id="d0e04-107">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="d0e04-108">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d0e04-108">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d0e04-109">操作和操作 $n $ 的 qubits 的数目 `givenU` `expectedU` 。</span><span class="sxs-lookup"><span data-stu-id="d0e04-109">The number of qubits $n$ that the operations `givenU` and `expectedU` operate on.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="d0e04-110">givenU： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d0e04-110">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d0e04-111">要检查 $n $ qubits 上的操作。</span><span class="sxs-lookup"><span data-stu-id="d0e04-111">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit-adj"></a><span data-ttu-id="d0e04-112">expectedU： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="d0e04-112">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="d0e04-113">要与进行比较 $n $ qubits 上的引用操作 `givenU` 。</span><span class="sxs-lookup"><span data-stu-id="d0e04-113">Reference operation on $n$ qubits that `givenU` is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d0e04-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d0e04-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

