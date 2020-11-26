---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: ApplyFixedPointAmplification 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: 13e70b1ebd5e3bf0996e6a76f4bffe57ca2d2250
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191527"
---
# <a name="applyfixedpointamplification-operation"></a><span data-ttu-id="7c4ed-102">ApplyFixedPointAmplification 操作</span><span class="sxs-lookup"><span data-stu-id="7c4ed-102">ApplyFixedPointAmplification operation</span></span>

<span data-ttu-id="7c4ed-103">命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="7c4ed-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="7c4ed-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7c4ed-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7c4ed-105">Fixed-Point 振幅放大算法</span><span class="sxs-lookup"><span data-stu-id="7c4ed-105">Fixed-Point Amplitude Amplification algorithm</span></span>

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="7c4ed-106">输入</span><span class="sxs-lookup"><span data-stu-id="7c4ed-106">Input</span></span>

### <a name="statepreporacle--stateoracle"></a><span data-ttu-id="7c4ed-107">statePrepOracle： [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="7c4ed-107">statePrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="7c4ed-108">准备开始状态的单一 oracle。</span><span class="sxs-lookup"><span data-stu-id="7c4ed-108">Unitary oracle that prepares the start state.</span></span>


### <a name="startqubits--qubit"></a><span data-ttu-id="7c4ed-109">startQubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7c4ed-109">startQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7c4ed-110">Qubit 注册</span><span class="sxs-lookup"><span data-stu-id="7c4ed-110">Qubit register</span></span>



## <a name="output--unit"></a><span data-ttu-id="7c4ed-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7c4ed-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7c4ed-112">备注</span><span class="sxs-lookup"><span data-stu-id="7c4ed-112">Remarks</span></span>

<span data-ttu-id="7c4ed-113">StartQubits 必须处于 $ \ket{0 \cdots 0} $ 状态。</span><span class="sxs-lookup"><span data-stu-id="7c4ed-113">The startQubits must be in the $\ket{0 \cdots 0}$ state.</span></span> <span data-ttu-id="7c4ed-114">此操作将循环访问多个查询，以 $2 $ 的幂来循环访问，直到达到最大数量的查询或找到目标状态。</span><span class="sxs-lookup"><span data-stu-id="7c4ed-114">This operation iterates over a number of queries in powers of $2$ until either a maximal number of queries is reached, or the target state is found.</span></span>