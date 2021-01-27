---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: ApplyMultiControlledCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: a6549084b1c2fda885823f451d17f9c2ebbb4600
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841683"
---
# <a name="applymulticontrolledca-operation"></a><span data-ttu-id="9d307-102">ApplyMultiControlledCA 操作</span><span class="sxs-lookup"><span data-stu-id="9d307-102">ApplyMultiControlledCA operation</span></span>

<span data-ttu-id="9d307-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9d307-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9d307-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9d307-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9d307-105">应用单个受控操作的多重控制版本。</span><span class="sxs-lookup"><span data-stu-id="9d307-105">Applies a multiply controlled version of a singly controlled operation.</span></span>
<span data-ttu-id="9d307-106">修饰符 `CA` 指示 qubit 操作可控制和 adjointable。</span><span class="sxs-lookup"><span data-stu-id="9d307-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9d307-107">输入</span><span class="sxs-lookup"><span data-stu-id="9d307-107">Input</span></span>

### <a name="singlycontrolledop--qubit--unit--is-adj"></a><span data-ttu-id="9d307-108">singlyControlledOp： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="9d307-108">singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="9d307-109">对单个 qubit 控制的操作。</span><span class="sxs-lookup"><span data-stu-id="9d307-109">An operation controlled on a single qubit.</span></span>
<span data-ttu-id="9d307-110">操作的参数中的第一个 qubit 假定为控件，而其余的则假定为目标 qubits。</span><span class="sxs-lookup"><span data-stu-id="9d307-110">The first qubit in the argument of the operation assumed to be a control and the rest are assumed to be target qubits.</span></span>
<span data-ttu-id="9d307-111">`ApplyMultiControlled` 始终 `singlyControlledOp` 使用长度至少为1的参数调用。</span><span class="sxs-lookup"><span data-stu-id="9d307-111">`ApplyMultiControlled` always calls `singlyControlledOp` with an argument of length at least 1.</span></span>


### <a name="ccnot--ccnotop"></a><span data-ttu-id="9d307-112">ccnot： [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="9d307-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="9d307-113">用于构造的受控控制的非入口。</span><span class="sxs-lookup"><span data-stu-id="9d307-113">The controlled-controlled-NOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="9d307-114">控件： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9d307-114">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9d307-115">要对其进行控制的 qubits `singlyControlledOp` 。</span><span class="sxs-lookup"><span data-stu-id="9d307-115">The qubits that `singlyControlledOp` is to be controlled on.</span></span>
<span data-ttu-id="9d307-116">的长度 `controls` 必须至少为1。</span><span class="sxs-lookup"><span data-stu-id="9d307-116">The length of `controls` must be at least 1.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="9d307-117">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9d307-117">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9d307-118">作用于的目标 qubits `singlyControlledOp` 。</span><span class="sxs-lookup"><span data-stu-id="9d307-118">The target qubits that `singlyControlledOp` acts upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9d307-119">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9d307-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9d307-120">备注</span><span class="sxs-lookup"><span data-stu-id="9d307-120">Remarks</span></span>

<span data-ttu-id="9d307-121">此操作仅使用 clean ancilla qubits。</span><span class="sxs-lookup"><span data-stu-id="9d307-121">This operation uses only clean ancilla qubits.</span></span>

<span data-ttu-id="9d307-122">有关说明和线路关系图，请参阅图4.10，& Nielsen 中的第4.3 节语</span><span class="sxs-lookup"><span data-stu-id="9d307-122">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang</span></span>

## <a name="references"></a><span data-ttu-id="9d307-123">参考</span><span class="sxs-lookup"><span data-stu-id="9d307-123">References</span></span>

- [<span data-ttu-id="9d307-124">*Michael Nielsen、Isaac 语*、量程计算和量程信息</span><span class="sxs-lookup"><span data-stu-id="9d307-124"> *Michael A. Nielsen , Isaac L. Chuang*, Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a><span data-ttu-id="9d307-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d307-125">See Also</span></span>

- [<span data-ttu-id="9d307-126">Canon. ApplyMultiControlledC</span><span class="sxs-lookup"><span data-stu-id="9d307-126">Microsoft.Quantum.Canon.ApplyMultiControlledC</span></span>](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)