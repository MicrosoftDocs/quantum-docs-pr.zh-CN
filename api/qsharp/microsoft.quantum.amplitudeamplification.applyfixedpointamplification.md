---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: ApplyFixedPointAmplification 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: f506be7b2e3f65cf89694e30d79c04ec30d25035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700120"
---
# <a name="applyfixedpointamplification-operation"></a><span data-ttu-id="e1762-102">ApplyFixedPointAmplification 操作</span><span class="sxs-lookup"><span data-stu-id="e1762-102">ApplyFixedPointAmplification operation</span></span>

<span data-ttu-id="e1762-103">命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="e1762-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="e1762-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e1762-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e1762-105">Fixed-Point 振幅放大算法</span><span class="sxs-lookup"><span data-stu-id="e1762-105">Fixed-Point Amplitude Amplification algorithm</span></span>

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="e1762-106">输入</span><span class="sxs-lookup"><span data-stu-id="e1762-106">Input</span></span>

### <a name="statepreporacle--stateoracle"></a><span data-ttu-id="e1762-107">statePrepOracle： [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="e1762-107">statePrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="e1762-108">准备开始状态的单一 oracle。</span><span class="sxs-lookup"><span data-stu-id="e1762-108">Unitary oracle that prepares the start state.</span></span>


### <a name="startqubits--qubit"></a><span data-ttu-id="e1762-109">startQubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e1762-109">startQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e1762-110">Qubit 注册</span><span class="sxs-lookup"><span data-stu-id="e1762-110">Qubit register</span></span>



## <a name="output--unit"></a><span data-ttu-id="e1762-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e1762-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e1762-112">注解</span><span class="sxs-lookup"><span data-stu-id="e1762-112">Remarks</span></span>

<span data-ttu-id="e1762-113">StartQubits 必须处于 $ \ket{0 \cdots 0} $ 状态。</span><span class="sxs-lookup"><span data-stu-id="e1762-113">The startQubits must be in the $\ket{0 \cdots 0}$ state.</span></span> <span data-ttu-id="e1762-114">此操作将循环访问多个查询，以 $2 $ 的幂来循环访问，直到达到最大数量的查询或找到目标状态。</span><span class="sxs-lookup"><span data-stu-id="e1762-114">This operation iterates over a number of queries in powers of $2$ until either a maximal number of queries is reached, or the target state is found.</span></span>