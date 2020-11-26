---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: CombinedStructure 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: 0a7d66be8b45d6a9df95b425e66b9b6bba241136
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211961"
---
# <a name="combinedstructure-function"></a><span data-ttu-id="d495e-102">CombinedStructure 函数</span><span class="sxs-lookup"><span data-stu-id="d495e-102">CombinedStructure function</span></span>

<span data-ttu-id="d495e-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d495e-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="d495e-104">Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d495e-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="d495e-105">给定一个或多个受控旋转层时，将返回具有模型参数索引移动的单个层，以使不同的层由不同的模型参数参数化。</span><span class="sxs-lookup"><span data-stu-id="d495e-105">Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.</span></span>

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="d495e-106">输入</span><span class="sxs-lookup"><span data-stu-id="d495e-106">Input</span></span>

### <a name="layers--controlledrotation"></a><span data-ttu-id="d495e-107">层： [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []</span><span class="sxs-lookup"><span data-stu-id="d495e-107">layers : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[][]</span></span>

<span data-ttu-id="d495e-108">要组合的层。</span><span class="sxs-lookup"><span data-stu-id="d495e-108">The layers to be combined.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="d495e-109">Output： [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="d495e-109">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="d495e-110">一层受控旋转，表示所有其他层的串联。</span><span class="sxs-lookup"><span data-stu-id="d495e-110">A single layer of controlled rotations, representing the concatenation of all other layers.</span></span>