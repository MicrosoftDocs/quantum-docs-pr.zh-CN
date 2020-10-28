---
uid: Microsoft.Quantum.MachineLearning.LocalRotationsLayer
title: LocalRotationsLayer 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LocalRotationsLayer
qsharp.summary: Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.
ms.openlocfilehash: 8a3557f76d5d7a7b6375e5640cf6d11172cd38a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700565"
---
# <a name="localrotationslayer-function"></a><span data-ttu-id="19bbf-102">LocalRotationsLayer 函数</span><span class="sxs-lookup"><span data-stu-id="19bbf-102">LocalRotationsLayer function</span></span>

<span data-ttu-id="19bbf-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="19bbf-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="19bbf-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="19bbf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="19bbf-105">返回一组不受 (控制的 qubit) 沿给定轴旋转的数组，并在寄存器中的每个 qubit 之间进行一次旋转，由不同的模型参数参数化。</span><span class="sxs-lookup"><span data-stu-id="19bbf-105">Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.</span></span>

```qsharp
function LocalRotationsLayer (nQubits : Int, axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="19bbf-106">输入</span><span class="sxs-lookup"><span data-stu-id="19bbf-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="19bbf-107">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="19bbf-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="19bbf-108">给定层处理的 qubits 的数目。</span><span class="sxs-lookup"><span data-stu-id="19bbf-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="19bbf-109">轴： [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="19bbf-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="19bbf-110">给定层中每次旋转的旋转轴。</span><span class="sxs-lookup"><span data-stu-id="19bbf-110">The rotation axis for each rotation in the given layer.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="19bbf-111">Output： [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="19bbf-111">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="19bbf-112">有关给定轴的受控旋转数组，每个 qubits 上一个轴 `nQubits` 。</span><span class="sxs-lookup"><span data-stu-id="19bbf-112">An array of controlled rotations about the given axis, one on each of `nQubits` qubits.</span></span>