---
uid: Microsoft.Quantum.Canon.ApplyCCNOTChain
title: ApplyCCNOTChain 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCCNOTChain
qsharp.summary: Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers. Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.
ms.openlocfilehash: e4f38e9bb54839076b817f6e61e96ca6a550576b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696375"
---
# <a name="applyccnotchain-operation"></a><span data-ttu-id="03c43-102">ApplyCCNOTChain 操作</span><span class="sxs-lookup"><span data-stu-id="03c43-102">ApplyCCNOTChain operation</span></span>

<span data-ttu-id="03c43-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="03c43-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="03c43-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="03c43-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="03c43-105">实现控制在两个 qubit 寄存器的相应位上控制的 CCNOT 入口的层叠，这是在其中一个寄存器的下一个 qubit 上进行的。</span><span class="sxs-lookup"><span data-stu-id="03c43-105">Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers.</span></span>
<span data-ttu-id="03c43-106">从两个寄存器中的位置0开始，将 CCNOT 应用于目标寄存器的位置1处的 qubit，然后由 qubits 在目标寄存器中的位置2进行控制，在目标 qubits 的位置2处进行控制，以目标 qubit 上的操作结束 `Length(nQubits)-1` 。</span><span class="sxs-lookup"><span data-stu-id="03c43-106">Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.</span></span>

```qsharp
operation ApplyCCNOTChain (register : Qubit[], targets : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="03c43-107">输入</span><span class="sxs-lookup"><span data-stu-id="03c43-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="03c43-108">register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="03c43-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="03c43-109">Qubit register，仅用于控件。</span><span class="sxs-lookup"><span data-stu-id="03c43-109">Qubit register, only used for controls.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="03c43-110">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="03c43-110">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="03c43-111">Qubit register，用于控件和作为目标。</span><span class="sxs-lookup"><span data-stu-id="03c43-111">Qubit register, used for controls and as target.</span></span>



## <a name="output--unit"></a><span data-ttu-id="03c43-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="03c43-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="03c43-113">注解</span><span class="sxs-lookup"><span data-stu-id="03c43-113">Remarks</span></span>

<span data-ttu-id="03c43-114">目标 qubit 注册必须有一个以上的 qubit。</span><span class="sxs-lookup"><span data-stu-id="03c43-114">The target qubit register must have one qubit more than the other register.</span></span>