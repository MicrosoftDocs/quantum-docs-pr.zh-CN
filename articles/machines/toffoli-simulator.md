---
title: 量程开发工具包 Toffoli 模拟器
description: 了解 Microsoft QDK Toffoli 模拟器，它是一种特殊用途的量程模拟器，可与数百万 qubits 一起使用。
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 8a29caaa0fa058600a74e7d130e644374cbfa19c
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907012"
---
# <a name="quantum-development-kit-toffoli-simulator"></a>量程开发工具包 Toffoli 模拟器

量程开发工具包提供了一个 Toffoli 模拟器，它是一种特殊用途的模拟器，可以模拟限制为 X、CNOT-CONTAINS 和多受控 X 量程操作的量程算法（所有传统逻辑和计算都可用）。

尽管 Toffoli 模拟器比[完整状态模拟器](xref:microsoft.quantum.machines.full-state-simulator)的操作受到限制更多，但它可以模拟更多 qubits。
Toffoli 模拟器可用于数百万 qubits，而完整状态模拟器一般限制为大约30。
它可以执行和调试在计算机上用 Q # 编写的有限的一组量程算法;例如，可以使用这些入口来实现计算布尔函数的 oracles，因此在上经过测试的可以使用此模拟器改变大量 qubits。

此量程模拟器通过 `ToffoliSimulator` 类公开。
若要使用模拟器，只需创建此类的一个实例，并将其传递给要执行的量程操作的 `Run` 方法，同时执行其余的参数：

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a>其他操作

当结果操作等于 `X` 或标识时，`ToffoliSimulator` 支持旋转和指数化 Paulis，如 `R` 和 `Exp`。

支持度量和断言，但仅在 Pauli `Z`。
请注意，某些度量值的概率始终为0或 1;Toffoli 模拟器中没有随机性。

支持 `DumpMachine` 和 `DumpRegister`。
它们都输出每个 qubit 的当前 `Z`的状态，每行一个 qubit。

## <a name="qubitcount"></a>QubitCount

默认情况下，`ToffoliSimulator` 为 65536 qubits 分配空间。
如果你的算法需要超过此值，则可以通过向构造函数提供 `qubitCount` 参数的值来更改 qubit 计数。
每个额外的 qubit 都需要额外的内存字节，因此，估计过高所需的 qubits 数量不会产生很大的代价。

例如：

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
