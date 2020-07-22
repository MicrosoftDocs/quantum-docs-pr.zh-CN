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
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a><span data-ttu-id="5590e-103">量程开发工具包（QDK） Toffoli 模拟器</span><span class="sxs-lookup"><span data-stu-id="5590e-103">Quantum Development Kit (QDK) Toffoli simulator</span></span>

<span data-ttu-id="5590e-104">QDK Toffoli 模拟器是一种特殊用途的模拟器，其作用域有限，只支持 `X` 、 `CNOT` 和多受控 `X` 量程操作。</span><span class="sxs-lookup"><span data-stu-id="5590e-104">The QDK Toffoli simulator is a special-purpose simulator with a limited scope and only supports `X`, `CNOT`, and multi-controlled `X` quantum operations.</span></span> <span data-ttu-id="5590e-105">所有传统逻辑和计算都可用。</span><span class="sxs-lookup"><span data-stu-id="5590e-105">All classical logic and computations are available.</span></span>

<span data-ttu-id="5590e-106">尽管 Toffoli 模拟器比[完整状态模拟器](xref:microsoft.quantum.machines.full-state-simulator)更受限制，但它的优势是能够模拟更多 qubits。</span><span class="sxs-lookup"><span data-stu-id="5590e-106">While the Toffoli simulator is more restricted in functionality than the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), it has the advantage of being able to simulate far more qubits.</span></span> <span data-ttu-id="5590e-107">Toffoli 模拟器可用于数百万 qubits，而完整状态模拟器仅限约 30 qubits。</span><span class="sxs-lookup"><span data-stu-id="5590e-107">The Toffoli simulator can be used with millions of qubits, while the full state simulator is limited to about 30 qubits.</span></span> <span data-ttu-id="5590e-108">这很有用，例如，使用 oracles 来计算布尔函数，它们可以使用有限的一组受支持的算法来实现，并在大量 qubits 上测试。</span><span class="sxs-lookup"><span data-stu-id="5590e-108">This is useful, for example, with oracles that evaluate Boolean functions - they can be implemented using the limited set of supported algorithms and tested on a large number of qubits.</span></span>

## <a name="invoking-the-toffoli-simulator"></a><span data-ttu-id="5590e-109">调用 Toffoli 模拟器</span><span class="sxs-lookup"><span data-stu-id="5590e-109">Invoking the Toffoli simulator</span></span>

<span data-ttu-id="5590e-110">通过类公开 Toffoli 模拟器 `ToffoliSimulator` 。</span><span class="sxs-lookup"><span data-stu-id="5590e-110">You expose the Toffoli simulator via the `ToffoliSimulator` class.</span></span> <span data-ttu-id="5590e-111">有关更多详细信息，请参阅[运行 Q # 程序的方法](xref:microsoft.quantum.guide.host-programs)。</span><span class="sxs-lookup"><span data-stu-id="5590e-111">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-toffoli-simulator-from-c"></a><span data-ttu-id="5590e-112">从 C 调用 Toffoli 模拟器#</span><span class="sxs-lookup"><span data-stu-id="5590e-112">Invoking the Toffoli simulator from C#</span></span>

<span data-ttu-id="5590e-113">与其他目标计算机一样，首先创建类的一个实例 `ToffoliSimulator` ，然后将其作为操作的方法的第一个参数进行传递 `Run` 。</span><span class="sxs-lookup"><span data-stu-id="5590e-113">As with other target machines, you first create an instance of the `ToffoliSimulator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="5590e-114">请注意，与类不同的是， `QuantumSimulator` `ToffoliSimulator` 类并不实现 <xref:System.IDisposable> 接口，因此不需要将其包含在 `using` 语句中。</span><span class="sxs-lookup"><span data-stu-id="5590e-114">Note that, unlike the `QuantumSimulator` class, the `ToffoliSimulator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a><span data-ttu-id="5590e-115">从 Python 调用 Toffoli 模拟器</span><span class="sxs-lookup"><span data-stu-id="5590e-115">Invoking the Toffoli simulator from Python</span></span>

<span data-ttu-id="5590e-116">在导入的 Q # 操作中使用 Python 库中的[toffoli_simulate （）](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable)方法：</span><span class="sxs-lookup"><span data-stu-id="5590e-116">Use the [toffoli_simulate()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a><span data-ttu-id="5590e-117">从命令行调用 Toffoli 模拟器</span><span class="sxs-lookup"><span data-stu-id="5590e-117">Invoking the Toffoli simulator from the command line</span></span>

<span data-ttu-id="5590e-118">从命令行运行 Q # 程序时，使用 **--模拟器**（或 **-s**快捷方式）参数指定 Toffoli 模拟器目标计算机。</span><span class="sxs-lookup"><span data-stu-id="5590e-118">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the Toffoli simulator target machine.</span></span> <span data-ttu-id="5590e-119">以下命令使用资源估计器运行程序：</span><span class="sxs-lookup"><span data-stu-id="5590e-119">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a><span data-ttu-id="5590e-120">从 Juptyer 笔记本调用 Toffoli 模拟器</span><span class="sxs-lookup"><span data-stu-id="5590e-120">Invoking the Toffoli simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="5590e-121">使用 IQ # 幻命令[% toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli)运行 Q # 操作。</span><span class="sxs-lookup"><span data-stu-id="5590e-121">Use the IQ# magic command [%toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) to run the Q# operation.</span></span>

```
%toffoli myOperation
```

## <a name="supported-operations"></a><span data-ttu-id="5590e-122">支持的操作</span><span class="sxs-lookup"><span data-stu-id="5590e-122">Supported operations</span></span>

<span data-ttu-id="5590e-123">Toffoli 模拟器支持：</span><span class="sxs-lookup"><span data-stu-id="5590e-123">The Toffoli simulator supports:</span></span>

* <span data-ttu-id="5590e-124">`R` `Exp` 当结果操作等于或标识矩阵时，旋转和指数化 Paulis （如和） `X` 。</span><span class="sxs-lookup"><span data-stu-id="5590e-124">Rotations and exponentiated Paulis, such as `R` and `Exp`, when the resulting operation equals `X` or the identity matrix.</span></span>
* <span data-ttu-id="5590e-125">度量和[断言](xref:microsoft.quantum.diagnostics.assertmeasurement)操作，但仅在 Pauli `Z` 基础中。</span><span class="sxs-lookup"><span data-stu-id="5590e-125">Measurement and [assert](xref:microsoft.quantum.diagnostics.assertmeasurement) operations, but only in the Pauli `Z` basis.</span></span> <span data-ttu-id="5590e-126">请注意，度量操作的概率始终为**0**或**1**;Toffoli 模拟器中没有随机性。</span><span class="sxs-lookup"><span data-stu-id="5590e-126">Note that a measurement operation's probability is always either **0** or **1**; there is no randomness in the Toffoli simulator.</span></span>
* <span data-ttu-id="5590e-127">`DumpMachine`和 `DumpRegister` 函数。</span><span class="sxs-lookup"><span data-stu-id="5590e-127">`DumpMachine` and `DumpRegister` functions.</span></span>
<span data-ttu-id="5590e-128">这两个函数输出 `Z` 每个 qubit 的当前基础状态，每行一个 qubit。</span><span class="sxs-lookup"><span data-stu-id="5590e-128">Both functions output the current `Z`-basis state of each qubit, one qubit per line.</span></span>

## <a name="specifying-the-number-of-qubits"></a><span data-ttu-id="5590e-129">指定 qubits 数</span><span class="sxs-lookup"><span data-stu-id="5590e-129">Specifying the number of qubits</span></span>

<span data-ttu-id="5590e-130">默认情况下， `ToffoliSimulator` 实例为 65536 qubits 分配空间。</span><span class="sxs-lookup"><span data-stu-id="5590e-130">By default, a `ToffoliSimulator` instance allocates space for 65,536 qubits.</span></span>
<span data-ttu-id="5590e-131">如果你的算法需要比此更多的 qubits，则可以通过向构造函数提供参数的值来指定 qubit 计数 `qubitCount` 。</span><span class="sxs-lookup"><span data-stu-id="5590e-131">If your algorithm requires more qubits than this, you can specify the qubit count by providing a value for the `qubitCount` parameter to the constructor.</span></span>
<span data-ttu-id="5590e-132">每个额外的 qubit 只需要一个字节的内存，因此估计过高的 qubits 数量不会产生很大的代价。</span><span class="sxs-lookup"><span data-stu-id="5590e-132">Each additional qubit requires only one byte of memory, so there is no significant cost to overestimating the number of qubits you'll need.</span></span>

<span data-ttu-id="5590e-133">例如：</span><span class="sxs-lookup"><span data-stu-id="5590e-133">For example:</span></span>

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

## <a name="see-also"></a><span data-ttu-id="5590e-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5590e-134">See also</span></span>

- [<span data-ttu-id="5590e-135">量程资源估计器</span><span class="sxs-lookup"><span data-stu-id="5590e-135">Quantum Resources Estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="5590e-136">量程跟踪模拟器</span><span class="sxs-lookup"><span data-stu-id="5590e-136">Quantum Trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="5590e-137">量程完全状态模拟器</span><span class="sxs-lookup"><span data-stu-id="5590e-137">Quantum Full State simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 