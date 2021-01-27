---
uid: Microsoft.Quantum.Characterization.EstimateFrequencyA
title: EstimateFrequencyA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequencyA
qsharp.summary: Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 6cca8dff70283e0d69441db8a5b31fb5bfb3082a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839914"
---
# <a name="estimatefrequencya-operation"></a><span data-ttu-id="d9bb3-102">EstimateFrequencyA 操作</span><span class="sxs-lookup"><span data-stu-id="d9bb3-102">EstimateFrequencyA operation</span></span>

<span data-ttu-id="d9bb3-103">命名空间 [：](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="d9bb3-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="d9bb3-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d9bb3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d9bb3-105">对于 adjointable 和度量值的准备， `Zero` 通过执行给定数量的试验来估算度量成功 (返回) 的频率。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-105">Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.</span></span>

```qsharp
operation EstimateFrequencyA (preparation : (Qubit[] => Unit is Adj), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="d9bb3-106">输入</span><span class="sxs-lookup"><span data-stu-id="d9bb3-106">Input</span></span>

### <a name="preparation--qubit--unit--is-adj"></a><span data-ttu-id="d9bb3-107">准备： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="d9bb3-107">preparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="d9bb3-108">Adjointable 操作 $P $，该操作在其输入寄存器上准备给定状态 $ \rho $。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-108">An adjointable operation $P$ that prepares a given state $\rho$ on its input register.</span></span>


### <a name="measurement--qubit--__invalidresult__"></a><span data-ttu-id="d9bb3-109">度量： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] =>__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="d9bb3-109">measurement : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __invalid<Result>__</span></span> 

<span data-ttu-id="d9bb3-110">操作 $M $ 表示感兴趣的度量。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-110">An operation $M$ representing the measurement of interest.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="d9bb3-111">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d9bb3-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d9bb3-112">准备和测量每个操作的 qubits 数目。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-112">The number of qubits on which the preparation and measurement each act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="d9bb3-113">nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d9bb3-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d9bb3-114">为了估计感兴趣的频率，应执行度量的次数。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-114">The number of times that the measurement should be performed in order to estimate the frequency of interest.</span></span>



## <a name="output--double"></a><span data-ttu-id="d9bb3-115">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d9bb3-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d9bb3-116">估计 $ \hat{p} $ of $M (P ( \ket{00 \cdots 0} \bra{00 \cdots 0} ) # B3 $ 返回的频率 `Zero` ，使用无偏差二项式估计器 $ \hat{p} = n \_ {\uparrow}/n \_ {\text{measurements}} $，其中 $n \_ {\uparrow} $ 是 `Zero` 观察到的结果数。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-116">An estimate $\hat{p}$ of the frequency with which $M(P(\ket{00 \cdots 0}\bra{00 \cdots 0}))$ returns `Zero`, obtained using the unbiased binomial estimator $\hat{p} = n\_{\uparrow} / n\_{\text{measurements}}$, where $n\_{\uparrow}$ is the number of `Zero` results observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="d9bb3-117">备注</span><span class="sxs-lookup"><span data-stu-id="d9bb3-117">Remarks</span></span>

<span data-ttu-id="d9bb3-118">对于 adjointable 操作，可以执行某些假设，如调用操作时，会将 qubits 的状态准备为完全相同的状态，从而使目标计算机能够进行某种性能优化。</span><span class="sxs-lookup"><span data-stu-id="d9bb3-118">For adjointable operations, certain assumptions can be made such like calling the operation will prepare the qubits to exactly the same state, which allow target machines to make some performance optimizations.</span></span>