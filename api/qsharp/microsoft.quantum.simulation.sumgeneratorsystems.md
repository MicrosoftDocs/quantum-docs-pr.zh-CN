---
uid: Microsoft.Quantum.Simulation.SumGeneratorSystems
title: SumGeneratorSystems 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SumGeneratorSystems
qsharp.summary: Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.
ms.openlocfilehash: b667a6af313b5bb8950a34a6d0406976bde49311
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696624"
---
# <a name="sumgeneratorsystems-function"></a>SumGeneratorSystems 函数

命名空间 [：](xref:Microsoft.Quantum.Simulation)

软件包 [](https://nuget.org/packages/)


添加多个 `GeneratorSystem` 创建新 GeneratorSystem 的。

```qsharp
function SumGeneratorSystems (generatorSystems : Microsoft.Quantum.Simulation.GeneratorSystem[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>输入

### <a name="generatorsystems--generatorsystem"></a>generatorSystems： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]

`GeneratorSystem[]` 类型的数组。



## <a name="output--generatorsystem"></a>输出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

一个， `GeneratorSystem` 它表示作为输入生成器系统的总和的系统。

## <a name="see-also"></a>另请参阅

- [GeneratorSystem。](xref:Microsoft.Quantum.Simulation.GeneratorSystem)