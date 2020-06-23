---
title: 量子模拟器和主机应用程序 | Microsoft Docs
description: 介绍如何使用经典计算 .NET 语言（通常为 C# 或 Q#）来驱动量子模拟器。
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines
ms.openlocfilehash: 14aed75ed0ed192f88699b1c7dbacfae23f74642
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273255"
---
# <a name="quantum-simulators-and-host-applications"></a>量子模拟器和主机应用程序

## <a name="what-youll-learn"></a>学习内容

> [!div class="checklist"]
> * 如何执行量子算法
> * 此版本中包括哪些量子模拟器
> * 如何为量子算法编写 C# 驱动程序

## <a name="the-quantum-development-kit-execution-model"></a>量子开发工具包执行模型

在[编写量子程序](xref:microsoft.quantum.write-program)时，我们通过将 `QuantumSimulator` 对象传递到算法类的 `Run` 方法来执行量子算法。
`QuantumSimulator` 类通过完全模拟量子状态向量来执行量子算法，这非常适合用于运行和测试 `Teleport`。
有关量子状态向量的详细信息，请参阅[概念指南](xref:microsoft.quantum.concepts.intro)。

其他目标计算机可用于运行量子算法。
计算机负责为算法提供量子基元的实现。
其中包括诸如 H、CNOT 和 Measure 等基元操作，以及量子位管理和跟踪。
不同类的量子机表示相同量子算法的不同执行模型。

每种类型的量子机可以提供这些基元的不同实现。
例如，开发工具包中包含的量子计算机跟踪模拟器根本不执行任何模拟。
而是跟踪算法的量子门、量子位和其他资源使用情况。

### <a name="quantum-machines"></a>量子机

将来，我们将定义其他量子机类以支持其他类型的模拟，并支持在拓扑量子计算机上执行。
在改变基础计算机实现的同时允许算法保持不变，可以轻松地在模拟中测试和调试算法，然后在实际硬件上运行该算法，确信该算法没有发生更改。

### <a name="whats-included-in-this-release"></a>此版本中包括的新增功能

此版本的量子开发人员工具包包含多个量子机类。
所有类在 `Microsoft.Quantum.Simulation.Simulators` 命名空间中定义。

* [完全状态向量模拟器](xref:microsoft.quantum.machines.full-state-simulator)，`QuantumSimulator` 类。
* [简单资源估算器](xref:microsoft.quantum.machines.resources-estimator)，`ResourcesEstimator` 类，它允许对运行量子算法所需的资源进行顶级分析。
* [基于跟踪的资源估算器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)，`QCTraceSimulator` 类，它允许对算法的整个调用关系图的资源消耗量进行高级分析。
* [Toffoli 模拟器](xref:microsoft.quantum.machines.toffoli-simulator)，`ToffoliSimulator` 类。

## <a name="writing-a-host-application"></a>编写主机应用程序

在[编写量子程序](xref:microsoft.quantum.write-program)时，我们为传送算法编写简单的 C# 驱动程序。 C# 驱动程序具有 4 个主要用途：

* 构造目标计算机
* 计算量子算法所需的任何参数
* 使用模拟器运行量子算法
* 处理操作结果

下面详细介绍每个步骤。

### <a name="constructing-the-target-machine"></a>构造目标计算机

量子机是普通 .NET 类的实例，因此它们是通过调用其构造函数来创建的，就像任何 .NET 类一样。
某些模拟器（包括 `QuantumSimulator`）实现 .NET <xref:System.IDisposable?displayProperty=nameWithType> 接口，因此应包装在 C# `using` 语句中。

### <a name="computing-arguments-for-the-algorithm"></a>计算算法的参数

在 `Teleport` 示例中，我们计算了要传递给量子算法的一些相对人工参数。
不过，通常情况下，量子算法需要大量数据，并且最简单的方法是从经典驱动程序提供数据。

例如，在执行化学模拟时，量子算法需要大量分子轨道交互积分。
通常，它们是在运行算法时提供的文件中读取的。
由于 Q# 没有访问文件系统的机制，因此此类数据最好由经典驱动程序收集，然后传递给量子算法的 `Run` 方法。

经典驱动程序起到重要作用的另一种情况是变分方法。
在此类算法中，将根据某些经典参数准备好量子状态，并且该状态用于计算感兴趣的某个值。
根据某种类型的爬山或机器学习算法调整参数，并再次运行量子算法。
对于此类算法，爬山算法本身最好以经典驱动程序调用的纯经典函数形式实现；然后将爬山的结果传递给量子算法的下一次执行。

### <a name="running-the-quantum-algorithm"></a>运行量子算法

此部分通常非常简单。
每个 Q# 操作都编译为提供静态 `Run` 方法的类。
此方法的参数由操作本身的平展参数元组以及附加的第一个参数（执行操作所用的模拟器）提供。 对于需要类型为 `(a: String, (b: Double, c: Double))` 的命名元组的操作，其平展对应类型为 `(String a, Double b, Double c)`。


向 `Run` 方法传递参数时，有一些细微问题：

* 数组必须包装在 `Microsoft.Quantum.Simulation.Core.QArray<T>` 对象中。
    `QArray` 类具有可采用相应对象的任何有序集合 (`IEnumerable<T>`) 的构造函数。
* 以 Q# 编写的空元组 `()` 由以 C# 编写的 `QVoid.Instance` 表示。
* 非空元组表示为 .NET `ValueTuple` 实例。
* Q# 用户定义的类型作为其基类型传递。
* 若要将操作或函数传递到 `Run` 方法，必须使用模拟器的 `Get<>` 方法获取操作或函数的类的实例。

### <a name="processing-the-results"></a>处理结果

从 `Run` 方法返回了量子算法的结果。
`Run` 方法以异步方式执行，因此它将返回 <xref:System.Threading.Tasks.Task`1> 的实例。
可以通过多种方法来获取实际操作的结果。 最简单的方法是使用 `Task` 的 [`Result` 属性](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result)：

```csharp
    var res = BellTest.Run(sim, 1000, initial).Result;
```
但其他方法（例如，使用 [`Wait` 方法](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait)或 C# [`await` 关键字](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await)）也将起作用。

与参数一样，Q# 元组表示为 `ValueTuple` 实例，Q# 数组表示为 `QArray` 实例。
用户定义的类型作为其基类型返回。
空元组 `()` 作为 `QVoid` 类的实例返回。

许多量子算法需要大量后续处理才能得出有用的答案。
例如，秀尔算法的量子部分只是找出数字因数的计算的开头。

在大多数情况下，这是在经典驱动程序中执行此类后续处理的最简单方法。
只有经典驱动程序才能向用户报告结果或将结果写入磁盘。
经典驱动程序将有权访问分析库和其他未在 Q# 中公开的数学函数。


## <a name="failures"></a>失败数

当在执行操作过程中到达 Q# `fail` 语句时，将引发 `ExecutionFailException`。

由于在 `Run` 方法中使用 `System.Task`，因此由 `fail` 语句引发的异常将包装到 `System.AggregateException` 中。
若要查找失败的实际原因，需要循环访问 `AggregateException` 
`InnerExceptions`，例如：

```csharp

            try
            {
                using(var sim = new QuantumSimulator())
                {
                    /// call your operations here...
                }
            }
            catch (AggregateException e)
            {
                // Unwrap AggregateException to get the message from Q# fail statement.
                // Go through all inner exceptions.
                foreach (Exception inner in e.InnerExceptions)
                {
                    // If the exception of type ExecutionFailException
                    if (inner is ExecutionFailException failException)
                    {
                        // Print the message it contains
                        Console.WriteLine($" {failException.Message}");
                    }
                }
            }
```

## <a name="other-classical-languages"></a>其他经典语言

虽然我们提供的示例采用 C#、F# 和 Python，但量子开发工具包也支持使用其他语言编写经典主机程序。
例如，如果你想要在 Visual Basic 中编写主机程序，[应该足以满足需要](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net)。
