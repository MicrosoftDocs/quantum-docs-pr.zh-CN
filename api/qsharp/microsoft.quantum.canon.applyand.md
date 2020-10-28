---
uid: Microsoft.Quantum.Canon.ApplyAnd
title: 现在操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.
ms.openlocfilehash: 5a4e18cb0361708e1fc00e8d62c0a6c2415d6bed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696387"
---
# <a name="applyand-operation"></a><span data-ttu-id="26032-102">现在操作</span><span class="sxs-lookup"><span data-stu-id="26032-102">ApplyAnd operation</span></span>

<span data-ttu-id="26032-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="26032-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="26032-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="26032-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="26032-105">当且仅当两个控件 qubits 都处于1状态时，使用度量来执行 adjoint 操作，以反转给定的目标 qubit。</span><span class="sxs-lookup"><span data-stu-id="26032-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="26032-106">说明</span><span class="sxs-lookup"><span data-stu-id="26032-106">Description</span></span>

<span data-ttu-id="26032-107">`target`当且仅当这两个控件都为1，但假定 `target` 处于状态0时，则反转。</span><span class="sxs-lookup"><span data-stu-id="26032-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="26032-108">操作具有 T 计数4、T 深度2和不需要 helper qubit，因此，如果已知为0，则可能更适合 CCNOT 操作 `target` 。</span><span class="sxs-lookup"><span data-stu-id="26032-108">The operation has T-count 4, T-depth 2 and requires no helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="26032-109">此操作的 adjoint 是基于度量的，不需要任何 T 入口。</span><span class="sxs-lookup"><span data-stu-id="26032-109">The adjoint of this operation is measurement based and requires no T gates.</span></span>

<span data-ttu-id="26032-110">此操作的受控应用程序不需要 helper qubit、 `2^c` `Rz` 入口和未进行深度优化，其中 `c` 是包括操作中两个控件的总体控制 qubits 的数目 `ApplyAnd` 。</span><span class="sxs-lookup"><span data-stu-id="26032-110">The controlled application of this operation requires no helper qubit, `2^c` `Rz` gates and is not optimized for depth, where `c` is the number of overall control qubits including the two controls from the `ApplyAnd` operation.</span></span>  <span data-ttu-id="26032-111">Adjoint 控制的应用程序要求 `2^c - 1` `Rz` 入口 (两个角度，) 非 adjoint 操作大小的两倍，无帮助器 qubit，不是深度优化。</span><span class="sxs-lookup"><span data-stu-id="26032-111">The adjoint controlled application requires `2^c - 1` `Rz` gates (with an angle twice the size of the non-adjoint operation), no helper qubit and is not optimized for depth.</span></span>

## <a name="input"></a><span data-ttu-id="26032-112">输入</span><span class="sxs-lookup"><span data-stu-id="26032-112">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="26032-113">control1： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="26032-113">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="26032-114">第一个控件 qubit</span><span class="sxs-lookup"><span data-stu-id="26032-114">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="26032-115">control2： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="26032-115">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="26032-116">第二个控件 qubit</span><span class="sxs-lookup"><span data-stu-id="26032-116">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="26032-117">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="26032-117">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="26032-118">目标辅助 qubit;必须处于状态0</span><span class="sxs-lookup"><span data-stu-id="26032-118">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="26032-119">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="26032-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="26032-120">参考</span><span class="sxs-lookup"><span data-stu-id="26032-120">References</span></span>

- <span data-ttu-id="26032-121">Cody： "容错 Toffoli 入口的 Novel 构造"，Phys. A 87，022328，2013 [arXiv： 1212.5069](https://arxiv.org/abs/1212.5069) doi>10.1145： 10.1103/PhysRevA 87.022328</span><span class="sxs-lookup"><span data-stu-id="26032-121">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="26032-122">Craig Gidney： "一半的量程增加成本"，量子2，page 74，2018 [arXiv： 1709.06648](https://arxiv.org/abs/1709.06648) doi>10.1145： 10.1103/PhysRevA. 85.044302</span><span class="sxs-lookup"><span data-stu-id="26032-122">Craig Gidney: "Halving the cost of quantum addition", Quantum 2, page 74, 2018 [arXiv:1709.06648](https://arxiv.org/abs/1709.06648) doi:10.1103/PhysRevA.85.044302</span></span>
- <span data-ttu-id="26032-123">Mathias Soeken： "量子 Oracle 线路和圣诞节树模式"， [博客文章2019年12月19日](https://msoeken.github.io/blog_qac.html) (注意：说明了多受控构造) </span><span class="sxs-lookup"><span data-stu-id="26032-123">Mathias Soeken: "Quantum Oracle Circuits and the Christmas Tree Pattern", [Blog article from December 19, 2019](https://msoeken.github.io/blog_qac.html) (note: explains the multiple controlled construction)</span></span>