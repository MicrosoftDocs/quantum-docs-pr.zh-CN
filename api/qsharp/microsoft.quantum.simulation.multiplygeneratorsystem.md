---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: MultiplyGeneratorSystem 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: 1d28de99dab3f7aca4bf3706fe98f5ef7c5286a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696683"
---
# <a name="multiplygeneratorsystem-function"></a>MultiplyGeneratorSystem 函数

命名空间 [：](xref:Microsoft.Quantum.Simulation)

软件包 [](https://nuget.org/packages/)


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