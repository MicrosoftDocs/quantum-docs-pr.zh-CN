---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithm
title: TrotterSimulationAlgorithm 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithm
qsharp.summary: '`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_.'
ms.openlocfilehash: c52acf293e69c78e7a82b0cf5d94de52d0f5a293
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696621"
---
# <a name="trottersimulationalgorithm-function"></a>TrotterSimulationAlgorithm 函数

命名空间 [：](xref:Microsoft.Quantum.Simulation)

软件包 [](https://nuget.org/packages/)


`SimulationAlgorithm` 使用 Trotter – Suzuki 分解来近似于时间演化运算符 _exp (-iHt)_ 的函数。

```qsharp
function TrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.SimulationAlgorithm
```


## <a name="input"></a>输入

### <a name="trotterstepsize--double"></a>trotterStepSize： [Double](xref:microsoft.quantum.lang-ref.double)

单个 Trotter 步骤中模拟时间演化的持续时间。


### <a name="trotterorder--int"></a>trotterOrder： [Int](xref:microsoft.quantum.lang-ref.int)

Trotter 集成器的顺序。 此值必须是1或偶数。



## <a name="output--simulationalgorithm"></a>输出： [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)

`SimulationAlgorithm` 类型。