---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateEnergy
title: EstimateEnergy 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateEnergy
qsharp.summary: Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.
ms.openlocfilehash: 52e527a68818c80f93bc177d3563064fd0f2aea3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695708"
---
# <a name="estimateenergy-operation"></a><span data-ttu-id="bb8ab-102">EstimateEnergy 操作</span><span class="sxs-lookup"><span data-stu-id="bb8ab-102">EstimateEnergy operation</span></span>

<span data-ttu-id="bb8ab-103">命名空间： [JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="bb8ab-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="bb8ab-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bb8ab-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bb8ab-105">通过对单个 Jordan-Wigner 条款提供的能源求和，来估算分子的能源。</span><span class="sxs-lookup"><span data-stu-id="bb8ab-105">Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.</span></span>

```qsharp
operation EstimateEnergy (jwHamiltonian : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="bb8ab-106">说明</span><span class="sxs-lookup"><span data-stu-id="bb8ab-106">Description</span></span>

<span data-ttu-id="bb8ab-107">此操作隐式依赖于加速索引约定。</span><span class="sxs-lookup"><span data-stu-id="bb8ab-107">This operation implicitly relies on the spin up-down indexing convention.</span></span>

## <a name="input"></a><span data-ttu-id="bb8ab-108">输入</span><span class="sxs-lookup"><span data-stu-id="bb8ab-108">Input</span></span>

### <a name="jwhamiltonian--jordanwignerencodingdata"></a><span data-ttu-id="bb8ab-109">jwHamiltonian： [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="bb8ab-109">jwHamiltonian : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="bb8ab-110">Jordan-Wigner Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="bb8ab-110">The Jordan-Wigner Hamiltonian.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="bb8ab-111">nSamples： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bb8ab-111">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bb8ab-112">要用于预计字词预期的样本数。</span><span class="sxs-lookup"><span data-stu-id="bb8ab-112">The number of samples to use for the estimation of the term expectations.</span></span>



## <a name="output--double"></a><span data-ttu-id="bb8ab-113">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bb8ab-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="bb8ab-114">估计的分子能源</span><span class="sxs-lookup"><span data-stu-id="bb8ab-114">The estimated energy of the molecule</span></span>