---
uid: Microsoft.Quantum.MachineLearning.PartialRotationsLayer
title: PartialRotationsLayer 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: PartialRotationsLayer
qsharp.summary: Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.
ms.openlocfilehash: ab964d2c43a13a5daf64aefdeccd1c26cd371ff4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700269"
---
# <a name="partialrotationslayer-function"></a><span data-ttu-id="41170-102">PartialRotationsLayer 函数</span><span class="sxs-lookup"><span data-stu-id="41170-102">PartialRotationsLayer function</span></span>

<span data-ttu-id="41170-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="41170-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="41170-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="41170-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="41170-105">返回沿给定轴旋转的 qubit 旋转数组，由不同的模型参数参数化。</span><span class="sxs-lookup"><span data-stu-id="41170-105">Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.</span></span>

```qsharp
function PartialRotationsLayer (idxsQubits : Int[], axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="41170-106">输入</span><span class="sxs-lookup"><span data-stu-id="41170-106">Input</span></span>

### <a name="idxsqubits--int"></a><span data-ttu-id="41170-107">idxsQubits： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="41170-107">idxsQubits : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="41170-108">要用作每个旋转目标的 qubits 的索引。</span><span class="sxs-lookup"><span data-stu-id="41170-108">Indices for the qubits to be used as the targets for each rotation.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="41170-109">轴： [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="41170-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="41170-110">给定层中每次旋转的旋转轴。</span><span class="sxs-lookup"><span data-stu-id="41170-110">The rotation axis for each rotation in the given layer.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="41170-111">Output： [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="41170-111">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="41170-112">有关给定轴的受控旋转数组，每个 qubits 上一个轴 `nQubits` 。</span><span class="sxs-lookup"><span data-stu-id="41170-112">An array of controlled rotations about the given axis, one on each of `nQubits` qubits.</span></span>