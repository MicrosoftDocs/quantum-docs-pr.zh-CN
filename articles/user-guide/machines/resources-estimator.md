---
title: 量程资源估计器-量程开发工具包
description: 了解 Microsoft QDK resources 估计器，它估算 Q# 在量程计算机上运行某一给定操作实例所需的资源。
author: anpaz
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: c3aa94c8b34ad7247fbdeab4bf4dcb96ce746014
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847465"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a>量程开发工具包 (QDK) 资源估计器

顾名思义，类会估算在 `ResourcesEstimator` 量程计算机上运行某一给定操作实例所需的资源 Q# 。 它通过运行量程操作来实现此操作，而无需实际模拟量子计算机的状态;出于此原因，它会估算 Q# 使用上千个 qubits 的操作的资源，前提是代码的传统部分在合理的时间内运行。

资源估计器是在 [量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的基础上构建的，它提供了一组更丰富的指标和工具来帮助调试 Q# 程序。

## <a name="invoking-and-running-the-resources-estimator"></a>调用和运行资源估计器

可以使用资源估计器运行任何 Q# 操作。 有关更多详细信息，请参阅 [运行 Q# 程序的方法](xref:microsoft.quantum.guide.host-programs)。

### <a name="invoking-the-resources-estimator-from-c"></a>从 C 调用资源估计器# 

与使用其他目标计算机一样，你首先创建 `ResourcesEstimator` 类的实例，然后将其作为操作的 `Run` 方法的第一个参数传递。

请注意，与 `QuantumSimulator` 类不同，`ResourcesEstimator` 类不实现 <xref:System.IDisposable> 接口，因此不需要将其放在 `using` 语句中。

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

如示例所示， `ResourcesEstimator` 提供 `ToTSV()` 方法，该方法生成一个表，其中包含以制表符分隔的值 (TSV) 。 可以将表保存到文件或将其显示在控制台中进行分析。 下面是前述程序的示例输出：

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

使用导入的操作在 Python 库中使用 [estimate_resources ( # B1 ](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) 方法 Q# ：

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a>从命令行调用资源估计器

在 Q# 从命令行运行程序时，使用 **--模拟器** (或 **-s** 快捷) 参数来指定 `ResourcesEstimator` 目标计算机。 以下命令使用资源估计器运行程序： 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a>从 Juptyer 笔记本调用资源估计器

使用 I Q# 幻命令 [% 估算](xref:microsoft.quantum.iqsharp.magic-ref.simulate) 来运行 Q# 操作。

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a>以编程方式检索估计的数据

除了 TSV 表之外，还可以通过资源估计器的属性以编程方式检索在运行期间估计的资源 `Data` 。 `Data`属性提供一个 `System.DataTable` 具有两列的实例： `Metric` 和 `Sum` ，并按指标的名称编制索引。

下面的代码演示如何检索和打印操作所使用的的 `QubitClifford` 总数 `T` 和 `CNOT` 操作 Q# ：

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
|__CNOT__    |操作的运行计数 `CNOT` (也称为受控 Pauli X 操作) 。|
|__QubitClifford__ |任何单个 qubit Clifford 和 Pauli 操作的运行计数。|
|度量     |任何度量值的运行计数。  |
|__R__    |任何单 qubit 循环、不包括 `T` 、Clifford 和 Pauli 操作的运行计数。  |
|__T__    |操作的运行计数 `T` 及其词干，包括 `T` 操作、T_x = 1xt-hy-ubw 和 T_y = 1Xt-hy-ubw。。  |
|__Depth__|操作运行的量程线路的深度 Q# (参见 [下面](#depth-width-and-qubitcount)) 。 默认情况下，深度指标仅计算 `T` 入口。 有关更多详细信息，请参阅 [深度计数器](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)。   |
|__Width__|操作运行的量程线路的宽度 Q# (参见 [下面](#depth-width-and-qubitcount)) 。 默认情况下，深度指标仅计算 `T` 入口。 有关更多详细信息，请参阅 [Width Counter](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)。   |
|__QubitCount__    |运行操作期间分配的最大 qubits 数的下限 Q# 。 此指标可能不与 __深度__ 兼容 (请参阅下面) 。  |
|__BorrowedWidth__    |操作中借用的最大 qubits 数 Q# 。  |


## <a name="depth-width-and-qubitcount"></a>深度、宽度和 QubitCount

报告的深度和宽度估计值彼此兼容。
 (以前都可以使用这两个数字，但宽度和宽度需要不同的线路。 ) 当前这对中的这两个指标都可以同时通过相同的线路实现。

报告以下指标：

__深度：__ 对于根操作-执行此操作所用的时间（假定配置的入口时间）。
对于调用的操作或后续操作-在操作开始和结束时最新 qubit 可用性时间之间的时间差。

__宽度：__ 对于根操作-实际用于执行它的 qubits 的数目 (和操作，它将调用) 。
对于被调用的操作或后续操作，还使用了除操作开始时已使用的 qubits 以外还有多少 qubits。

请注意，重复使用 qubits 不会影响此数字。
例如，如果在操作 A 开始之前已释放几个 qubits，并且此操作要求的所有 qubit 都是通过重复使用以前的版本 qubits 满足的 (和从) 调用的操作，则将操作 A 的宽度报告为0。 成功的借用 qubits 不会影响宽度。

__QubitCount：__ 对于根操作-qubits 执行此 (操作所需的最小数量的和从其调用) 的操作。
对于被调用的操作或后续操作，为单独执行此操作所需的最小 qubits 数。 此数值不包括输入 qubits。 它包括借用 qubits。

支持两种操作模式。 通过设置 QCTraceSimulatorConfiguration 来选择模式。

__OptimizeDepth = false：__ 这是默认模式。 建议使用 QubitManager，以便在分配新的 qubits 之前重复使用已发布的。 对于根操作，" __宽度__ " 将成为 (下限) 的最小宽度。 系统会报告兼容 __深度__ ，可对其进行实现。 __QubitCount__ 将与根操作的 __宽度__ 相同，假设没有借款。

__OptimizeDepth = true：__ 不建议在执行和执行过程中执行 QubitManager，qubit 重复使用和基于启发式的优化进行 qubit。 对于根操作 __深度__ ，将成为下限)  (最小深度。 为此深度报告兼容的 __宽度__ (同时) 可以实现这两者。 若要优化宽度，程序中稍后遇到的入口可能计划在程序前面所遇到的关口之前，但 qubits 计划为在深度保持最少的情况下重复使用。 由于 qubits 基于时间值重用，因此建议将入口时间配置为整数值。 不保证 __宽度__ 是最佳的。 有关详细信息，请参阅跟踪的白皮书 [宽度和深度](https://github.com/microsoft/qsharp-runtime/tree/main/src/Simulation/Simulators/QCTraceSimulator/Docs)。

## <a name="providing-the-probability-of-measurement-outcomes"></a>提供测量结果的概率

您可以使用 <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> <xref:Microsoft.Quantum.Diagnostics> 命名空间中的来提供有关测量操作预期概率的信息。 有关详细信息，请参阅 [量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)

## <a name="see-also"></a>另请参阅

- [量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [量子 Toffoli 模拟器](xref:microsoft.quantum.machines.toffoli-simulator)
- [量子全状态模拟器](xref:microsoft.quantum.machines.full-state-simulator) 
