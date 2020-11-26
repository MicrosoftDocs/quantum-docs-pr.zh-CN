---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: MultiplyGeneratorSystem 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: effb9e3ca754f77bbe1ea0fb6ca30ae49e92d531
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229148"
---
# <a name="multiplygeneratorsystem-function"></a>MultiplyGeneratorSystem 函数

命名空间 [：](xref:Microsoft.Quantum.Simulation)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


将中所有字词的系数相乘 `GeneratorSystem` 。

```qsharp
function MultiplyGeneratorSystem (multiplier : Double, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>输入

### <a name="multiplier--double"></a>乘数： [Double](xref:microsoft.quantum.lang-ref.double)

系数的乘数。


### <a name="generatorsystem--generatorsystem"></a>generatorSystem： [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

作为被乘数的 `GeneratorSystem`。



## <a name="output--generatorsystem"></a>输出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

， `GeneratorSystem` 它表示系数大于系数的系统 `multiplier` 。

## <a name="see-also"></a>另请参阅

- [GeneratorSystem。](xref:Microsoft.Quantum.Simulation.GeneratorSystem)