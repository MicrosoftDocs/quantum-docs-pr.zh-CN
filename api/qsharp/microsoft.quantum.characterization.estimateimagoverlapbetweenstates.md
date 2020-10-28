---
uid: Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates
title: EstimateImagOverlapBetweenStates 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateImagOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the imaginary part of the overlap between the states prepared by each operation.
ms.openlocfilehash: 8b73115c3243c594897ac4b309ec52d5e9863d26
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695893"
---
# <a name="estimateimagoverlapbetweenstates-operation"></a><span data-ttu-id="27184-102">EstimateImagOverlapBetweenStates 操作</span><span class="sxs-lookup"><span data-stu-id="27184-102">EstimateImagOverlapBetweenStates operation</span></span>

<span data-ttu-id="27184-103">命名空间 [：](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="27184-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="27184-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="27184-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="27184-105">假设每个操作都准备好状态的副本，并估计每个操作准备的状态之间重叠部分的虚部。</span><span class="sxs-lookup"><span data-stu-id="27184-105">Given two operations which each prepare copies of a state, estimates the imaginary part of the overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateImagOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="27184-106">输入</span><span class="sxs-lookup"><span data-stu-id="27184-106">Input</span></span>

### <a name="commonpreparation--qubit--unit-adj"></a><span data-ttu-id="27184-107">commonPreparation： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="27184-107">commonPreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="27184-108">准备固定输入状态的操作。</span><span class="sxs-lookup"><span data-stu-id="27184-108">An operation that prepares a fixed input state.</span></span>


### <a name="preparation1--qubit--unit-adj--ctl"></a><span data-ttu-id="27184-109">preparation1： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="27184-109">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="27184-110">要进行比较的两个状态准备操作中的第一个。</span><span class="sxs-lookup"><span data-stu-id="27184-110">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit-adj--ctl"></a><span data-ttu-id="27184-111">preparation2： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="27184-111">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="27184-112">要进行比较的两个状态准备操作的第二个。</span><span class="sxs-lookup"><span data-stu-id="27184-112">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="27184-113">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="27184-113">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="27184-114">对其执行、和的 qubits 的数目 `commonPreparation` `preparation1` `preparation2` 。</span><span class="sxs-lookup"><span data-stu-id="27184-114">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="27184-115">nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="27184-115">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="27184-116">要在估计重叠时使用的度量值的数量。</span><span class="sxs-lookup"><span data-stu-id="27184-116">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="27184-117">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="27184-117">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="27184-118">注解</span><span class="sxs-lookup"><span data-stu-id="27184-118">Remarks</span></span>

<span data-ttu-id="27184-119">此操作使用 Hadamard 测试查找 $ $ \begin{align} \braket{\psi 的虚部 |V ^ {\dagger} U |\psi} \end{align} $ $ 其中 $ \ket{\psi} $ 是准备的状态 `commonPreparation` ，$U $ 是的操作的单一表示形式 `preparation1` ，其中 $V $ 对应于 `preparation2` 。</span><span class="sxs-lookup"><span data-stu-id="27184-119">This operation uses the Hadamard test to find the imaginary part of $$ \begin{align} \braket{\psi | V^{\dagger} U | \psi} \end{align} $$ where $\ket{\psi}$ is the state prepared by `commonPreparation`, $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="references"></a><span data-ttu-id="27184-120">参考</span><span class="sxs-lookup"><span data-stu-id="27184-120">References</span></span>

- <span data-ttu-id="27184-121">Aharonov *et* [quant/0511096](https://arxiv.org/abs/quant-ph/0511096)。</span><span class="sxs-lookup"><span data-stu-id="27184-121">Aharonov *et al.* [quant-ph/0511096](https://arxiv.org/abs/quant-ph/0511096).</span></span>

## <a name="see-also"></a><span data-ttu-id="27184-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27184-122">See Also</span></span>

- [<span data-ttu-id="27184-123">EstimateRealOverlapBetweenStates。</span><span class="sxs-lookup"><span data-stu-id="27184-123">Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [<span data-ttu-id="27184-124">EstimateOverlapBetweenStates。</span><span class="sxs-lookup"><span data-stu-id="27184-124">Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)