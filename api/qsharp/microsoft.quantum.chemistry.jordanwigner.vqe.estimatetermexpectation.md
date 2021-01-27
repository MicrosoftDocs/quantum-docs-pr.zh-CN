---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: EstimateTermExpectation 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: 7df4c1ea859140a669698434c6f8a786ea3bc2ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835670"
---
# <a name="estimatetermexpectation-operation"></a><span data-ttu-id="7fdb9-102">EstimateTermExpectation 操作</span><span class="sxs-lookup"><span data-stu-id="7fdb9-102">EstimateTermExpectation operation</span></span>

<span data-ttu-id="7fdb9-103">命名空间： [JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="7fdb9-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="7fdb9-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="7fdb9-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="7fdb9-105">计算与给定 Jordan-Wigner Hamiltonian 术语关联的能量</span><span class="sxs-lookup"><span data-stu-id="7fdb9-105">Computes the energy associated to a given Jordan-Wigner Hamiltonian term</span></span>

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="7fdb9-106">说明</span><span class="sxs-lookup"><span data-stu-id="7fdb9-106">Description</span></span>

<span data-ttu-id="7fdb9-107">此操作估算与每个度量运算符关联的预期值，并使用采样将其与相应的系数相乘。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-107">This operation estimates the expectation value associated to each measurement operator and multiplies it by the corresponding coefficient, using sampling.</span></span>
<span data-ttu-id="7fdb9-108">结果聚合到一个变量中，该变量包含 Jordan-Wigner 术语的能量。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-108">The results are aggregated into a variable containing the energy of the Jordan-Wigner term.</span></span>

## <a name="input"></a><span data-ttu-id="7fdb9-109">输入</span><span class="sxs-lookup"><span data-stu-id="7fdb9-109">Input</span></span>

### <a name="inputstateunitary--qubit--unit--is-adj"></a><span data-ttu-id="7fdb9-110">inputStateUnitary： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="7fdb9-110">inputStateUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="7fdb9-111">用于状态准备的单一。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-111">The unitary used for state preparation.</span></span>


### <a name="ops--pauli"></a><span data-ttu-id="7fdb9-112">ops： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="7fdb9-112">ops : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="7fdb9-113">Jordan-Wigner 术语的度量运算符。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-113">The measurement operators of the Jordan-Wigner term.</span></span>


### <a name="coeffs--double"></a><span data-ttu-id="7fdb9-114">coeffs： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="7fdb9-114">coeffs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="7fdb9-115">Jordan-Wigner 项的系数。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-115">The coefficients of the Jordan-Wigner term.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="7fdb9-116">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7fdb9-116">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7fdb9-117">模拟分子系统所需的 qubits 数。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-117">The number of qubits required to simulate the molecular system.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="7fdb9-118">nSamples： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7fdb9-118">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7fdb9-119">要用于预计字词预计的样本数。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-119">The number of samples to use for the estimation of the term expectation.</span></span>



## <a name="output--double"></a><span data-ttu-id="7fdb9-120">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7fdb9-120">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7fdb9-121">与 Jordan-Wigner 术语关联的能量。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-121">The energy associated to the Jordan-Wigner term.</span></span>