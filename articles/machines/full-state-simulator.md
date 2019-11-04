---
title: 量程开发工具包完整状态模拟器 |Microsoft Docs
description: Microsoft 的量程开发工具包完整状态模拟器概述
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: ab0e65765d27e301a59948d7c02105a523022e68
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184672"
---
# <a name="quantum-development-kit-full-state-simulator"></a><span data-ttu-id="a933d-103">量程开发工具包完整状态模拟器</span><span class="sxs-lookup"><span data-stu-id="a933d-103">Quantum Development Kit Full State Simulator</span></span>

<span data-ttu-id="a933d-104">量程开发工具包提供了一个完整的状态量程模拟器，类似于 Microsoft Research 的[LIQ $ Ui | \rangle $](http://stationq.github.io/Liquid/) 。</span><span class="sxs-lookup"><span data-stu-id="a933d-104">The Quantum Development Kit provides a full state quantum simulator similar to [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) from Microsoft Research.</span></span>
<span data-ttu-id="a933d-105">此模拟器可用于执行和调试在计算机上用 Q # 编写的量程算法。</span><span class="sxs-lookup"><span data-stu-id="a933d-105">This simulator can be used to execute and debug quantum algorithms written in Q# on your computer.</span></span>

<span data-ttu-id="a933d-106">此量程模拟器通过 `QuantumSimulator` 类公开。</span><span class="sxs-lookup"><span data-stu-id="a933d-106">This quantum simulator is exposed via the `QuantumSimulator` class.</span></span> <span data-ttu-id="a933d-107">若要使用模拟器，只需创建此类的一个实例，并将其传递给要执行的量程操作的 `Run` 方法，同时执行其余的参数：</span><span class="sxs-lookup"><span data-stu-id="a933d-107">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a><span data-ttu-id="a933d-108">IDisposable</span><span class="sxs-lookup"><span data-stu-id="a933d-108">IDisposable</span></span>

<span data-ttu-id="a933d-109">`QuantumSimulator` 类实现 <xref:System.IDisposable>，因此，在不再使用模拟器的实例后，应调用 `Dispose` 方法。</span><span class="sxs-lookup"><span data-stu-id="a933d-109">The `QuantumSimulator` class implements <xref:System.IDisposable>, thus the `Dispose` method should be called once the instance of the simulator is not used anymore.</span></span> <span data-ttu-id="a933d-110">实现此目的的最佳方式是在 `using` 语句中包装模拟器，如以上示例中所示。</span><span class="sxs-lookup"><span data-stu-id="a933d-110">The best way to do this is to wrap the simulator within a `using` statement, as in the example above.</span></span>

## <a name="seed"></a><span data-ttu-id="a933d-111">种子</span><span class="sxs-lookup"><span data-stu-id="a933d-111">Seed</span></span>

<span data-ttu-id="a933d-112">`QuantumSimulator` 使用随机数生成器来模拟量子随机性。</span><span class="sxs-lookup"><span data-stu-id="a933d-112">The `QuantumSimulator` uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="a933d-113">出于测试目的，具有确定性的结果有时会很有用。</span><span class="sxs-lookup"><span data-stu-id="a933d-113">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="a933d-114">为此，可以通过 `randomNumberGeneratorSeed` 参数在 `QuantumSimulator`的构造函数中提供随机数生成器的种子：</span><span class="sxs-lookup"><span data-stu-id="a933d-114">This can be accomplished by providing a seed for the random number generator in the `QuantumSimulator`'s constructor via the `randomNumberGeneratorSeed` parameter:</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a><span data-ttu-id="a933d-115">线程数</span><span class="sxs-lookup"><span data-stu-id="a933d-115">Threads</span></span>

<span data-ttu-id="a933d-116">`QuantumSimulator` 使用[OpenMP](http://www.openmp.org/)对所需的线性代数进行并行化。</span><span class="sxs-lookup"><span data-stu-id="a933d-116">The `QuantumSimulator` uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="a933d-117">默认情况下，OpenMP 使用所有可用的硬件线程，这意味着具有少量 qubits 的程序通常会运行缓慢，因为所需协调将 dwarf 实际工作。</span><span class="sxs-lookup"><span data-stu-id="a933d-117">By default OpenMP uses all available hardware threads, which means that programs with small numbers of qubits will often run slowly because the coordination required will dwarf the actual work.</span></span> <span data-ttu-id="a933d-118">为此，可以将环境变量 `OMP_NUM_THREADS` 设置为一个较小的数字。</span><span class="sxs-lookup"><span data-stu-id="a933d-118">This can be fixed by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="a933d-119">由于经验非常粗略，1个线程非常适合最多4个 qubits，而每个 qubit 的另一个线程非常好，不过，这一点非常依赖于你的算法。</span><span class="sxs-lookup"><span data-stu-id="a933d-119">As a very rough rule of thumb, 1 thread is good for up to about 4 qubits, and then an additional thread per qubit is good, although this is highly dependent on your algorithm.</span></span>

