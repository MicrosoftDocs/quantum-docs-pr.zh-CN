---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: CyclicEntanglingLayer 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 6e0f5057b35baefe2677126ba70ee4fddde7d4db
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696729"
---
# <a name="cyclicentanglinglayer-function"></a><span data-ttu-id="4b93f-102">CyclicEntanglingLayer 函数</span><span class="sxs-lookup"><span data-stu-id="4b93f-102">CyclicEntanglingLayer function</span></span>

<span data-ttu-id="4b93f-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="4b93f-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="4b93f-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4b93f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4b93f-105">返回沿给定轴进行了单独控制的旋转的数组，将循环排列在 qubits 的寄存器中，并通过不同的模型参数进行参数化。</span><span class="sxs-lookup"><span data-stu-id="4b93f-105">Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.</span></span>

```qsharp
function CyclicEntanglingLayer (nQubits : Int, axis : Pauli, stride : Int) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="4b93f-106">输入</span><span class="sxs-lookup"><span data-stu-id="4b93f-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="4b93f-107">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4b93f-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4b93f-108">给定层处理的 qubits 的数目。</span><span class="sxs-lookup"><span data-stu-id="4b93f-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="4b93f-109">轴： [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="4b93f-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="4b93f-110">给定层中每次旋转的旋转轴。</span><span class="sxs-lookup"><span data-stu-id="4b93f-110">The rotation axis for each rotation in the given layer.</span></span>


### <a name="stride--int"></a><span data-ttu-id="4b93f-111">步幅： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4b93f-111">stride : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4b93f-112">每个旋转的目标索引和控件索引之间的分隔。</span><span class="sxs-lookup"><span data-stu-id="4b93f-112">The separation between the target and control indices for each rotation.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="4b93f-113">Output： [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="4b93f-113">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="4b93f-114">跨 qubits 寄存器布局循环的由两个 qubit 控制的循环组成的数组 `nQubits` 。</span><span class="sxs-lookup"><span data-stu-id="4b93f-114">An array of two-qubit controlled rotations laid out cyclically across a register of `nQubits` qubits.</span></span>