---
title: 完整状态模拟器
description: '了解如何在 Microsoft Quantum Development Kit 完全状态模拟器上运行 Q # 程序。'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: f73abbc4366b003e4b22366ed83ca9c897737307
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906111"
---
# <a name="quantum-development-kit-full-state-simulator"></a>量程开发工具包完整状态模拟器

量程开发工具包提供了一个完整的状态量程模拟器，类似于 Microsoft Research 的[LIQ $ Ui | \rangle $](http://stationq.github.io/Liquid/) 。
此模拟器可用于执行和调试在计算机上用 Q # 编写的量程算法。

此量程模拟器通过 `QuantumSimulator` 类公开。 若要使用模拟器，只需创建此类的一个实例，并将其传递给要执行的量程操作的 `Run` 方法，同时执行其余的参数：

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a>IDisposable

`QuantumSimulator` 类实现 <xref:System.IDisposable>，因此，在不再使用模拟器的实例后，应调用 `Dispose` 方法。 实现此目的的最佳方式是在 `using` 语句中包装模拟器，如以上示例中所示。

## <a name="seed"></a>Seed

`QuantumSimulator` 使用随机数生成器来模拟量子随机性。 出于测试目的，具有确定性的结果有时会很有用。 为此，可以通过 `randomNumberGeneratorSeed` 参数在 `QuantumSimulator`的构造函数中提供随机数生成器的种子：

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a>线程

`QuantumSimulator` 使用[OpenMP](http://www.openmp.org/)对所需的线性代数进行并行化。 OpenMP 默认使用所有可用的硬件线程，这意味着具有少量的量子位的程序通常运行缓慢，因为所需的协调远多于实际工作。 为此，可以将环境变量 `OMP_NUM_THREADS` 设置为一个较小的数字。 作为非常粗略的经验法则，1 个线程最多可以容纳约 4 个量子位，然后每个量子位最好增加一个线程，但这在很大程度上取决于你的算法。

