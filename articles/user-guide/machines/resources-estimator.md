---
title: 量程资源估计器-量程开发工具包
description: '了解 Microsoft QDK resources 估计器，它估算在量程计算机上运行 Q # 操作的给定实例所需的资源。'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 0909a050e89d6295664e54ab63cfda5d407a8f12
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870527"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a>量程开发工具包（QDK）资源估计器

顾名思义，类会估算在 `ResourcesEstimator` 量程计算机上运行 Q # 操作的给定实例所需的资源。 它通过执行量程操作来实现此操作，而无需实际模拟量子计算机的状态;出于此原因，它会估算使用上千个 qubits 的 Q # 操作的资源，前提是代码的传统部分在合理的时间内运行。

资源估计器是在[量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的基础上构建的，它提供了一组更丰富的指标和工具来帮助调试 Q # 程序。

## <a name="invoking-and-running-the-resources-estimator"></a>调用和运行资源估计器

可以使用资源估计器运行任何 Q # 操作。 有关更多详细信息，请参阅[运行 Q # 程序的方法](xref:microsoft.quantum.guide.host-programs)。

### <a name="invoking-the-resources-estimator-from-c"></a>从 C 调用资源估计器# 

与其他目标计算机一样，首先创建类的一个实例 `ResourceEstimator` ，然后将其作为操作的方法的第一个参数进行传递 `Run` 。

请注意，与类不同的是， `QuantumSimulator` `ResourceEstimator` 类并不实现 <xref:System.IDisposable> 接口，因此不需要将其包含在 `using` 语句中。

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();
            Console.WriteLine(estimator.ToTSV());
        }
    }
}
```

如示例所示， `ResourcesEstimator` 提供了 `ToTSV()` 方法，该方法生成一个包含制表符分隔值（TSV）的表。 可以将表保存到文件或将其显示在控制台中进行分析。 下面是前述程序的示例输出：

```output
Metric          Sum
CNOT            1000
QubitClifford   1000
R               0
Measure         4002
T               0
Depth           0
Width           2
BorrowedWidth   0
```

> [!NOTE]
> `ResourcesEstimator`实例不会在每次运行时重置其计算。 如果使用同一个实例运行另一个操作，则会将新结果与现有结果聚合在一起。 如果需要在运行之间重置计算，则为每次运行创建一个新的实例。

### <a name="invoking-the-resources-estimator-from-python"></a>从 Python 调用资源估计器

在导入的 Q # 操作中使用 Python 库中的[estimate_resources （）](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable)方法：

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a>从命令行调用资源估计器

从命令行运行 Q # 程序时，使用 **--模拟器**（或 **-s**快捷方式）参数指定 `ResourcesEstimator` 目标计算机。 以下命令使用资源估计器运行程序： 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a>从 Juptyer 笔记本调用资源估计器

使用 IQ # 幻命令[% 估算](xref:microsoft.quantum.iqsharp.magic-ref.simulate)运行 Q # 操作。

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a>以编程方式检索估计的数据

除了 TSV 表之外，还可以通过资源估计器的属性以编程方式检索在运行期间估计的资源 `Data` 。 `Data`属性提供一个 `System.DataTable` 具有两列的实例： `Metric` 和 `Sum` ，并按指标的名称编制索引。

下面的代码演示如何检索和打印 `QubitClifford` `T` `CNOT` Q # 操作使用的和操作的总数：

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();

            var data = estimator.Data;
            Console.WriteLine($"QubitCliffords: {data.Rows.Find("QubitClifford")["Sum"]}");
            Console.WriteLine($"Ts: {data.Rows.Find("T")["Sum"]}");
            Console.WriteLine($"CNOTs: {data.Rows.Find("CNOT")["Sum"]}");
        }
    }
}
```

## <a name="metrics-reported"></a>报告的指标

资源估计器跟踪以下度量值：

|指标|说明|
|----|----|
|__CNOT__    |操作的运行计数 `CNOT` （也称为受控 Pauli X 操作）。|
|__QubitClifford__ |任何单个 qubit Clifford 和 Pauli 操作的运行计数。|
|度量     |任何度量值的运行计数。  |
|__R__    |任何单 qubit 循环、不包括 `T` 、Clifford 和 Pauli 操作的运行计数。  |
|__T__    |操作的运行计数 `T` 及其词干，包括 `T` 操作、T_x = 1xt-hy-ubw 和 T_y = 1Xt-hy-ubw。。  |
|__Depth__|由 Q # 操作运行的量程线路深度的下限。 默认情况下，深度指标仅计算 `T` 入口。 有关更多详细信息，请参阅[深度计数器](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)。   |
|__Width__    |在运行 Q # 操作期间分配的最大 qubits 数的下限。 可能无法同时实现__深度__和__宽度__下限。  |
|__BorrowedWidth__    |Q # 操作内借用的最大 qubits 数。  |

## <a name="providing-the-probability-of-measurement-outcomes"></a>提供测量结果的概率

您可以使用 <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> <xref:microsoft.quantum.diagnostics> 命名空间中的来提供有关测量操作预期概率的信息。 有关详细信息，请参阅[量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)

## <a name="see-also"></a>另请参阅

- [量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [量程 Toffoli 模拟器](xref:microsoft.quantum.machines.toffoli-simulator)
- [量程完全状态模拟器](xref:microsoft.quantum.machines.full-state-simulator) 