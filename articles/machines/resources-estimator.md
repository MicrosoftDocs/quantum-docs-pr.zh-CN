---
title: 量程开发工具包资源估计器
description: '了解资源估计器，这些资源估计在量程计算机上运行 Q # 操作的给定实例所需的资源。'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 01d242ed405bdd326f65e534f82ff378a464ee7d
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426877"
---
# <a name="the-resources-estimator-target-machine"></a>资源估计器目标计算机

顾名思义， `ResourcesEstimator` 估计在量程计算机上运行 Q # 操作的给定实例所需的资源。
它通过执行量程操作来实现此操作，而无需实际模拟量子计算机的状态;出于此原因，如果代码的传统部分可以在合理的时间内运行，则它可以估计使用上千个 qubits 的 Q # 操作的资源。

## <a name="usage"></a>使用情况

`ResourcesEstimator`只是另一种类型的目标计算机，因此它可用于运行任何 Q # 操作。 

作为其他目标计算机，若要在 c # 主机程序上使用该实例，请创建一个实例，并将其作为该操作方法的第一个参数进行传递 `Run` ：

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

如示例所示， `ResourcesEstimator` 提供了一个 `ToTSV()` 方法，该方法生成一个包含制表符分隔值（TSV）的表，该表可以保存到文件中或写入控制台进行分析。 上述程序的输出应如下所示：

```Output
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
> `ResourcesEstimator`不会在每次运行时重置其计算，如果使用同一个实例执行其他操作，它将使聚合计数保持在现有结果的顶部。
> 如果需要在运行之间重置计算，则为每次执行创建一个新的实例。


## <a name="programmatically-retrieving-the-estimated-data"></a>以编程方式检索估计的数据

除了 TSV 表之外，还可以通过的属性以编程方式检索资源估算 `ResourcesEstimator` `Data` 。 `Data`提供一个 `System.DataTable` 具有两列的实例： `Metric` 和 `Sum` ，并按指标名称进行索引。

下面的代码演示如何检索和打印 `QubitClifford` `T` `CNOT` Q # 操作使用的和入口总数：

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

下面是估计的指标列表 `ResourcesEstimator` ：

* __Cnot-contains__：已执行的 cnot-contains （也称为受控 Pauli X 入口）入口的计数。
* __QubitClifford__：执行的任何单个 qubit Clifford 和 Pauli 入口的计数。
* __度量值__：执行的任何度量值的计数。
* __R__：执行的任何单个 qubit 循环的计数，不包括 T、Clifford 和 Pauli 入口。
* __T__： t 入口及其词干的计数（包括 t 入口、T_x = 1xt-hy-ubw）和 T_y = 1xt-hy-ubw，已执行。
* __深度__：由 Q # 操作执行的量程线路的深度。 默认情况下，在深度中只对 T 个入口计数，有关详细信息，请参阅[深度计数器](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)。
* __Width__：在执行 Q # 操作期间分配的最大 qubits 数。
* __BorrowedWidth__： Q # 操作内借用的最大 qubits 数。


## <a name="providing-the-probability-of-measurement-outcomes"></a>提供度量结果的概率

<xref:microsoft.quantum.intrinsic.assertprob><xref:microsoft.quantum.intrinsic>可以使用命名空间中的信息来提供有关测量结果的信息，以帮助推动 Q # 计划的执行。 以下示例对此进行了说明：

```qsharp
operation Teleport(source : Qubit, target : Qubit) : Unit {

    using (qubit = Qubit()) {

        H(q);
        CNOT(qubit, target);

        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [qubit], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(qubit) == One) { X(target); X(qubit); }
    }
}
```

当遇到此情况时， `ResourcesEstimator` `AssertProb` 它将记录对的度量， `PauliZ` `source` 并 `q` 应为其给定结果 `Zero` ，其概率为0.5。 当它稍后执行时 `M` ，它将查找结果概率的已记录值，并 `M` 返回 `Zero` `One` 概率为0.5 的或。


## <a name="see-also"></a>另请参阅

在 `ResourcesEstimator` 量程计算机[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的基础上构建，它提供了一组更丰富的指标，可以在完整的调用关系图上报告指标，还可以使用[不同的输入检查器](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)来帮助查找 Q # 计划中的 bug。 有关详细信息，请参阅[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)文档。

