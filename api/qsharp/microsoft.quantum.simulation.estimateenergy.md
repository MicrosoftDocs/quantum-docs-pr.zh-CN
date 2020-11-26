---
uid: Microsoft.Quantum.Simulation.EstimateEnergy
title: EstimateEnergy 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EstimateEnergy
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: 0a02a8aad891c45b184b9b18d4e9383236485940
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229488"
---
# <a name="estimateenergy-operation"></a><span data-ttu-id="0f550-102">EstimateEnergy 操作</span><span class="sxs-lookup"><span data-stu-id="0f550-102">EstimateEnergy operation</span></span>

<span data-ttu-id="0f550-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="0f550-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="0f550-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0f550-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0f550-105">通过对 `statePrepUnitary` 使用生成的状态的自动分配的输入状态阶段估算应用，来执行状态准备 `qpeUnitary` `phaseEstAlgorithm` 。</span><span class="sxs-lookup"><span data-stu-id="0f550-105">Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.</span></span>

```qsharp
operation EstimateEnergy (nQubits : Int, statePrepUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double)) : Double
```


## <a name="input"></a><span data-ttu-id="0f550-106">输入</span><span class="sxs-lookup"><span data-stu-id="0f550-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="0f550-107">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0f550-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0f550-108">用于执行模拟的 qubits 的数目。</span><span class="sxs-lookup"><span data-stu-id="0f550-108">Number of qubits used to perform simulation.</span></span>


### <a name="stateprepunitary--qubit--unit"></a><span data-ttu-id="0f550-109">statePrepUnitary： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0f550-109">statePrepUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0f550-110">Oracle 表示初始 dynamical 生成器的状态准备。</span><span class="sxs-lookup"><span data-stu-id="0f550-110">An oracle representing state preparation for the initial dynamical generator.</span></span>


### <a name="qpeunitary--qubit--unit--is-adj--ctl"></a><span data-ttu-id="0f550-111">qpeUnitary： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="0f550-111">qpeUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="0f550-112">一种 oracle，表示单一操作员 $U $，表示 dynamical 发电机下的时间 $ \ket{\phi} $ 和接地状态 $E 能量为的演变 \\ 。</span><span class="sxs-lookup"><span data-stu-id="0f550-112">An oracle representing a unitary operator $U$ representing evolution for time $\delta t$ under a dynamical generator with ground state $\ket{\phi}$ and ground state energy $E = \phi\\,\delta t$.</span></span>


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a><span data-ttu-id="0f550-113">phaseEstAlgorithm： ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) => [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0f550-113">phaseEstAlgorithm : ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span></span> 

<span data-ttu-id="0f550-114">对给定的单一操作执行阶段估计的操作。</span><span class="sxs-lookup"><span data-stu-id="0f550-114">An operation that performs phase estimation on a given unitary operation.</span></span>
<span data-ttu-id="0f550-115">有关更多详细信息，请参阅 [迭代阶段估算](/quantum/libraries/characterization#iterative-phase-estimation) 。</span><span class="sxs-lookup"><span data-stu-id="0f550-115">See [iterative phase estimation](/quantum/libraries/characterization#iterative-phase-estimation) for more details.</span></span>



## <a name="output--double"></a><span data-ttu-id="0f550-116">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0f550-116">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0f550-117">由 $U $ 表示的生成器的基本状态能量 $ \phi $ 的估计 $ \hat{\phi} $。</span><span class="sxs-lookup"><span data-stu-id="0f550-117">An estimate $\hat{\phi}$ of the ground state energy $\phi$ of the ground state energy of the generator represented by $U$.</span></span>