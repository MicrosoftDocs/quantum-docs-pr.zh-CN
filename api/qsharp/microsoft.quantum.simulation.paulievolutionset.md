---
uid: Microsoft.Quantum.Simulation.PauliEvolutionSet
title: PauliEvolutionSet 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: fb53b90b6ab5ce1003f66b68a8c2ad8b3631f627
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230338"
---
# <a name="paulievolutionset-function"></a>PauliEvolutionSet 函数

命名空间 [：](xref:Microsoft.Quantum.Simulation)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


将 dynamical 生成器表示为一组 simulatable 入口和 Pauli 中的扩展。

```qsharp
function PauliEvolutionSet () : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="output--evolutionset"></a>输出： [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)

一个 `EvolutionSet` ，它将 `GeneratorIndex` Pauli 基础的映射到 "EvolutionUnitary"。

## <a name="remarks"></a>备注

这是由的部分应用程序获取的 <xref:microsoft.quantum.simulation.paulievolutionfunction> 。