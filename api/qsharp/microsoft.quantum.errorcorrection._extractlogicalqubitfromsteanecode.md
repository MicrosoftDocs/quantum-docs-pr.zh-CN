---
uid: Microsoft.Quantum.ErrorCorrection._ExtractLogicalQubitFromSteaneCode
title: _ExtractLogicalQubitFromSteaneCode 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: _ExtractLogicalQubitFromSteaneCode
qsharp.summary: >-
  Syndrome measurement and the inverse of embedding.

  $X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit. This asymmetry leads to a different syndrome extraction routine. One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.
ms.openlocfilehash: fe64343e30a0a3f0d05382e7812d37d5b13133d3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853214"
---
# <a name="_extractlogicalqubitfromsteanecode-operation"></a><span data-ttu-id="6f86e-102">_ExtractLogicalQubitFromSteaneCode 操作</span><span class="sxs-lookup"><span data-stu-id="6f86e-102">_ExtractLogicalQubitFromSteaneCode operation</span></span>

<span data-ttu-id="6f86e-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="6f86e-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="6f86e-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6f86e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6f86e-105">与嵌入有关的症状。</span><span class="sxs-lookup"><span data-stu-id="6f86e-105">Syndrome measurement and the inverse of embedding.</span></span>

<span data-ttu-id="6f86e-106">不会平等对待 $X $-和 $Z $-stabilizers，这是因为编码线路的特定选择。</span><span class="sxs-lookup"><span data-stu-id="6f86e-106">$X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit.</span></span>
<span data-ttu-id="6f86e-107">这种不对称会导致不同的症状提取例程。</span><span class="sxs-lookup"><span data-stu-id="6f86e-107">This asymmetry leads to a different syndrome extraction routine.</span></span>
<span data-ttu-id="6f86e-108">可以通过直接在代码状态上测量多 qubit Pauli 运算符来度量症状，但对于升华目的，逻辑 qubit 将返回到单个 qubit 中，而无需进一步 ancillas。</span><span class="sxs-lookup"><span data-stu-id="6f86e-108">One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.</span></span>

```qsharp
operation _ExtractLogicalQubitFromSteaneCode (code : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit, Int, Int)
```


## <a name="input"></a><span data-ttu-id="6f86e-109">输入</span><span class="sxs-lookup"><span data-stu-id="6f86e-109">Input</span></span>

### <a name="code--logicalregister"></a><span data-ttu-id="6f86e-110">代码： [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="6f86e-110">code : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>





## <a name="output--qubitintint"></a><span data-ttu-id="6f86e-111">Output： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)，[int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)) </span><span class="sxs-lookup"><span data-stu-id="6f86e-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

<span data-ttu-id="6f86e-112">逻辑 qubit 和一对整数，用于 $X $-症状和 $Z $-症状。</span><span class="sxs-lookup"><span data-stu-id="6f86e-112">The logical qubit and a pair of integers for $X$-syndrome and $Z$-syndrome.</span></span>
<span data-ttu-id="6f86e-113">它们表示代码 qubit 的索引，其中一次 $X $ 或 $Z $-错误将导致测定的症状。</span><span class="sxs-lookup"><span data-stu-id="6f86e-113">They represent the index of the code qubit on which a single $X$- or $Z$-error would have caused the measured syndrome.</span></span>

## <a name="remarks"></a><span data-ttu-id="6f86e-114">备注</span><span class="sxs-lookup"><span data-stu-id="6f86e-114">Remarks</span></span>

<span data-ttu-id="6f86e-115">请注意，此操作不会标记为 `internal` ，因为单元测试直接依赖于此操作。</span><span class="sxs-lookup"><span data-stu-id="6f86e-115">Note that this operation is not marked as `internal`, as unit tests directly depend on this operation.</span></span> <span data-ttu-id="6f86e-116">作为未来的改进，应重构单元测试，使其仅依赖公共 callables。</span><span class="sxs-lookup"><span data-stu-id="6f86e-116">As a future improvement, unit tests should be refactored to depend only on public callables directly.</span></span>

> [!WARNING]
> <span data-ttu-id="6f86e-117">对于 Steane 的 7 qubit 代码，此例程定制为特定的编码线路;如果修改了编码线路，则可能必须以不同的方式解释症状结果。</span><span class="sxs-lookup"><span data-stu-id="6f86e-117">This routine is tailored to a particular encoding circuit for Steane's 7 qubit code; if the encoding circuit is modified then the syndrome outcome might have to be interpreted differently.</span></span>