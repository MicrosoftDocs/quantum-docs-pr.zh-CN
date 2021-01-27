---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: CombinedStructure 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: b8ec007202c8e63dc2e98d0c752f6ba1a453e236
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847418"
---
# <a name="combinedstructure-function"></a><span data-ttu-id="64a28-102">CombinedStructure 函数</span><span class="sxs-lookup"><span data-stu-id="64a28-102">CombinedStructure function</span></span>

<span data-ttu-id="64a28-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="64a28-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="64a28-104">Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="64a28-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="64a28-105">给定一个或多个受控旋转层时，将返回具有模型参数索引移动的单个层，以使不同的层由不同的模型参数参数化。</span><span class="sxs-lookup"><span data-stu-id="64a28-105">Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.</span></span>

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="64a28-106">输入</span><span class="sxs-lookup"><span data-stu-id="64a28-106">Input</span></span>

### <a name="layers--controlledrotation"></a><span data-ttu-id="64a28-107">层： [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []</span><span class="sxs-lookup"><span data-stu-id="64a28-107">layers : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[][]</span></span>

<span data-ttu-id="64a28-108">要组合的层。</span><span class="sxs-lookup"><span data-stu-id="64a28-108">The layers to be combined.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="64a28-109">Output： [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="64a28-109">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="64a28-110">一层受控旋转，表示所有其他层的串联。</span><span class="sxs-lookup"><span data-stu-id="64a28-110">A single layer of controlled rotations, representing the concatenation of all other layers.</span></span>

## <a name="example"></a><span data-ttu-id="64a28-111">示例</span><span class="sxs-lookup"><span data-stu-id="64a28-111">Example</span></span>

<span data-ttu-id="64a28-112">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="64a28-112">The following are equivalent:</span></span>

```qsharp
let structure = CombinedStructure([
    LocalRotationLayer(2, PauliY),
    CyclicEntanglingLayer(3, PauliX, 2)
]);
let structure = [
    ControlledRotation((0, new Int[0]), PauliY, 0),
    ControlledRotation((1, new Int[0]), PauliY, 1),
    ControlledRotation((0, [2]), PauliX, 2),
    ControlledRotation((1, [0]), PauliX, 3),
    ControlledRotation((2, [1]), PauliX, 4)
];
```