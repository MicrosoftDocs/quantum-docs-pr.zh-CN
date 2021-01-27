---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: _prepareEntangledState 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 5a74978a536a92dafae0b532805bd8e8ae1c888e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830974"
---
# <a name="_prepareentangledstate-operation"></a><span data-ttu-id="71263-102">_prepareEntangledState 操作</span><span class="sxs-lookup"><span data-stu-id="71263-102">_prepareEntangledState operation</span></span>

<span data-ttu-id="71263-103">命名空间 [：](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="71263-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="71263-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="71263-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="71263-105">给定两个寄存器，在各自寄存器上的每对 qubits 之间准备最大化放大状态。</span><span class="sxs-lookup"><span data-stu-id="71263-105">Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers.</span></span>
<span data-ttu-id="71263-106">所有 qubits 必须以 | 0 ⟩状态启动。</span><span class="sxs-lookup"><span data-stu-id="71263-106">All qubits must start in the |0⟩ state.</span></span>

<span data-ttu-id="71263-107">结果是，每个寄存器中的相应 qubits 对都处于 $ \bra{\ beta_ {00} } \ket{\ beta_ {00} } $ 中。</span><span class="sxs-lookup"><span data-stu-id="71263-107">The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.</span></span>

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="71263-108">输入</span><span class="sxs-lookup"><span data-stu-id="71263-108">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="71263-109">left： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="71263-109">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="71263-110">$ \Ket{0\cdots 0} $ 状态中的 qubit 数组</span><span class="sxs-lookup"><span data-stu-id="71263-110">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="71263-111">right： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="71263-111">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="71263-112">$ \Ket{0\cdots 0} $ 状态中的 qubit 数组</span><span class="sxs-lookup"><span data-stu-id="71263-112">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="71263-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="71263-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

