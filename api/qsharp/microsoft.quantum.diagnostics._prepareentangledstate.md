---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: _prepareEntangledState 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 384dad5905cec50b500028e1bc352a742122b299
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695620"
---
# <a name="_prepareentangledstate-operation"></a><span data-ttu-id="dc9b2-102">_prepareEntangledState 操作</span><span class="sxs-lookup"><span data-stu-id="dc9b2-102">_prepareEntangledState operation</span></span>

<span data-ttu-id="dc9b2-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="dc9b2-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="dc9b2-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dc9b2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dc9b2-105">给定两个寄存器，在各自寄存器上的每对 qubits 之间准备最大化放大状态。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-105">Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers.</span></span>
<span data-ttu-id="dc9b2-106">所有 qubits 必须以 | 0 ⟩状态启动。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-106">All qubits must start in the |0⟩ state.</span></span>

<span data-ttu-id="dc9b2-107">结果是，每个寄存器中的相应 qubits 对都处于 $ \bra{\ beta_ {00} } \ket{\ beta_ {00} } $ 中。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-107">The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.</span></span>

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="dc9b2-108">输入</span><span class="sxs-lookup"><span data-stu-id="dc9b2-108">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="dc9b2-109">left： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="dc9b2-109">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="dc9b2-110">$ \Ket{0\cdots 0} $ 状态中的 qubit 数组</span><span class="sxs-lookup"><span data-stu-id="dc9b2-110">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="dc9b2-111">right： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="dc9b2-111">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="dc9b2-112">$ \Ket{0\cdots 0} $ 状态中的 qubit 数组</span><span class="sxs-lookup"><span data-stu-id="dc9b2-112">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="dc9b2-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dc9b2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

