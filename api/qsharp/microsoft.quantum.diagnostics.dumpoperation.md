---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: DumpOperation 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: 444d42e2440b30b3bdf50d55a399568bed063222
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695581"
---
# <a name="dumpoperation-operation"></a><span data-ttu-id="605a4-102">DumpOperation 操作</span><span class="sxs-lookup"><span data-stu-id="605a4-102">DumpOperation operation</span></span>

<span data-ttu-id="605a4-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="605a4-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="605a4-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="605a4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="605a4-105">在给定操作的情况下，显示有关当前执行目标可用的操作的诊断。</span><span class="sxs-lookup"><span data-stu-id="605a4-105">Given an operation, displays diagnostics about the operation that are made available by the current execution target.</span></span>

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="605a4-106">输入</span><span class="sxs-lookup"><span data-stu-id="605a4-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="605a4-107">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="605a4-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="605a4-108">给定操作对其起作用的 qubits 的数目。</span><span class="sxs-lookup"><span data-stu-id="605a4-108">The number of qubits on which the given operation acts.</span></span>


### <a name="op--qubit--unit-adj"></a><span data-ttu-id="605a4-109">op： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="605a4-109">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="605a4-110">要诊断的操作。</span><span class="sxs-lookup"><span data-stu-id="605a4-110">The operation that is to be diagnosed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="605a4-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="605a4-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="605a4-112">注解</span><span class="sxs-lookup"><span data-stu-id="605a4-112">Remarks</span></span>

<span data-ttu-id="605a4-113">调用此操作在 Q # 内没有明显的效果。</span><span class="sxs-lookup"><span data-stu-id="605a4-113">Calling this operation has no observable effect from within Q#.</span></span> <span data-ttu-id="605a4-114">显示的确切诊断（如果有）依赖于当前的执行目标和编辑器环境。</span><span class="sxs-lookup"><span data-stu-id="605a4-114">The exact diagnostics that are displayed, if any, are dependent on the current execution target and editor environment.</span></span>
<span data-ttu-id="605a4-115">例如，在全状态量程模拟器上使用时，会显示一个用于表示的单一矩阵 `op` 。</span><span class="sxs-lookup"><span data-stu-id="605a4-115">For example, when used on the full-state quantum simulator, a unitary matrix used to represent `op` is displayed.</span></span>

<span data-ttu-id="605a4-116">请注意，当在可接受全局阶段歧义的模拟器上运行时 (例如：全状态模拟器) ，返回的表示形式可能会因全局阶段而异。</span><span class="sxs-lookup"><span data-stu-id="605a4-116">Note that, when run on simulators that admit a global phase ambiguity (e.g.: the full-state simulator), returned representations may vary up to a global phase.</span></span>

<span data-ttu-id="605a4-117">同样，根据支持此操作的每个模拟器使用的约定，行和列的排序顺序也可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="605a4-117">Similarly, the ordering of rows and columns matrix representations may vary with the conventions used by each simulator supporting this operation.</span></span>