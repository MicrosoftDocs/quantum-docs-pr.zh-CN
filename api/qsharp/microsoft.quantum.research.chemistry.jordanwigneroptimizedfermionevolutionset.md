---
uid: Microsoft.Quantum.Research.Chemistry.JordanWignerOptimizedFermionEvolutionSet
title: JordanWignerOptimizedFermionEvolutionSet 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JordanWignerOptimizedFermionEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 941d66a936ef1a2ac76230d14ca8437ac2a4a049
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857888"
---
# <a name="jordanwigneroptimizedfermionevolutionset-function"></a>JordanWignerOptimizedFermionEvolutionSet 函数

命名空间： [...](xref:Microsoft.Quantum.Research.Chemistry)

包： [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)


将 dynamical 生成器表示为一组 simulatable 入口和 Pauli 中的扩展。

```qsharp
function JordanWignerOptimizedFermionEvolutionSet (parityQubit : Qubit) : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="input"></a>输入

### <a name="parityqubit--qubit"></a>parityQubit： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit，用于确定时间演化的符号。



## <a name="output--evolutionset"></a>输出： [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)

一个 `EvolutionSet` ，它将 `GeneratorIndex` JWOptimized 基础的映射到 "EvolutionUnitary"。