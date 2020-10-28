---
uid: Microsoft.Quantum.Simulation.PauliEvolutionSet
title: PauliEvolutionSet 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 89c81aca4cfad6087d764ac8f5a0f1426e905e4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700160"
---
# <a name="paulievolutionset-function"></a>PauliEvolutionSet 函数

命名空间 [：](xref:Microsoft.Quantum.Simulation)

软件包 [](https://nuget.org/packages/)


将 dynamical 生成器表示为一组 simulatable 入口和 Pauli 中的扩展。

```qsharp
function PauliEvolutionSet () : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="output--evolutionset"></a>输出： [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)

一个 `EvolutionSet` ，它将 `GeneratorIndex` Pauli 基础的映射到 "EvolutionUnitary"。

## <a name="remarks"></a>注解

这是由的部分应用程序获取的 <xref:microsoft.quantum.simulation.paulievolutionfunction> 。