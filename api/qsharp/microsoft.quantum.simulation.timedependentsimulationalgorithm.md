---
uid: Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
title: TimeDependentSimulationAlgorithm 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentSimulationAlgorithm
qsharp.summary: >-
  Represents a time-dependent simulation algorithm.

  A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule> to unitary time-evolution for some time-interval.
ms.openlocfilehash: b495a9fd96c78872f84e8f8183105f6290f70655
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192513"
---
# <a name="timedependentsimulationalgorithm-user-defined-type"></a>TimeDependentSimulationAlgorithm 用户定义的类型

命名空间 [：](xref:Microsoft.Quantum.Simulation)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


表示依赖时间的模拟算法。

依赖于时间的模拟技术将 <xref:microsoft.quantum.simulation.evolutionschedule>
用于某些时间间隔的单一时间演变。

```qsharp

newtype TimeDependentSimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionSchedule, Qubit[]) => Unit is Adj + Ctl));
```

