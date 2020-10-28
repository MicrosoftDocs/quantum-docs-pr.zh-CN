---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: _assertEqualOnBasisVector 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: 01b6d5aede102e47df86ea70d071d81eba1ade6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695623"
---
# <a name="_assertequalonbasisvector-operation"></a><span data-ttu-id="4052b-102">_assertEqualOnBasisVector 操作</span><span class="sxs-lookup"><span data-stu-id="4052b-102">_assertEqualOnBasisVector operation</span></span>

<span data-ttu-id="4052b-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="4052b-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="4052b-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4052b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4052b-105">检查应用两个操作的结果 `givenU` 和 `expectedU` 基础状态是否相同。</span><span class="sxs-lookup"><span data-stu-id="4052b-105">Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same.</span></span> <span data-ttu-id="4052b-106">基础状态由 `basis` 参数描述。</span><span class="sxs-lookup"><span data-stu-id="4052b-106">The basis state is described by `basis` parameter.</span></span>
<span data-ttu-id="4052b-107"><xref:microsoft.quantum.extensions.fliptobasis>有关此说明的详细信息，请参阅函数。</span><span class="sxs-lookup"><span data-stu-id="4052b-107">See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.</span></span>

```qsharp
operation _assertEqualOnBasisVector (basis : Int[], givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="4052b-108">输入</span><span class="sxs-lookup"><span data-stu-id="4052b-108">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="4052b-109">basis： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="4052b-109">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="4052b-110">Qubit 基础状态 ID 指定的基础状态 (0 <= id <= 3) 对于 $n $ qubits 中的每个。</span><span class="sxs-lookup"><span data-stu-id="4052b-110">Basis state specified by a single-qubit basis state ID (0 <= id <= 3) for each of $n$ qubits.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="4052b-111">givenU： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4052b-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4052b-112">要检查 $n $ qubits 上的操作。</span><span class="sxs-lookup"><span data-stu-id="4052b-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit-adj"></a><span data-ttu-id="4052b-113">expectedU： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="4052b-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="4052b-114">对 givenU 进行比较 $n $ qubits 上的引用操作。</span><span class="sxs-lookup"><span data-stu-id="4052b-114">Reference operation on $n$ qubits that givenU is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4052b-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4052b-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

