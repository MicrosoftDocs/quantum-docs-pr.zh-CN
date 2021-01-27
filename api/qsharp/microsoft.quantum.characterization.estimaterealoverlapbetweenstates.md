---
uid: Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates
title: EstimateRealOverlapBetweenStates 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateRealOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the real part of the overlap between the states prepared by each operation.
ms.openlocfilehash: 1448e760294e958b152f4ceb3faf979441ca986d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851859"
---
# <a name="estimaterealoverlapbetweenstates-operation"></a><span data-ttu-id="d9760-102">EstimateRealOverlapBetweenStates 操作</span><span class="sxs-lookup"><span data-stu-id="d9760-102">EstimateRealOverlapBetweenStates operation</span></span>

<span data-ttu-id="d9760-103">命名空间 [：](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="d9760-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="d9760-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d9760-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d9760-105">假设每个操作都准备好状态的副本，并对每个操作准备的状态之间的重叠部分进行估计。</span><span class="sxs-lookup"><span data-stu-id="d9760-105">Given two operations which each prepare copies of a state, estimates the real part of the overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateRealOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="d9760-106">输入</span><span class="sxs-lookup"><span data-stu-id="d9760-106">Input</span></span>

### <a name="commonpreparation--qubit--unit--is-adj"></a><span data-ttu-id="d9760-107">commonPreparation： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="d9760-107">commonPreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="d9760-108">准备固定输入状态的操作。</span><span class="sxs-lookup"><span data-stu-id="d9760-108">An operation that prepares a fixed input state.</span></span>


### <a name="preparation1--qubit--unit--is-adj--ctl"></a><span data-ttu-id="d9760-109">preparation1： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="d9760-109">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="d9760-110">要进行比较的两个状态准备操作中的第一个。</span><span class="sxs-lookup"><span data-stu-id="d9760-110">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit--is-adj--ctl"></a><span data-ttu-id="d9760-111">preparation2： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="d9760-111">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="d9760-112">要进行比较的两个状态准备操作的第二个。</span><span class="sxs-lookup"><span data-stu-id="d9760-112">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="d9760-113">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d9760-113">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d9760-114">对其执行、和的 qubits 的数目 `commonPreparation` `preparation1` `preparation2` 。</span><span class="sxs-lookup"><span data-stu-id="d9760-114">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="d9760-115">nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d9760-115">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d9760-116">要在估计重叠时使用的度量值的数量。</span><span class="sxs-lookup"><span data-stu-id="d9760-116">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="d9760-117">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d9760-117">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="d9760-118">备注</span><span class="sxs-lookup"><span data-stu-id="d9760-118">Remarks</span></span>

<span data-ttu-id="d9760-119">此操作使用 Hadamard 测试查找 $ $ \begin{align} \braket{\psi 的实部 |V ^ {\dagger} U |\psi} \end{align} $ $ 其中 $ \ket{\psi} $ 是准备的状态 `commonPreparation` ，$U $ 是的操作的单一表示形式 `preparation1` ，其中 $V $ 对应于 `preparation2` 。</span><span class="sxs-lookup"><span data-stu-id="d9760-119">This operation uses the Hadamard test to find the real part of $$ \begin{align} \braket{\psi | V^{\dagger} U | \psi} \end{align} $$ where $\ket{\psi}$ is the state prepared by `commonPreparation`, $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="references"></a><span data-ttu-id="d9760-120">参考</span><span class="sxs-lookup"><span data-stu-id="d9760-120">References</span></span>

- <span data-ttu-id="d9760-121">Aharonov *et* [quant/0511096](https://arxiv.org/abs/quant-ph/0511096)。</span><span class="sxs-lookup"><span data-stu-id="d9760-121">Aharonov *et al.* [quant-ph/0511096](https://arxiv.org/abs/quant-ph/0511096).</span></span>

## <a name="see-also"></a><span data-ttu-id="d9760-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9760-122">See Also</span></span>

- [<span data-ttu-id="d9760-123">EstimateImagOverlapBetweenStates。</span><span class="sxs-lookup"><span data-stu-id="d9760-123">Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)
- [<span data-ttu-id="d9760-124">EstimateOverlapBetweenStates。</span><span class="sxs-lookup"><span data-stu-id="d9760-124">Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)