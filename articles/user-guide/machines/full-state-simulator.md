---
title: 完整状态量程模拟器-量程开发工具包
description: 了解如何 Q# 在 Microsoft Quantum Development Kit 完全状态模拟器上运行你的程序。
author: anpaz
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.full-state-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 950e61c812cc6df739ddaa1de855f753557d6d1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858172"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a><span data-ttu-id="7a206-103">量程开发工具包 (QDK) 完整状态模拟器</span><span class="sxs-lookup"><span data-stu-id="7a206-103">Quantum Development Kit (QDK) full state simulator</span></span>

<span data-ttu-id="7a206-104">QDK 提供了模拟本地计算机上的量子计算机的完整状态模拟器。</span><span class="sxs-lookup"><span data-stu-id="7a206-104">The QDK provides a full state simulator that simulates a quantum machine on your local computer.</span></span> <span data-ttu-id="7a206-105">可以使用完整状态模拟器来运行和调试用编写的量程算法 Q# ，最多可利用30个 qubits。</span><span class="sxs-lookup"><span data-stu-id="7a206-105">You can use the full state simulator to run and debug quantum algorithms written in Q#, utilizing up to 30 qubits.</span></span> <span data-ttu-id="7a206-106">完整状态模拟器类似于 Microsoft Research 的  [LIQ $ Ui | \rangle $](http://stationq.github.io/Liquid/) 平台中使用的量程模拟器。</span><span class="sxs-lookup"><span data-stu-id="7a206-106">The full state simulator is similar to the quantum simulator used in the  [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) platform from Microsoft Research.</span></span>

## <a name="invoking-and-running-the-full-state-simulator"></a><span data-ttu-id="7a206-107">调用并运行完全状态模拟器</span><span class="sxs-lookup"><span data-stu-id="7a206-107">Invoking and running the full state simulator</span></span>

<span data-ttu-id="7a206-108">通过类公开完整状态模拟器 `QuantumSimulator` 。</span><span class="sxs-lookup"><span data-stu-id="7a206-108">You expose the full state simulator via the `QuantumSimulator` class.</span></span> <span data-ttu-id="7a206-109">有关更多详细信息，请参阅 [运行 Q# 程序的方法](xref:microsoft.quantum.guide.host-programs)。</span><span class="sxs-lookup"><span data-stu-id="7a206-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-simulator-from-c"></a><span data-ttu-id="7a206-110">从 C 调用模拟器#</span><span class="sxs-lookup"><span data-stu-id="7a206-110">Invoking the simulator from C#</span></span>

<span data-ttu-id="7a206-111">创建类的实例， `QuantumSimulator` 然后将其传递给 `Run` 量程操作的方法以及任何其他参数。</span><span class="sxs-lookup"><span data-stu-id="7a206-111">Create an instance of the `QuantumSimulator` class and then pass it to the `Run` method of a quantum operation, along with any additional parameters.</span></span>
```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

<span data-ttu-id="7a206-112">由于 `QuantumSimulator` 类实现 <xref:System.IDisposable> 接口，因此，一旦不再需要模拟器的实例，就必须调用 `Dispose` 方法。</span><span class="sxs-lookup"><span data-stu-id="7a206-112">Because the `QuantumSimulator` class implements the <xref:System.IDisposable> interface, you must call the `Dispose` method once you do not need the instance of the simulator anymore.</span></span> <span data-ttu-id="7a206-113">执行此操作的最佳方法是在 [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) 语句中包装模拟器声明和操作，这会自动调用 `Dispose` 方法。</span><span class="sxs-lookup"><span data-stu-id="7a206-113">The best way to do this is to wrap the simulator declaration and operations within a [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) statement, which automatically calls the `Dispose` method.</span></span>

### <a name="invoking-the-simulator-from-python"></a><span data-ttu-id="7a206-114">从 Python 调用模拟器</span><span class="sxs-lookup"><span data-stu-id="7a206-114">Invoking the simulator from Python</span></span>

<span data-ttu-id="7a206-115">使用导入的操作从 Python 库中 [模拟 ( # B1 ](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) 方法 Q# Q# ：</span><span class="sxs-lookup"><span data-stu-id="7a206-115">Use the [simulate()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Q# Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a><span data-ttu-id="7a206-116">从命令行调用模拟器</span><span class="sxs-lookup"><span data-stu-id="7a206-116">Invoking the simulator from the command line</span></span>

<span data-ttu-id="7a206-117">在 Q# 从命令行运行程序时，完全状态模拟器是默认的目标计算机。</span><span class="sxs-lookup"><span data-stu-id="7a206-117">When running a Q# program from the command line, the full state simulator is the default target machine.</span></span> <span data-ttu-id="7a206-118">（可选）可以使用 **--模拟器** (或 **-s** 快捷键) 参数指定所需的目标计算机。</span><span class="sxs-lookup"><span data-stu-id="7a206-118">Optionally, you can use the **--simulator** (or **-s** shortcut) parameter to specify the desired target machine.</span></span> <span data-ttu-id="7a206-119">以下两个命令都使用完整状态模拟器运行程序。</span><span class="sxs-lookup"><span data-stu-id="7a206-119">Both of the following commands run a program using the full state simulator.</span></span> 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a><span data-ttu-id="7a206-120">从 Juptyer 笔记本调用模拟器</span><span class="sxs-lookup"><span data-stu-id="7a206-120">Invoking the simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="7a206-121">使用 "我的 Q# 神奇命令 [% 模拟](xref:microsoft.quantum.iqsharp.magic-ref.simulate) " 运行 Q# 操作。</span><span class="sxs-lookup"><span data-stu-id="7a206-121">Use the IQ# magic command [%simulate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%simulate myOperation
```
## <a name="seeding-the-simulator"></a><span data-ttu-id="7a206-122">播种模拟器</span><span class="sxs-lookup"><span data-stu-id="7a206-122">Seeding the simulator</span></span>

<span data-ttu-id="7a206-123">默认情况下，完整状态模拟器使用随机数生成器来模拟量程随机性。</span><span class="sxs-lookup"><span data-stu-id="7a206-123">By default, the full state simulator uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="7a206-124">出于测试目的，具有确定性的结果有时会很有用。</span><span class="sxs-lookup"><span data-stu-id="7a206-124">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="7a206-125">在 c # 程序中，可以通过参数在构造函数中提供随机数生成器的种子，来实现此目的 `QuantumSimulator` `randomNumberGeneratorSeed` 。</span><span class="sxs-lookup"><span data-stu-id="7a206-125">In a C# program, you can accomplish this by providing a seed for the random number generator in the `QuantumSimulator` constructor via the `randomNumberGeneratorSeed` parameter.</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="configuring-threads"></a><span data-ttu-id="7a206-126">配置线程</span><span class="sxs-lookup"><span data-stu-id="7a206-126">Configuring threads</span></span>

<span data-ttu-id="7a206-127">完整状态模拟器使用 [OpenMP](http://www.openmp.org/) 对所需的线性代数进行并行化。</span><span class="sxs-lookup"><span data-stu-id="7a206-127">The full state simulator uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="7a206-128">默认情况下，OpenMP 使用所有可用的硬件线程，这意味着具有少量 qubits 的程序通常会运行缓慢，因为需要 dwarfs 实际工作。</span><span class="sxs-lookup"><span data-stu-id="7a206-128">By default, OpenMP uses all available hardware threads, which means that programs with small numbers of qubits often runs slowly because the coordination that is required dwarfs the actual work.</span></span> <span data-ttu-id="7a206-129">可以通过将环境变量设置 `OMP_NUM_THREADS` 为小数值来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="7a206-129">You can fix this by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="7a206-130">根据经验法则，为一个线程配置最多四个 qubits，然后为每个 qubit 配置一个其他线程。</span><span class="sxs-lookup"><span data-stu-id="7a206-130">As a rule of thumb, configure one thread for up to four qubits, and then one additional thread per qubit.</span></span> <span data-ttu-id="7a206-131">你可能需要根据你的算法调整此变量。</span><span class="sxs-lookup"><span data-stu-id="7a206-131">You might need to adjust the variable depending on your algorithm.</span></span>

## <a name="see-also"></a><span data-ttu-id="7a206-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7a206-132">See also</span></span>

- [<span data-ttu-id="7a206-133">量子资源估算器</span><span class="sxs-lookup"><span data-stu-id="7a206-133">Quantum resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="7a206-134">量子 Toffoli 模拟器</span><span class="sxs-lookup"><span data-stu-id="7a206-134">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="7a206-135">量程跟踪模拟器</span><span class="sxs-lookup"><span data-stu-id="7a206-135">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)