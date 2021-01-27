---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: PrepareEntangledState 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 9bf42131860b9fe9bd223ade32f95ec747abefe8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854368"
---
# <a name="prepareentangledstate-operation"></a><span data-ttu-id="a9091-102">PrepareEntangledState 操作</span><span class="sxs-lookup"><span data-stu-id="a9091-102">PrepareEntangledState operation</span></span>

<span data-ttu-id="a9091-103">命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="a9091-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="a9091-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a9091-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a9091-105">成对 entangles 两个 qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="a9091-105">Pairwise entangles two qubit registers.</span></span>

<span data-ttu-id="a9091-106">也就是说，假设有两个寄存器，则准备最大化放大 state $ \frac {1} {\sqrt {2} } \left ( \ket {00} + \ket \right 在 {11} 各自寄存器上的每对 qubits 之间) $，假设每个注册都以 $ \ket{0\cdots 0} $ 状态启动。</span><span class="sxs-lookup"><span data-stu-id="a9091-106">That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.</span></span>

```qsharp
operation PrepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a9091-107">输入</span><span class="sxs-lookup"><span data-stu-id="a9091-107">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="a9091-108">left： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a9091-108">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a9091-109">$ \Ket{0\cdots 0} $ 状态中的 qubit 数组</span><span class="sxs-lookup"><span data-stu-id="a9091-109">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="a9091-110">right： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a9091-110">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a9091-111">$ \Ket{0\cdots 0} $ 状态中的 qubit 数组</span><span class="sxs-lookup"><span data-stu-id="a9091-111">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="a9091-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a9091-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

