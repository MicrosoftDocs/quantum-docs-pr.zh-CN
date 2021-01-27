---
uid: Microsoft.Quantum.Canon.ApplyLowDepthAnd
title: ApplyLowDepthAnd 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyLowDepthAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.
ms.openlocfilehash: 7fa9d9bf2f1905bf1b59e783d7bceb8cb2e09fa4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841711"
---
# <a name="applylowdepthand-operation"></a><span data-ttu-id="455bf-102">ApplyLowDepthAnd 操作</span><span class="sxs-lookup"><span data-stu-id="455bf-102">ApplyLowDepthAnd operation</span></span>

<span data-ttu-id="455bf-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="455bf-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="455bf-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="455bf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="455bf-105">当且仅当两个 control qubits 都处于1状态时，使用 qubit 执行 adjoint 操作时，使用度量来反转给定目标。</span><span class="sxs-lookup"><span data-stu-id="455bf-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyLowDepthAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="455bf-106">说明</span><span class="sxs-lookup"><span data-stu-id="455bf-106">Description</span></span>

<span data-ttu-id="455bf-107">`target`当且仅当这两个控件都为1，但假定 `target` 处于状态0时，则反转。</span><span class="sxs-lookup"><span data-stu-id="455bf-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="455bf-108">操作具有 T 计数4、T 深度1和需要一个 helper qubit，因此，如果已知为0，则可能更适合 CCNOT 操作 `target` 。</span><span class="sxs-lookup"><span data-stu-id="455bf-108">The operation has T-count 4, T-depth 1 and requires one helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="455bf-109">此操作的 adjoint 是基于度量的，不需要任何 T 入口，也不需要 helper qubit。</span><span class="sxs-lookup"><span data-stu-id="455bf-109">The adjoint of this operation is measurement based and requires no T gates, and no helper qubit.</span></span>

## <a name="input"></a><span data-ttu-id="455bf-110">输入</span><span class="sxs-lookup"><span data-stu-id="455bf-110">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="455bf-111">control1： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="455bf-111">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="455bf-112">第一个控件 qubit</span><span class="sxs-lookup"><span data-stu-id="455bf-112">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="455bf-113">control2： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="455bf-113">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="455bf-114">第二个控件 qubit</span><span class="sxs-lookup"><span data-stu-id="455bf-114">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="455bf-115">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="455bf-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="455bf-116">目标辅助 qubit;必须处于状态0</span><span class="sxs-lookup"><span data-stu-id="455bf-116">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="455bf-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="455bf-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="455bf-118">参考</span><span class="sxs-lookup"><span data-stu-id="455bf-118">References</span></span>

- <span data-ttu-id="455bf-119">Cody： "容错 Toffoli 入口的 Novel 构造"，Phys. A 87，022328，2013 [arXiv： 1212.5069](https://arxiv.org/abs/1212.5069) doi>10.1145： 10.1103/PhysRevA 87.022328</span><span class="sxs-lookup"><span data-stu-id="455bf-119">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="455bf-120">Peter Selinger： "T 深一条的量子线路"，Phys，87，042302，2013 [arXiv： 1210.0974](https://arxiv.org/abs/1210.0974) doi>10.1145： 10.1103/PhysRevA 87.042302</span><span class="sxs-lookup"><span data-stu-id="455bf-120">Peter Selinger: "Quantum circuits of T-depth one", Phys. Rev. A 87, 042302, 2013 [arXiv:1210.0974](https://arxiv.org/abs/1210.0974) doi:10.1103/PhysRevA.87.042302</span></span>