---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace
title: AssertOperationsEqualInPlace 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).

  This assertion uses $n$ qubits and requires multiple calls of the operations being compared.
ms.openlocfilehash: 407a139da816281346eb06849f81e91b83202653
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695597"
---
# <a name="assertoperationsequalinplace-operation"></a><span data-ttu-id="fc2bd-102">AssertOperationsEqualInPlace 操作</span><span class="sxs-lookup"><span data-stu-id="fc2bd-102">AssertOperationsEqualInPlace operation</span></span>

<span data-ttu-id="fc2bd-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="fc2bd-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="fc2bd-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fc2bd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fc2bd-105">假设有两个运算，则断言它们对于所有输入状态都是相同的。</span><span class="sxs-lookup"><span data-stu-id="fc2bd-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="fc2bd-106">此断言是通过以下方式实现的：检查所有状态的操作的操作： $V _0 \otimes ... \otimes V_ {n-1} $，其中 $V _k $ 是状态 $ \ket {0} $，$ \ket $ {1} ，$ \ket{+} $，$ \ket{i} $ (+ 1 Eigenstate Of Pauli Y operator) 。</span><span class="sxs-lookup"><span data-stu-id="fc2bd-106">This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).</span></span>

<span data-ttu-id="fc2bd-107">此断言使用 $n $ qubits，需要对要比较的操作进行多次调用。</span><span class="sxs-lookup"><span data-stu-id="fc2bd-107">This assertion uses $n$ qubits and requires multiple calls of the operations being compared.</span></span>

```qsharp
operation AssertOperationsEqualInPlace (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="fc2bd-108">输入</span><span class="sxs-lookup"><span data-stu-id="fc2bd-108">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="fc2bd-109">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fc2bd-109">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fc2bd-110">操作和操作 $n $ 的 qubits 的数目 `givenU` `expectedU` 。</span><span class="sxs-lookup"><span data-stu-id="fc2bd-110">The number of qubits $n$ that the operations `givenU` and `expectedU` operate on.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="fc2bd-111">givenU： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fc2bd-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="fc2bd-112">要检查 $n $ qubits 上的操作。</span><span class="sxs-lookup"><span data-stu-id="fc2bd-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit-adj"></a><span data-ttu-id="fc2bd-113">expectedU： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="fc2bd-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="fc2bd-114">要与进行比较 $n $ qubits 上的引用操作 `givenU` 。</span><span class="sxs-lookup"><span data-stu-id="fc2bd-114">Reference operation on $n$ qubits that `givenU` is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fc2bd-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fc2bd-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="fc2bd-116">参考</span><span class="sxs-lookup"><span data-stu-id="fc2bd-116">References</span></span>

<span data-ttu-id="fc2bd-117">状态 $ \ket {0} $、$ \ket {1} $、$ \ket{+} $ 和 $ \ket{i} $ 是 Chuang-Nielsen 的基础，如中所述 [ *I. L. Chuang, M. A. Nielsen*](https://arxiv.org/abs/quant-ph/9610001)。</span><span class="sxs-lookup"><span data-stu-id="fc2bd-117">The basis of states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ is the Chuang-Nielsen basis, described in [ *I. L. Chuang, M. A. Nielsen* ](https://arxiv.org/abs/quant-ph/9610001).</span></span>

## <a name="see-also"></a><span data-ttu-id="fc2bd-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc2bd-118">See Also</span></span>

- [<span data-ttu-id="fc2bd-119">AssertOperationsEqualReferenced。</span><span class="sxs-lookup"><span data-stu-id="fc2bd-119">Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced)