---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: EstimateTermExpectation 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: ef689c55f966e63a2ab8bcdccf99d9cb5e6d3a4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695705"
---
# <a name="estimatetermexpectation-operation"></a><span data-ttu-id="d7cff-102">EstimateTermExpectation 操作</span><span class="sxs-lookup"><span data-stu-id="d7cff-102">EstimateTermExpectation operation</span></span>

<span data-ttu-id="d7cff-103">命名空间： [JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="d7cff-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="d7cff-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d7cff-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d7cff-105">计算与给定 Jordan-Wigner Hamiltonian 术语关联的能量</span><span class="sxs-lookup"><span data-stu-id="d7cff-105">Computes the energy associated to a given Jordan-Wigner Hamiltonian term</span></span>

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="d7cff-106">说明</span><span class="sxs-lookup"><span data-stu-id="d7cff-106">Description</span></span>

<span data-ttu-id="d7cff-107">此操作估算与每个度量运算符关联的预期值，并使用采样将其与相应的系数相乘。</span><span class="sxs-lookup"><span data-stu-id="d7cff-107">This operation estimates the expectation value associated to each measurement operator and multiplies it by the corresponding coefficient, using sampling.</span></span>
<span data-ttu-id="d7cff-108">结果聚合到一个变量中，该变量包含 Jordan-Wigner 术语的能量。</span><span class="sxs-lookup"><span data-stu-id="d7cff-108">The results are aggregated into a variable containing the energy of the Jordan-Wigner term.</span></span>

## <a name="input"></a><span data-ttu-id="d7cff-109">输入</span><span class="sxs-lookup"><span data-stu-id="d7cff-109">Input</span></span>

### <a name="inputstateunitary--qubit--unit-adj"></a><span data-ttu-id="d7cff-110">inputStateUnitary： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="d7cff-110">inputStateUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="d7cff-111">用于状态准备的单一。</span><span class="sxs-lookup"><span data-stu-id="d7cff-111">The unitary used for state preparation.</span></span>


### <a name="ops--pauli"></a><span data-ttu-id="d7cff-112">ops： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="d7cff-112">ops : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="d7cff-113">Jordan-Wigner 术语的度量运算符。</span><span class="sxs-lookup"><span data-stu-id="d7cff-113">The measurement operators of the Jordan-Wigner term.</span></span>


### <a name="coeffs--double"></a><span data-ttu-id="d7cff-114">coeffs： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="d7cff-114">coeffs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="d7cff-115">Jordan-Wigner 项的系数。</span><span class="sxs-lookup"><span data-stu-id="d7cff-115">The coefficients of the Jordan-Wigner term.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="d7cff-116">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d7cff-116">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d7cff-117">模拟分子系统所需的 qubits 数。</span><span class="sxs-lookup"><span data-stu-id="d7cff-117">The number of qubits required to simulate the molecular system.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="d7cff-118">nSamples： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d7cff-118">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d7cff-119">要用于预计字词预计的样本数。</span><span class="sxs-lookup"><span data-stu-id="d7cff-119">The number of samples to use for the estimation of the term expectation.</span></span>



## <a name="output--double"></a><span data-ttu-id="d7cff-120">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d7cff-120">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d7cff-121">与 Jordan-Wigner 术语关联的能量。</span><span class="sxs-lookup"><span data-stu-id="d7cff-121">The energy associated to the Jordan-Wigner term.</span></span>