---
title: 量子模拟器和 Q# 程序
description: 介绍可用作 Q# 程序的目标计算机的量子模拟器。
author: QuantumWriter
ms.author: v-benbra
ms.date: 6/17/2020
ms.topic: article
uid: microsoft.quantum.machines
no-loc:
- Q#
- $$v
ms.openlocfilehash: f40c63eed60379aa46a0cd9cfdd7d8de8c22c079
ms.sourcegitcommit: d98190988ff03146d9ca2b0d325870cd717d729a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2020
ms.locfileid: "91771308"
---
# <a name="quantum-simulators"></a><span data-ttu-id="1d12e-103">量子模拟器</span><span class="sxs-lookup"><span data-stu-id="1d12e-103">Quantum simulators</span></span>

<span data-ttu-id="1d12e-104">量子模拟器是在经典计算机上运行并充当 Q# 程序的目标计算机的软件程序。借助这些软件程序，可以在预测量子位将如何对不同操作做出反应的环境中运行和测试量子程序。</span><span class="sxs-lookup"><span data-stu-id="1d12e-104">Quantum simulators are software programs that run on classical computers and act as the *target machine* for a Q# program, making it possible to run and test quantum programs in an environment that predicts how qubits will react to different operations.</span></span> <span data-ttu-id="1d12e-105">本文介绍 Quantum 开发工具包 (QDK) 中包含哪些量子模拟器，以及将 Q# 程序传递到量子模拟器的不同方式，例如，可通过命令行传递，也可通过以经典语言编写的驱动程序代码传递。</span><span class="sxs-lookup"><span data-stu-id="1d12e-105">This article describes which quantum simulators are included with the Quantum Development Kit (QDK), and different ways that you can pass a Q# program to the quantum simulators, for example, via the command line or by using driver code written in a classical language.</span></span>  



## <a name="the-quantum-development-kit-qdk-quantum-simulators"></a><span data-ttu-id="1d12e-106">Quantum 开发工具包 (QDK) 量子模拟器</span><span class="sxs-lookup"><span data-stu-id="1d12e-106">The Quantum Development Kit (QDK) quantum simulators</span></span>

<span data-ttu-id="1d12e-107">量子模拟器负责为算法提供量子基元的实现。</span><span class="sxs-lookup"><span data-stu-id="1d12e-107">The quantum simulator is responsible for providing implementations of quantum primitives for an algorithm.</span></span> <span data-ttu-id="1d12e-108">其中包括 `H`、`CNOT` 和 `Measure` 等基元操作，以及量子位管理和跟踪。</span><span class="sxs-lookup"><span data-stu-id="1d12e-108">This includes primitive operations such as `H`, `CNOT`, and `Measure`, as well as qubit management and tracking.</span></span> <span data-ttu-id="1d12e-109">QDK 包括不同类的量子模拟器，它们表示同一量子算法的不同模拟方式。</span><span class="sxs-lookup"><span data-stu-id="1d12e-109">The QDK includes different classes of quantum simulators representing different ways of simulating the same quantum algorithm.</span></span> 


<span data-ttu-id="1d12e-110">每种类型的量子模拟器可以提供这些基元的不同实现。</span><span class="sxs-lookup"><span data-stu-id="1d12e-110">Each type of quantum simulator can provide different implementations of these primitives.</span></span> <span data-ttu-id="1d12e-111">例如，[全状态模拟器](xref:microsoft.quantum.machines.full-state-simulator)通过全面模拟[量子状态矢量](xref:microsoft.quantum.glossary#quantum-state)来运行量子算法，而[量子计算机跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)则根本不考虑实际的量子状态。</span><span class="sxs-lookup"><span data-stu-id="1d12e-111">For example, the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator) runs the quantum algorithm by fully simulating the [quantum state vector](xref:microsoft.quantum.glossary#quantum-state), whereas the [quantum computer trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) doesn't consider the actual quantum state at all.</span></span> <span data-ttu-id="1d12e-112">而是跟踪算法的量子门、量子位和其他资源使用情况。</span><span class="sxs-lookup"><span data-stu-id="1d12e-112">Rather, it tracks gate, qubit, and other resource usage for the algorithm.</span></span>

### <a name="quantum-machine-classes"></a><span data-ttu-id="1d12e-113">量子计算机类</span><span class="sxs-lookup"><span data-stu-id="1d12e-113">Quantum machine classes</span></span>

<span data-ttu-id="1d12e-114">未来，QDK 将定义更多量子计算机类以支持其他类型的模拟，并支持在量子硬件上运行。</span><span class="sxs-lookup"><span data-stu-id="1d12e-114">In the future, the QDK will define additional quantum machine classes to support other types of simulation and to support running on quantum hardware.</span></span> <span data-ttu-id="1d12e-115">在改变基础计算机实现的同时允许算法保持不变，可以轻松地在模拟中测试和调试算法，然后在实际硬件上运行该算法，确信该算法没有发生更改。</span><span class="sxs-lookup"><span data-stu-id="1d12e-115">Allowing the algorithm to stay constant while varying the underlying machine implementation makes it easy to test and debug an algorithm in simulation and then run it on real hardware with confidence that the algorithm hasn't changed.</span></span>

<span data-ttu-id="1d12e-116">QDK 包含多个量子计算机类，全都在 `Microsoft.Quantum.Simulation.Simulators` 命名空间中定义。</span><span class="sxs-lookup"><span data-stu-id="1d12e-116">The QDK includes several quantum machine classes, all defined in the `Microsoft.Quantum.Simulation.Simulators` namespace.</span></span>

|<span data-ttu-id="1d12e-117">模拟器</span><span class="sxs-lookup"><span data-stu-id="1d12e-117">Simulator</span></span> |<span data-ttu-id="1d12e-118">类</span><span class="sxs-lookup"><span data-stu-id="1d12e-118">Class</span></span>|<span data-ttu-id="1d12e-119">说明</span><span class="sxs-lookup"><span data-stu-id="1d12e-119">Description</span></span>|
|-----|------|---|
|[<span data-ttu-id="1d12e-120">全状态模拟器</span><span class="sxs-lookup"><span data-stu-id="1d12e-120">Full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator)| `QuantumSimulator` | <span data-ttu-id="1d12e-121">运行和调试量子算法，限制为大约 30 个量子位。</span><span class="sxs-lookup"><span data-stu-id="1d12e-121">Runs and debugs quantum algorithms, and is limited to about 30 qubits.</span></span> |
|[<span data-ttu-id="1d12e-122">简单的资源估算器</span><span class="sxs-lookup"><span data-stu-id="1d12e-122">Simple resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)| `ResourcesEstimator` | <span data-ttu-id="1d12e-123">对运行量子算法所需的资源进行顶级分析，支持数千个量子位。</span><span class="sxs-lookup"><span data-stu-id="1d12e-123">Performs a top level analysis of the resources needed to run a quantum algorithm, and supports thousands of qubits.</span></span>|
|[<span data-ttu-id="1d12e-124">基于跟踪的资源估算器</span><span class="sxs-lookup"><span data-stu-id="1d12e-124">Trace-based resource estimator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)|  `QCTraceSimulator` |<span data-ttu-id="1d12e-125">对算法的整个调用关系图的资源消耗量运行高级分析，支持数千个量子位。</span><span class="sxs-lookup"><span data-stu-id="1d12e-125">Runs advanced analysis of resources consumptions for the algorithm's entire call-graph, and supports thousands of qubits.</span></span>|
|[<span data-ttu-id="1d12e-126">Toffoli 模拟器</span><span class="sxs-lookup"><span data-stu-id="1d12e-126">Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)| `ToffoliSimulator` |<span data-ttu-id="1d12e-127">模拟仅限 `X` 和 `CNOT` 在内的量子算法和多重控制的 `X` 量子操作，支持数百万个量子位。</span><span class="sxs-lookup"><span data-stu-id="1d12e-127">Simulates quantum algorithms that are limited to `X`, `CNOT`, and multi-controlled `X` quantum operations, and supports million of qubits.</span></span> |

## <a name="invoking-the-quantum-simulator"></a><span data-ttu-id="1d12e-128">调用量子模拟器</span><span class="sxs-lookup"><span data-stu-id="1d12e-128">Invoking the quantum simulator</span></span>

<span data-ttu-id="1d12e-129">在 [Q# 程序的运行方式](xref:microsoft.quantum.guide.host-programs)中，演示了三种将 Q# 代码传递到量子模拟器的方式：</span><span class="sxs-lookup"><span data-stu-id="1d12e-129">In [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs), three ways of passing the Q# code to the quantum simulator are demonstrated:</span></span> 

* <span data-ttu-id="1d12e-130">使用命令行</span><span class="sxs-lookup"><span data-stu-id="1d12e-130">Using the command line</span></span>
* <span data-ttu-id="1d12e-131">使用 Python 主机程序</span><span class="sxs-lookup"><span data-stu-id="1d12e-131">Using a Python host program</span></span>
* <span data-ttu-id="1d12e-132">使用 C# 主机程序</span><span class="sxs-lookup"><span data-stu-id="1d12e-132">Using a C# host program</span></span>

<span data-ttu-id="1d12e-133">量子机是普通 .NET 类的实例，因此它们是通过调用其构造函数来创建的，就像任何 .NET 类一样。</span><span class="sxs-lookup"><span data-stu-id="1d12e-133">Quantum machines are instances of normal .NET classes, so they are created by invoking their constructor, just like any .NET class.</span></span> <span data-ttu-id="1d12e-134">具体操作方式取决于运行 Q# 程序的方式。</span><span class="sxs-lookup"><span data-stu-id="1d12e-134">How you do this depends on how you run the Q# program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1d12e-135">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1d12e-135">Next steps</span></span>

* <span data-ttu-id="1d12e-136">若要详细了解如何在不同环境中调用 Q# 程序的目标计算机，请参阅 [Q# 程序的运行方式](xref:microsoft.quantum.guide.host-programs)。</span><span class="sxs-lookup"><span data-stu-id="1d12e-136">For details about how to invoke target machines for Q# programs in different environments, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
