---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: ApplyMultiControlledCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: 5662efe0dc6f665206b8773596bf885ce631413c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696310"
---
# <a name="applymulticontrolledca-operation"></a><span data-ttu-id="d69b1-102">ApplyMultiControlledCA 操作</span><span class="sxs-lookup"><span data-stu-id="d69b1-102">ApplyMultiControlledCA operation</span></span>

<span data-ttu-id="d69b1-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d69b1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d69b1-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d69b1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d69b1-105">应用单个受控操作的多重控制版本。</span><span class="sxs-lookup"><span data-stu-id="d69b1-105">Applies a multiply controlled version of a singly controlled operation.</span></span>
<span data-ttu-id="d69b1-106">修饰符 `CA` 指示 qubit 操作可控制和 adjointable。</span><span class="sxs-lookup"><span data-stu-id="d69b1-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="d69b1-107">输入</span><span class="sxs-lookup"><span data-stu-id="d69b1-107">Input</span></span>

### <a name="singlycontrolledop--qubit--unit-adj"></a><span data-ttu-id="d69b1-108">singlyControlledOp： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="d69b1-108">singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="d69b1-109">对单个 qubit 控制的操作。</span><span class="sxs-lookup"><span data-stu-id="d69b1-109">An operation controlled on a single qubit.</span></span>
<span data-ttu-id="d69b1-110">操作的参数中的第一个 qubit 假定为控件，而其余的则假定为目标 qubits。</span><span class="sxs-lookup"><span data-stu-id="d69b1-110">The first qubit in the argument of the operation assumed to be a control and the rest are assumed to be target qubits.</span></span>
<span data-ttu-id="d69b1-111">`ApplyMultiControlled` 始终 `singlyControlledOp` 使用长度至少为1的参数调用。</span><span class="sxs-lookup"><span data-stu-id="d69b1-111">`ApplyMultiControlled` always calls `singlyControlledOp` with an argument of length at least 1.</span></span>


### <a name="ccnot--ccnotop"></a><span data-ttu-id="d69b1-112">ccnot： [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="d69b1-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="d69b1-113">用于构造的受控控制的非入口。</span><span class="sxs-lookup"><span data-stu-id="d69b1-113">The controlled-controlled-NOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="d69b1-114">控件： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d69b1-114">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d69b1-115">要对其进行控制的 qubits `singlyControlledOp` 。</span><span class="sxs-lookup"><span data-stu-id="d69b1-115">The qubits that `singlyControlledOp` is to be controlled on.</span></span>
<span data-ttu-id="d69b1-116">的长度 `controls` 必须至少为1。</span><span class="sxs-lookup"><span data-stu-id="d69b1-116">The length of `controls` must be at least 1.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="d69b1-117">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d69b1-117">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d69b1-118">作用于的目标 qubits `singlyControlledOp` 。</span><span class="sxs-lookup"><span data-stu-id="d69b1-118">The target qubits that `singlyControlledOp` acts upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d69b1-119">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d69b1-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d69b1-120">注解</span><span class="sxs-lookup"><span data-stu-id="d69b1-120">Remarks</span></span>

<span data-ttu-id="d69b1-121">此操作仅使用 clean ancilla qubits。</span><span class="sxs-lookup"><span data-stu-id="d69b1-121">This operation uses only clean ancilla qubits.</span></span>

<span data-ttu-id="d69b1-122">有关说明和线路关系图，请参阅图4.10，& Nielsen 中的第4.3 节语</span><span class="sxs-lookup"><span data-stu-id="d69b1-122">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang</span></span>

## <a name="references"></a><span data-ttu-id="d69b1-123">参考</span><span class="sxs-lookup"><span data-stu-id="d69b1-123">References</span></span>

- [<span data-ttu-id="d69b1-124">*Michael Nielsen、Isaac 语* 、量程计算和量程信息</span><span class="sxs-lookup"><span data-stu-id="d69b1-124"> *Michael A. Nielsen , Isaac L. Chuang* , Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a><span data-ttu-id="d69b1-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d69b1-125">See Also</span></span>

- [<span data-ttu-id="d69b1-126">Canon. ApplyMultiControlledC</span><span class="sxs-lookup"><span data-stu-id="d69b1-126">Microsoft.Quantum.Canon.ApplyMultiControlledC</span></span>](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)