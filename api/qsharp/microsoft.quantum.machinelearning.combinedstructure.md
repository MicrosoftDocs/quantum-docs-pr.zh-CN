---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: CombinedStructure 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: fbfd87761a40abe350e5f955fb53d8024eeb614e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696730"
---
# <a name="combinedstructure-function"></a>CombinedStructure 函数

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

软件包 [](https://nuget.org/packages/)


给定一个或多个受控旋转层时，将返回具有模型参数索引移动的单个层，以使不同的层由不同的模型参数参数化。

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>输入

### <a name="layers--controlledrotation"></a>层： [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []

要组合的层。



## <a name="output--controlledrotation"></a>Output： [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

一层受控旋转，表示所有其他层的串联。