---
uid: Microsoft.Quantum.MachineLearning.LocalRotationsLayer
title: LocalRotationsLayer 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LocalRotationsLayer
qsharp.summary: Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.
ms.openlocfilehash: a3658bbf62068c9eea2d9b763cbff5596f426135
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854979"
---
# <a name="localrotationslayer-function"></a><span data-ttu-id="4e81f-102">LocalRotationsLayer 函数</span><span class="sxs-lookup"><span data-stu-id="4e81f-102">LocalRotationsLayer function</span></span>

<span data-ttu-id="4e81f-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="4e81f-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="4e81f-104">Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="4e81f-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="4e81f-105">返回一组不受 (控制的 qubit) 沿给定轴旋转的数组，并在寄存器中的每个 qubit 之间进行一次旋转，由不同的模型参数参数化。</span><span class="sxs-lookup"><span data-stu-id="4e81f-105">Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.</span></span>

```qsharp
function LocalRotationsLayer (nQubits : Int, axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="4e81f-106">输入</span><span class="sxs-lookup"><span data-stu-id="4e81f-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="4e81f-107">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4e81f-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4e81f-108">给定层处理的 qubits 的数目。</span><span class="sxs-lookup"><span data-stu-id="4e81f-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="4e81f-109">轴： [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="4e81f-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="4e81f-110">给定层中每次旋转的旋转轴。</span><span class="sxs-lookup"><span data-stu-id="4e81f-110">The rotation axis for each rotation in the given layer.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="4e81f-111">Output： [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="4e81f-111">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="4e81f-112">有关给定轴的受控旋转数组，每个 qubits 上一个轴 `nQubits` 。</span><span class="sxs-lookup"><span data-stu-id="4e81f-112">An array of controlled rotations about the given axis, one on each of `nQubits` qubits.</span></span>