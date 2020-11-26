---
uid: Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
title: TimeDependentGeneratorSystem 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentGeneratorSystem
qsharp.summary: Represents a time-dependent dynamical generator as a function from time to the value of the dynamical generator at that time.
ms.openlocfilehash: b9b11a5850cbf9bc0b908f1644443611e91bb258
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192445"
---
# <a name="timedependentgeneratorsystem-user-defined-type"></a>TimeDependentGeneratorSystem 用户定义的类型

命名空间 [：](xref:Microsoft.Quantum.Simulation)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


表示时间依赖于时间的 dynamical 生成器作为函数，时间与 dynamical 生成器的值相同。

```qsharp

newtype TimeDependentGeneratorSystem = ((Double -> Microsoft.Quantum.Simulation.GeneratorSystem));
```

