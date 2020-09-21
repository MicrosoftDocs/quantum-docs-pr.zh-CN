---
title: 完整状态量程模拟器-量程开发工具包
description: 了解如何 Q# 在 Microsoft Quantum Development Kit 完全状态模拟器上运行你的程序。
author: anpaz-msft
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 632af681c5818ab7246c0f5849a8b8e716b570cb
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833376"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a>量程开发工具包 (QDK) 完整状态模拟器

QDK 提供了模拟本地计算机上的量子计算机的完整状态模拟器。 可以使用完整状态模拟器来运行和调试用编写的量程算法 Q# ，最多可利用30个 qubits。 完整状态模拟器类似于 Microsoft Research 的  [LIQ $ Ui | \rangle $](http://stationq.github.io/Liquid/) 平台中使用的量程模拟器。

## <a name="invoking-and-running-the-full-state-simulator"></a>调用并运行完全状态模拟器

通过类公开完整状态模拟器 `QuantumSimulator` 。 有关更多详细信息，请参阅 [运行 Q# 程序的方法](xref:microsoft.quantum.guide.host-programs)。

### <a name="invoking-the-simulator-from-c"></a>从 C 调用模拟器#

创建类的实例， `QuantumSimulator` 然后将其传递给 `Run` 量程操作的方法以及任何其他参数。
```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

由于 `QuantumSimulator` 类实现 <xref:System.IDisposable> 接口，因此，一旦不再需要模拟器的实例，就必须调用 `Dispose` 方法。 执行此操作的最佳方法是在 [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) 语句中包装模拟器声明和操作，这会自动调用 `Dispose` 方法。

### <a name="invoking-the-simulator-from-python"></a>从 Python 调用模拟器

使用导入的操作从 Python 库中 [模拟 ( # B1 ](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) 方法 Q# Q# ：

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a>从命令行调用模拟器

在 Q# 从命令行运行程序时，完全状态模拟器是默认的目标计算机。 （可选）可以使用 **--模拟器** (或 **-s** 快捷键) 参数指定所需的目标计算机。 以下两个命令都使用完整状态模拟器运行程序。 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a>从 Juptyer 笔记本调用模拟器

使用 "我的 Q# 神奇命令 [% 模拟](xref:microsoft.quantum.iqsharp.magic-ref.simulate) " 运行 Q# 操作。

```
%simulate myOperation
```
## <a name="seeding-the-simulator"></a>播种模拟器

默认情况下，完整状态模拟器使用随机数生成器来模拟量程随机性。 出于测试目的，具有确定性的结果有时会很有用。 在 c # 程序中，可以通过参数在构造函数中提供随机数生成器的种子，来实现此目的 `QuantumSimulator` `randomNumberGeneratorSeed` 。

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="configuring-threads"></a>配置线程

完整状态模拟器使用 [OpenMP](http://www.openmp.org/) 对所需的线性代数进行并行化。 默认情况下，OpenMP 使用所有可用的硬件线程，这意味着具有少量 qubits 的程序通常会运行缓慢，因为需要 dwarfs 实际工作。 可以通过将环境变量设置 `OMP_NUM_THREADS` 为小数值来解决此问题。 根据经验法则，为一个线程配置最多四个 qubits，然后为每个 qubit 配置一个其他线程。 你可能需要根据你的算法调整此变量。

## <a name="see-also"></a>另请参阅

- [量子资源估算器](xref:microsoft.quantum.machines.resources-estimator)
- [量子 Toffoli 模拟器](xref:microsoft.quantum.machines.toffoli-simulator)
- [量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)