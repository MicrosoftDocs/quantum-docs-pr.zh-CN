---
uid: Microsoft.Quantum.Characterization.EstimateFrequency
title: EstimateFrequency 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequency
qsharp.summary: Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 83589637a7bfa328812207271844411f57d42097
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695899"
---
# <a name="estimatefrequency-operation"></a><span data-ttu-id="fbf66-102">EstimateFrequency 操作</span><span class="sxs-lookup"><span data-stu-id="fbf66-102">EstimateFrequency operation</span></span>

<span data-ttu-id="fbf66-103">命名空间 [：](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="fbf66-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="fbf66-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fbf66-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fbf66-105">考虑到准备和度量， `Zero` 通过执行给定数量的试验，估算量化指标成功 (返回) 的频率。</span><span class="sxs-lookup"><span data-stu-id="fbf66-105">Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.</span></span>

```qsharp
operation EstimateFrequency (preparation : (Qubit[] => Unit), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="fbf66-106">输入</span><span class="sxs-lookup"><span data-stu-id="fbf66-106">Input</span></span>

### <a name="preparation--qubit--unit"></a><span data-ttu-id="fbf66-107">准备： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fbf66-107">preparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="fbf66-108">操作 $P $，该操作在其输入寄存器上准备给定状态 $ \rho $。</span><span class="sxs-lookup"><span data-stu-id="fbf66-108">An operation $P$ that prepares a given state $\rho$ on its input register.</span></span>


### <a name="measurement--qubit--__invalidresult__"></a><span data-ttu-id="fbf66-109">度量： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="fbf66-109">measurement : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __invalid<Result>__</span></span> 

<span data-ttu-id="fbf66-110">操作 $M $ 表示感兴趣的度量。</span><span class="sxs-lookup"><span data-stu-id="fbf66-110">An operation $M$ representing the measurement of interest.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="fbf66-111">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fbf66-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fbf66-112">准备和测量每个操作的 qubits 数目。</span><span class="sxs-lookup"><span data-stu-id="fbf66-112">The number of qubits on which the preparation and measurement each act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="fbf66-113">nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fbf66-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fbf66-114">为了估计感兴趣的频率，应执行度量的次数。</span><span class="sxs-lookup"><span data-stu-id="fbf66-114">The number of times that the measurement should be performed in order to estimate the frequency of interest.</span></span>



## <a name="output--double"></a><span data-ttu-id="fbf66-115">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fbf66-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fbf66-116">估计 $ \hat{p} $ of $M (P ( \ket{00 \cdots 0} \bra{00 \cdots 0} ) # B3 $ 返回的频率 `Zero` ，使用无偏差二项式估计器 $ \hat{p} = n \_ {\uparrow}/n \_ {\text{measurements}} $，其中 $n \_ {\uparrow} $ 是 `Zero` 观察到的结果数。</span><span class="sxs-lookup"><span data-stu-id="fbf66-116">An estimate $\hat{p}$ of the frequency with which $M(P(\ket{00 \cdots 0}\bra{00 \cdots 0}))$ returns `Zero`, obtained using the unbiased binomial estimator $\hat{p} = n\_{\uparrow} / n\_{\text{measurements}}$, where $n\_{\uparrow}$ is the number of `Zero` results observed.</span></span>

<span data-ttu-id="fbf66-117">这对于遵守物理限制的目标计算机尤其重要，因此无法衡量概率。</span><span class="sxs-lookup"><span data-stu-id="fbf66-117">This is particularly important on target machines which respect physical limitations, such that probabilities cannot be measured.</span></span>