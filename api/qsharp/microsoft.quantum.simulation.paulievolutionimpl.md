---
uid: Microsoft.Quantum.Simulation.PauliEvolutionImpl
title: PauliEvolutionImpl 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.

  See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 2fc9fda2dd6eec71d8b17ba8a00d8545e517eec8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696678"
---
# <a name="paulievolutionimpl-operation"></a>PauliEvolutionImpl 操作

命名空间 [：](xref:Microsoft.Quantum.Simulation)

软件包 [](https://nuget.org/packages/)


将 dynamical 生成器表示为一组 simulatable 入口和 Pauli 中的扩展。

有关更多详细信息，请参阅 [Dynamical 生成器建模](/quantum/libraries/data-structures#dynamical-generator-modeling) 。

```qsharp
operation PauliEvolutionImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, delta : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a>输入

### <a name="generatorindex--generatorindex"></a>generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

要在 Pauli 基础中表示为单一进化的生成器索引。


### <a name="delta--double"></a>delta： [Double](xref:microsoft.quantum.lang-ref.double)

中引用的术语在时间演变期间的乘数 `generatorIndex` 。


### <a name="qubits--qubit"></a>qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

根据时间演化运算符进行注册。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

