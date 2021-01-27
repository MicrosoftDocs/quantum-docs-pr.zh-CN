---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: _assertEqualOnBasisVector 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: 041fecfa27ae5bd17fa8fdc89ce964f985f6124b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853587"
---
# <a name="_assertequalonbasisvector-operation"></a><span data-ttu-id="303bc-102">_assertEqualOnBasisVector 操作</span><span class="sxs-lookup"><span data-stu-id="303bc-102">_assertEqualOnBasisVector operation</span></span>

<span data-ttu-id="303bc-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="303bc-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="303bc-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="303bc-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="303bc-105">检查应用两个操作的结果 `givenU` 和 `expectedU` 基础状态是否相同。</span><span class="sxs-lookup"><span data-stu-id="303bc-105">Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same.</span></span> <span data-ttu-id="303bc-106">基础状态由 `basis` 参数描述。</span><span class="sxs-lookup"><span data-stu-id="303bc-106">The basis state is described by `basis` parameter.</span></span>
<span data-ttu-id="303bc-107"><xref:microsoft.quantum.extensions.fliptobasis>有关此说明的详细信息，请参阅函数。</span><span class="sxs-lookup"><span data-stu-id="303bc-107">See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.</span></span>

```qsharp
operation _assertEqualOnBasisVector (basis : Int[], givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="303bc-108">输入</span><span class="sxs-lookup"><span data-stu-id="303bc-108">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="303bc-109">basis： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="303bc-109">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="303bc-110">Qubit 基础状态 ID 指定的基础状态 (0 <= id <= 3) 对于 $n $ qubits 中的每个。</span><span class="sxs-lookup"><span data-stu-id="303bc-110">Basis state specified by a single-qubit basis state ID (0 <= id <= 3) for each of $n$ qubits.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="303bc-111">givenU： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="303bc-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="303bc-112">要检查 $n $ qubits 上的操作。</span><span class="sxs-lookup"><span data-stu-id="303bc-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit--is-adj"></a><span data-ttu-id="303bc-113">expectedU： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="303bc-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="303bc-114">对 givenU 进行比较 $n $ qubits 上的引用操作。</span><span class="sxs-lookup"><span data-stu-id="303bc-114">Reference operation on $n$ qubits that givenU is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="303bc-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="303bc-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

