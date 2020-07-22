---
title: 量程 Toffoli 模拟器-量程开发工具包
description: 了解 Microsoft QDK Toffoli 模拟器，它是一种特殊用途的量程模拟器，可与数百万 qubits 一起使用。
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 6/25/2020
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: a6ceee592e628215511ec83475d9e25bf54674f7
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870611"
---
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a>量程开发工具包（QDK） Toffoli 模拟器

QDK Toffoli 模拟器是一种特殊用途的模拟器，其作用域有限，只支持 `X` 、 `CNOT` 和多受控 `X` 量程操作。 所有传统逻辑和计算都可用。

尽管 Toffoli 模拟器比[完整状态模拟器](xref:microsoft.quantum.machines.full-state-simulator)更受限制，但它的优势是能够模拟更多 qubits。 Toffoli 模拟器可用于数百万 qubits，而完整状态模拟器仅限约 30 qubits。 这很有用，例如，使用 oracles 来计算布尔函数，它们可以使用有限的一组受支持的算法来实现，并在大量 qubits 上测试。

## <a name="invoking-the-toffoli-simulator"></a>调用 Toffoli 模拟器

通过类公开 Toffoli 模拟器 `ToffoliSimulator` 。 有关更多详细信息，请参阅[运行 Q # 程序的方法](xref:microsoft.quantum.guide.host-programs)。

### <a name="invoking-the-toffoli-simulator-from-c"></a>从 C 调用 Toffoli 模拟器#

与其他目标计算机一样，首先创建类的一个实例 `ToffoliSimulator` ，然后将其作为操作的方法的第一个参数进行传递 `Run` 。

请注意，与类不同的是， `QuantumSimulator` `ToffoliSimulator` 类并不实现 <xref:System.IDisposable> 接口，因此不需要将其包含在 `using` 语句中。

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a>从 Python 调用 Toffoli 模拟器

在导入的 Q # 操作中使用 Python 库中的[toffoli_simulate （）](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable)方法：

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a>从命令行调用 Toffoli 模拟器

从命令行运行 Q # 程序时，使用 **--模拟器**（或 **-s**快捷方式）参数指定 Toffoli 模拟器目标计算机。 以下命令使用资源估计器运行程序： 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a>从 Juptyer 笔记本调用 Toffoli 模拟器

使用 IQ # 幻命令[% toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli)运行 Q # 操作。

```
%toffoli myOperation
```

## <a name="supported-operations"></a>支持的操作

Toffoli 模拟器支持：

* `R` `Exp` 当结果操作等于或标识矩阵时，旋转和指数化 Paulis （如和） `X` 。
* 度量和[断言](xref:microsoft.quantum.diagnostics.assertmeasurement)操作，但仅在 Pauli `Z` 基础中。 请注意，度量操作的概率始终为**0**或**1**;Toffoli 模拟器中没有随机性。
* `DumpMachine`和 `DumpRegister` 函数。
这两个函数输出 `Z` 每个 qubit 的当前基础状态，每行一个 qubit。

## <a name="specifying-the-number-of-qubits"></a>指定 qubits 数

默认情况下， `ToffoliSimulator` 实例为 65536 qubits 分配空间。
如果你的算法需要比此更多的 qubits，则可以通过向构造函数提供参数的值来指定 qubit 计数 `qubitCount` 。
每个额外的 qubit 只需要一个字节的内存，因此估计过高的 qubits 数量不会产生很大的代价。

例如：

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

## <a name="see-also"></a>另请参阅

- [量程资源估计器](xref:microsoft.quantum.machines.resources-estimator)
- [量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [量程完全状态模拟器](xref:microsoft.quantum.machines.full-state-simulator) 