---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: ApplyFixedPointAmplification 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: fa19c3bb06ae91a2fa18acb6f853020830e749f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847236"
---
# <a name="applyfixedpointamplification-operation"></a><span data-ttu-id="2fca3-102">ApplyFixedPointAmplification 操作</span><span class="sxs-lookup"><span data-stu-id="2fca3-102">ApplyFixedPointAmplification operation</span></span>

<span data-ttu-id="2fca3-103">命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="2fca3-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="2fca3-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2fca3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2fca3-105">Fixed-Point 振幅放大算法</span><span class="sxs-lookup"><span data-stu-id="2fca3-105">Fixed-Point Amplitude Amplification algorithm</span></span>

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="2fca3-106">输入</span><span class="sxs-lookup"><span data-stu-id="2fca3-106">Input</span></span>

### <a name="statepreporacle--stateoracle"></a><span data-ttu-id="2fca3-107">statePrepOracle： [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="2fca3-107">statePrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="2fca3-108">准备开始状态的单一 oracle。</span><span class="sxs-lookup"><span data-stu-id="2fca3-108">Unitary oracle that prepares the start state.</span></span>


### <a name="startqubits--qubit"></a><span data-ttu-id="2fca3-109">startQubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2fca3-109">startQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2fca3-110">Qubit 注册</span><span class="sxs-lookup"><span data-stu-id="2fca3-110">Qubit register</span></span>



## <a name="output--unit"></a><span data-ttu-id="2fca3-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2fca3-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2fca3-112">备注</span><span class="sxs-lookup"><span data-stu-id="2fca3-112">Remarks</span></span>

<span data-ttu-id="2fca3-113">StartQubits 必须处于 $ \ket{0 \cdots 0} $ 状态。</span><span class="sxs-lookup"><span data-stu-id="2fca3-113">The startQubits must be in the $\ket{0 \cdots 0}$ state.</span></span> <span data-ttu-id="2fca3-114">此操作将循环访问多个查询，以 $2 $ 的幂来循环访问，直到达到最大数量的查询或找到目标状态。</span><span class="sxs-lookup"><span data-stu-id="2fca3-114">This operation iterates over a number of queries in powers of $2$ until either a maximal number of queries is reached, or the target state is found.</span></span>