---
title: 宽度计数器-量程开发工具包
description: '了解 Microsoft QDK width 计数器，该计数器使用量程跟踪模拟器来计算程序中由操作分配和借用的 qubits 的数量 :::no-loc(Q#)::: 。'
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: e54e92cc4a76ce9f9c5aead84f2b64320d6b4f1c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691130"
---
# <a name="quantum-trace-simulator-width-counter"></a><span data-ttu-id="62940-103">量程跟踪模拟器：宽度计数器</span><span class="sxs-lookup"><span data-stu-id="62940-103">Quantum trace simulator: width counter</span></span>

<span data-ttu-id="62940-104">Width 计数器是量程开发工具包 [量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的一部分。</span><span class="sxs-lookup"><span data-stu-id="62940-104">The width counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="62940-105">您可以使用它来计算程序中每个操作所分配和借用的 qubits 的数目 :::no-loc(Q#)::: 。</span><span class="sxs-lookup"><span data-stu-id="62940-105">You can use it to count the number of qubits allocated and borrowed by each operation in a :::no-loc(Q#)::: program.</span></span> <span data-ttu-id="62940-106">一些基元操作可以分配额外的 qubits，例如，将受控 `X` 操作或受控 `T` 操作相乘。</span><span class="sxs-lookup"><span data-stu-id="62940-106">Some primitive operations can allocate extra qubits, for example, multiply controlled `X` operations or controlled `T` operations.</span></span>

## <a name="invoking-the-width-counter"></a><span data-ttu-id="62940-107">调用 width 计数器</span><span class="sxs-lookup"><span data-stu-id="62940-107">Invoking the width counter</span></span>

<span data-ttu-id="62940-108">若要运行具有 width 计数器的量程跟踪模拟器，您必须创建一个 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 实例，将 `UseWidthCounter` 属性设置为 **true** ，然后 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> 使用作为参数创建新的实例 `QCTraceSimulatorConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="62940-108">To run the quantum trace simulator with the width counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseWidthCounter` property to **true** , and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a><span data-ttu-id="62940-109">在 c # 宿主程序中使用 width 计数器</span><span class="sxs-lookup"><span data-stu-id="62940-109">Using the width counter in a C# host program</span></span>

<span data-ttu-id="62940-110">本部分中的 c # 示例将根据 <xref:Microsoft.Quantum.Intrinsic.X> 下面的示例代码，计算由执行乘法控制的操作所分配的额外 qubits 的数目 :::no-loc(Q#)::: ：</span><span class="sxs-lookup"><span data-stu-id="62940-110">The C# example that follows in this section computes the number of extra qubits allocated by the implementation of a multiply controlled <xref:Microsoft.Quantum.Intrinsic.X> operation, based on the following :::no-loc(Q#)::: sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

<span data-ttu-id="62940-111">乘法控制 <xref:Microsoft.Quantum.Intrinsic.X> 运算的作用是总共5个 qubits，分配两个 [辅助 qubits](xref:microsoft.quantum.glossary#ancilla)，且输入宽度为 **5** 。</span><span class="sxs-lookup"><span data-stu-id="62940-111">The multiply controlled <xref:Microsoft.Quantum.Intrinsic.X> operation acts on a total of five qubits, allocates two [ancillary qubits](xref:microsoft.quantum.glossary#ancilla), and has an input width of **5** .</span></span> <span data-ttu-id="62940-112">使用以下 c # 程序来验证计数：</span><span class="sxs-lookup"><span data-stu-id="62940-112">Use the following C# program to verify the counts:</span></span>

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = ApplyMultiControlledX.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

<span data-ttu-id="62940-113">程序的第一个部分运行 `ApplyMultiControlledX` 操作。</span><span class="sxs-lookup"><span data-stu-id="62940-113">The first part of the program runs the `ApplyMultiControlledX` operation.</span></span> <span data-ttu-id="62940-114">第二部分使用 [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) 方法检索已分配的 qubits 的数目，以及操作收到的作为输入的 qubits 数 `Controlled X` 。</span><span class="sxs-lookup"><span data-stu-id="62940-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of allocated qubits as well as the number of qubits that the `Controlled X` operation received as input.</span></span> 

<span data-ttu-id="62940-115">最后，可以使用以下内容输出使用 CSV 格式的 width 计数器收集的所有统计信息：</span><span class="sxs-lookup"><span data-stu-id="62940-115">Finally, you can output all the statistics collected by the width counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="62940-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62940-116">See also</span></span>

- <span data-ttu-id="62940-117">量程开发工具包 [量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro) 概述。</span><span class="sxs-lookup"><span data-stu-id="62940-117">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="62940-118"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API 参考。</span><span class="sxs-lookup"><span data-stu-id="62940-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="62940-119"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API 参考。</span><span class="sxs-lookup"><span data-stu-id="62940-119">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="62940-120"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter>API 参考。</span><span class="sxs-lookup"><span data-stu-id="62940-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter> API reference.</span></span>
