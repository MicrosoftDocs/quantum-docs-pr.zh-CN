---
uid: Microsoft.Quantum.Canon.AndLadder
title: AndLadder 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: AndLadder
qsharp.summary: Performs a controlled "AND ladder" on a register of target qubits.
ms.openlocfilehash: 05a0e8110539742501883fea75ac368d9946164d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696391"
---
# <a name="andladder-operation"></a><span data-ttu-id="d5c09-102">AndLadder 操作</span><span class="sxs-lookup"><span data-stu-id="d5c09-102">AndLadder operation</span></span>

<span data-ttu-id="d5c09-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d5c09-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d5c09-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d5c09-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d5c09-105">在目标 qubits 的寄存器上执行受控的 "AND 阶梯"。</span><span class="sxs-lookup"><span data-stu-id="d5c09-105">Performs a controlled "AND ladder" on a register of target qubits.</span></span>

```qsharp
operation AndLadder (ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="description"></a><span data-ttu-id="d5c09-106">说明</span><span class="sxs-lookup"><span data-stu-id="d5c09-106">Description</span></span>

<span data-ttu-id="d5c09-107">此操作应用以下映射中描述的转换： $ $ \begin{align} \ket{x \_ 1，\dots ..，x \_ n} \ket{y \_ 1，\dots ..，y \_ {n-1}} \mapsto \ket{x \_ 1，\dots ..，x \_ n} \ket{y \_ 1 \oplus (x \_ 1 \land x \_ 2) \dots ..，y \_ {n-1} \oplus (x \_ 1 \land x \_ 2 \land \cdots \land x \_ {n-1}}，\end{align} $ $，其中 $ \ket{x \_ 1，\dots ..，x \_ n} $ 表示的计算基础状态 `controls` ，其中 $ \ket{y \_ 1，\dots ..，y \_ {n-1}} $ 表示计算基础状态 `targets` 。</span><span class="sxs-lookup"><span data-stu-id="d5c09-107">This operation applies a transformation described by the following mapping of the computational basis, $$ \begin{align} \ket{x\_1, \dots, x\_n} \ket{y\_1, \dots, y\_{n - 1}} \mapsto \ket{x\_1, \dots, x\_n} \ket{ y\_1 \oplus (x\_1 \land x\_2), \dots, y\_{n - 1} \oplus (x\_1 \land x\_2 \land \cdots \land x\_{n - 1} }, \end{align} $$ where $\ket{x\_1, \dots, x\_n}$ refers to the computational basis states of `controls`, and where $\ket{y\_1, \dots, y\_{n - 1}}$ refers to the computational basis states of `targets`.</span></span>

## <a name="input"></a><span data-ttu-id="d5c09-108">输入</span><span class="sxs-lookup"><span data-stu-id="d5c09-108">Input</span></span>

### <a name="ccnot--ccnotop"></a><span data-ttu-id="d5c09-109">ccnot： [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="d5c09-109">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="d5c09-110">用于构造的 CCNOT 入口。</span><span class="sxs-lookup"><span data-stu-id="d5c09-110">The CCNOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="d5c09-111">控件： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d5c09-111">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d5c09-112">要用作和阶梯控件的 qubits 寄存器。</span><span class="sxs-lookup"><span data-stu-id="d5c09-112">A register of qubits to be used as controls for the and ladder.</span></span>
<span data-ttu-id="d5c09-113">此操作使计算基础状态保持不 `controls` 变。</span><span class="sxs-lookup"><span data-stu-id="d5c09-113">This operation leaves computational basis states of `controls` invariant.</span></span>
<span data-ttu-id="d5c09-114">的长度 `controls` 必须至少为2，并且必须等于的长度加 1 `targets` 。</span><span class="sxs-lookup"><span data-stu-id="d5c09-114">The length of `controls` must be at least 2, and must be equal to one plus the length of `targets`.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="d5c09-115">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d5c09-115">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d5c09-116">的长度 `targets` 必须至少为1，并且必须等于减1的长度 `controls` 。</span><span class="sxs-lookup"><span data-stu-id="d5c09-116">The length of `targets` must be at least 1 and equal to the length of `controls` minus one.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d5c09-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d5c09-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d5c09-118">注解</span><span class="sxs-lookup"><span data-stu-id="d5c09-118">Remarks</span></span>

- <span data-ttu-id="d5c09-119">用作和的一部分 <xref:microsoft.quantum.canon.applymulticontrolledc> <xref:microsoft.quantum.canon.applymulticontrolledca> 。</span><span class="sxs-lookup"><span data-stu-id="d5c09-119">Used as a part of <xref:microsoft.quantum.canon.applymulticontrolledc> and <xref:microsoft.quantum.canon.applymulticontrolledca>.</span></span>
- <span data-ttu-id="d5c09-120">有关说明和线路关系图，请参阅图4.10： Nielsen & 语中的第4.3 节。</span><span class="sxs-lookup"><span data-stu-id="d5c09-120">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang.</span></span>

## <a name="references"></a><span data-ttu-id="d5c09-121">参考</span><span class="sxs-lookup"><span data-stu-id="d5c09-121">References</span></span>

- [<span data-ttu-id="d5c09-122">*Michael Nielsen、Isaac 语* 、量程计算和量程信息</span><span class="sxs-lookup"><span data-stu-id="d5c09-122"> *Michael A. Nielsen , Isaac L. Chuang* , Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)