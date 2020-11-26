---
uid: Microsoft.Quantum.Characterization.QuantumPhaseEstimation
title: QuantumPhaseEstimation 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: QuantumPhaseEstimation
qsharp.summary: Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.
ms.openlocfilehash: 14ba3e012f6561e7089f9fe59b2a13516b211d51
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204209"
---
# <a name="quantumphaseestimation-operation"></a><span data-ttu-id="72fbb-102">QuantumPhaseEstimation 操作</span><span class="sxs-lookup"><span data-stu-id="72fbb-102">QuantumPhaseEstimation operation</span></span>

<span data-ttu-id="72fbb-103">命名空间 [：](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="72fbb-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="72fbb-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="72fbb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="72fbb-105">执行给定 oracle 和的量程阶段估算算法 `U` ，并将 `targetState` 该阶段读入大字节序量程寄存器。</span><span class="sxs-lookup"><span data-stu-id="72fbb-105">Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.</span></span>

```qsharp
operation QuantumPhaseEstimation (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[], controlRegister : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="72fbb-106">输入</span><span class="sxs-lookup"><span data-stu-id="72fbb-106">Input</span></span>

### <a name="oracle--discreteoracle"></a><span data-ttu-id="72fbb-107">oracle： [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="72fbb-107">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="72fbb-108">为给定整数幂 m 实现 $U ^ m $ 的操作。</span><span class="sxs-lookup"><span data-stu-id="72fbb-108">An operation implementing $U^m$ for given integer powers m.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="72fbb-109">targetState： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="72fbb-109">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="72fbb-110">表示状态 $ \ket{\phi} $ 的量程寄存器 $U $。</span><span class="sxs-lookup"><span data-stu-id="72fbb-110">A quantum register representing the state $\ket{\phi}$ acted on by $U$.</span></span> <span data-ttu-id="72fbb-111">如果 $ \ket{\phi} $ 是 $U $ 的 eigenstate，$U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ for $ \phi \in [0，2 \ pi) $ 未知阶段。</span><span class="sxs-lookup"><span data-stu-id="72fbb-111">If $\ket{\phi}$ is an eigenstate of $U$, $U\ket{\phi} = e^{i\phi} \ket{\phi}$ for $\phi \in [0, 2\pi)$ an unknown phase.</span></span>


### <a name="controlregister--bigendian"></a><span data-ttu-id="72fbb-112">controlRegister： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="72fbb-112">controlRegister : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="72fbb-113">大字节序表示形式整数寄存器，可用于控制提供的 oracle，并在应用程序中包含 $ \phi $ 的表示形式。</span><span class="sxs-lookup"><span data-stu-id="72fbb-113">A big-endian representation integer register that can be used to control the provided oracle, and that will contain the a representation of $\phi$ following the application of this operation.</span></span> <span data-ttu-id="72fbb-114">假定 controlRegister 在初始状态 $ \ket{00\cdots 0} $ 下启动，其中寄存器的长度指示所需的精度。</span><span class="sxs-lookup"><span data-stu-id="72fbb-114">The controlRegister is assumed to start in the initial state $\ket{00\cdots 0}$, where the length of the register indicates the desired precision.</span></span>



## <a name="output--unit"></a><span data-ttu-id="72fbb-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="72fbb-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

