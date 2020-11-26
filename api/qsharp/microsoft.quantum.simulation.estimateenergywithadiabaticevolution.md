---
uid: Microsoft.Quantum.Simulation.EstimateEnergyWithAdiabaticEvolution
title: EstimateEnergyWithAdiabaticEvolution 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EstimateEnergyWithAdiabaticEvolution
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: b279d35418b8f013ad0d72e9a980c9bf6ce0689a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225323"
---
# <a name="estimateenergywithadiabaticevolution-operation"></a><span data-ttu-id="db194-102">EstimateEnergyWithAdiabaticEvolution 操作</span><span class="sxs-lookup"><span data-stu-id="db194-102">EstimateEnergyWithAdiabaticEvolution operation</span></span>

<span data-ttu-id="db194-103">命名空间 [：](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="db194-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="db194-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="db194-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="db194-105">执行状态准备，方法是 `statePrepUnitary` 对自动分配的输入状态应用，然后使用 adiabatic 状态准备 `adiabaticUnitary` ，并最终使用相对于产生状态的阶段估算 `qpeUnitary` `phaseEstAlgorithm` 。</span><span class="sxs-lookup"><span data-stu-id="db194-105">Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.</span></span>

```qsharp
operation EstimateEnergyWithAdiabaticEvolution (nQubits : Int, statePrepUnitary : (Qubit[] => Unit), adiabaticUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double)) : Double
```


## <a name="input"></a><span data-ttu-id="db194-106">输入</span><span class="sxs-lookup"><span data-stu-id="db194-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="db194-107">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="db194-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="db194-108">用于模拟的 qubits 的数目。</span><span class="sxs-lookup"><span data-stu-id="db194-108">Number of qubits used for the simulation.</span></span>


### <a name="stateprepunitary--qubit--unit"></a><span data-ttu-id="db194-109">statePrepUnitary： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="db194-109">statePrepUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="db194-110">Oracle 表示初始 dynamical 生成器的状态准备。</span><span class="sxs-lookup"><span data-stu-id="db194-110">An oracle representing state preparation for the initial dynamical generator.</span></span>


### <a name="adiabaticunitary--qubit--unit"></a><span data-ttu-id="db194-111">adiabaticUnitary： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="db194-111">adiabaticUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="db194-112">Oracle，表示要用于实现到算法最终状态的扫描的 adiabatic 进化算法。</span><span class="sxs-lookup"><span data-stu-id="db194-112">An oracle representing the adiabatic evolution algorithm to be used to implement the sweeps to the final state of the algorithm.</span></span>


### <a name="qpeunitary--qubit--unit--is-adj--ctl"></a><span data-ttu-id="db194-113">qpeUnitary： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="db194-113">qpeUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="db194-114">一种 oracle，表示单一操作员 $U $，表示 dynamical 发电机下的时间 $ \ket{\phi} $ 和接地状态 $E 能量为的演变 \\ 。</span><span class="sxs-lookup"><span data-stu-id="db194-114">An oracle representing a unitary operator $U$ representing evolution for time $\delta t$ under a dynamical generator with ground state $\ket{\phi}$ and ground state energy $E = \phi\\,\delta t$.</span></span>


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a><span data-ttu-id="db194-115">phaseEstAlgorithm： ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) => [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="db194-115">phaseEstAlgorithm : ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span></span> 

<span data-ttu-id="db194-116">对给定的单一操作执行阶段估计的操作。</span><span class="sxs-lookup"><span data-stu-id="db194-116">An operation that performs phase estimation on a given unitary operation.</span></span>
<span data-ttu-id="db194-117">有关更多详细信息，请参阅 [迭代阶段估算](/quantum/libraries/characterization#iterative-phase-estimation) 。</span><span class="sxs-lookup"><span data-stu-id="db194-117">See [iterative phase estimation](/quantum/libraries/characterization#iterative-phase-estimation) for more details.</span></span>



## <a name="output--double"></a><span data-ttu-id="db194-118">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="db194-118">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="db194-119">由 $U $ 表示的生成器的 "估计 $ \hat{\phi} $"。</span><span class="sxs-lookup"><span data-stu-id="db194-119">An estimate $\hat{\phi}$ of the ground state energy $\phi$ of the generator represented by $U$.</span></span>