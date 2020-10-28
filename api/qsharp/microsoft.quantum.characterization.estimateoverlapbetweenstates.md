---
uid: Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates
title: EstimateOverlapBetweenStates 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.
ms.openlocfilehash: 58a367c7ff7d13ac5c1eb1588fb8dac66414776c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695886"
---
# <a name="estimateoverlapbetweenstates-operation"></a><span data-ttu-id="d77be-102">EstimateOverlapBetweenStates 操作</span><span class="sxs-lookup"><span data-stu-id="d77be-102">EstimateOverlapBetweenStates operation</span></span>

<span data-ttu-id="d77be-103">命名空间 [：](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="d77be-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="d77be-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d77be-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d77be-105">给定两个操作，每个操作都准备状态的副本，并估计每个操作准备的状态之间的平方重叠。</span><span class="sxs-lookup"><span data-stu-id="d77be-105">Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateOverlapBetweenStates (preparation1 : (Qubit[] => Unit is Adj), preparation2 : (Qubit[] => Unit is Adj), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="d77be-106">输入</span><span class="sxs-lookup"><span data-stu-id="d77be-106">Input</span></span>

### <a name="preparation1--qubit--unit-adj"></a><span data-ttu-id="d77be-107">preparation1： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="d77be-107">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="d77be-108">要进行比较的两个状态准备操作中的第一个。</span><span class="sxs-lookup"><span data-stu-id="d77be-108">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit-adj"></a><span data-ttu-id="d77be-109">preparation2： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="d77be-109">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="d77be-110">要进行比较的两个状态准备操作的第二个。</span><span class="sxs-lookup"><span data-stu-id="d77be-110">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="d77be-111">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d77be-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d77be-112">对其执行、和的 qubits 的数目 `commonPreparation` `preparation1` `preparation2` 。</span><span class="sxs-lookup"><span data-stu-id="d77be-112">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="d77be-113">nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d77be-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d77be-114">要在估计重叠时使用的度量值的数量。</span><span class="sxs-lookup"><span data-stu-id="d77be-114">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="d77be-115">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d77be-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="d77be-116">注解</span><span class="sxs-lookup"><span data-stu-id="d77be-116">Remarks</span></span>

<span data-ttu-id="d77be-117">此操作使用交换测试查找 $ $ \begin{align} \left |\braket{00\cdots 0 |V ^ {\dagger} U |00 \ cdots 0} \right | ^ 2 \end{align} $ $，其中 $U $ 是操作的单一表示形式 `preparation1` ，其中 $V $ 对应于 `preparation2` 。</span><span class="sxs-lookup"><span data-stu-id="d77be-117">This operation uses the SWAP test to find $$ \begin{align} \left| \braket{00\cdots 0 | V^{\dagger} U | 00\cdots 0} \right|^2 \end{align} $$ where $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="see-also"></a><span data-ttu-id="d77be-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d77be-118">See Also</span></span>

- [<span data-ttu-id="d77be-119">EstimateRealOverlapBetweenStates。</span><span class="sxs-lookup"><span data-stu-id="d77be-119">Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [<span data-ttu-id="d77be-120">EstimateImagOverlapBetweenStates。</span><span class="sxs-lookup"><span data-stu-id="d77be-120">Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)