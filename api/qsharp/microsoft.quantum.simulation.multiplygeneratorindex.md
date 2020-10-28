---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorIndex
title: MultiplyGeneratorIndex 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorIndex
qsharp.summary: Multiplies the coefficient in a `GeneratorIndex`.
ms.openlocfilehash: 9ee0568073b65b027cc98eb56934e9286b59c27f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700857"
---
# <a name="multiplygeneratorindex-function"></a>MultiplyGeneratorIndex 函数

命名空间 [：](xref:Microsoft.Quantum.Simulation)

软件包 [](https://nuget.org/packages/)


将中的系数相乘 `GeneratorIndex` 。

```qsharp
function MultiplyGeneratorIndex (multiplier : Double, generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>输入

### <a name="multiplier--double"></a>乘数： [Double](xref:microsoft.quantum.lang-ref.double)

系数的乘数。


### <a name="generatorindex--generatorindex"></a>generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

作为被乘数的 `GeneratorIndex`。



## <a name="output--generatorindex"></a>输出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

一个， `GeneratorIndex` 它表示一个系数大于系数的字词 `multiplier` 。

## <a name="see-also"></a>另请参阅

- [GeneratorIndex。](xref:Microsoft.Quantum.Simulation.GeneratorIndex)