---
uid: Microsoft.Quantum.Simulation.SumGeneratorSystems
title: SumGeneratorSystems 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SumGeneratorSystems
qsharp.summary: Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.
ms.openlocfilehash: 7cb18e161dce3a52d7c9a0bf6a45d4818db2b849
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192462"
---
# <a name="sumgeneratorsystems-function"></a>SumGeneratorSystems 函数

命名空间 [：](xref:Microsoft.Quantum.Simulation)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


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