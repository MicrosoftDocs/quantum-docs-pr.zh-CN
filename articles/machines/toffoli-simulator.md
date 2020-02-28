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
# <a name="quantum-development-kit-toffoli-simulator"></a><span data-ttu-id="25650-103">量程开发工具包 Toffoli 模拟器</span><span class="sxs-lookup"><span data-stu-id="25650-103">Quantum Development Kit Toffoli Simulator</span></span>

<span data-ttu-id="25650-104">量程开发工具包提供了一个 Toffoli 模拟器，它是一种特殊用途的模拟器，可以模拟限制为 X、CNOT-CONTAINS 和多受控 X 量程操作的量程算法（所有传统逻辑和计算都可用）。</span><span class="sxs-lookup"><span data-stu-id="25650-104">The Quantum Development Kit provides a Toffoli simulator, which is a special-purpose simulator that can simulate quantum algorithms that are limited to X, CNOT, and multi-controlled X quantum operations (all classical logic and computations are available).</span></span>

<span data-ttu-id="25650-105">尽管 Toffoli 模拟器比[完整状态模拟器](xref:microsoft.quantum.machines.full-state-simulator)的操作受到限制更多，但它可以模拟更多 qubits。</span><span class="sxs-lookup"><span data-stu-id="25650-105">While the Toffoli simulator is much more restricted in operation than the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), it can simulate far more qubits.</span></span>
<span data-ttu-id="25650-106">Toffoli 模拟器可用于数百万 qubits，而完整状态模拟器一般限制为大约30。</span><span class="sxs-lookup"><span data-stu-id="25650-106">The Toffoli simulator can be used with millions of qubits, while the full state simulator is generally limited to about 30.</span></span>
<span data-ttu-id="25650-107">它可以执行和调试在计算机上用 Q # 编写的有限的一组量程算法;例如，可以使用这些入口来实现计算布尔函数的 oracles，因此在上经过测试的可以使用此模拟器改变大量 qubits。</span><span class="sxs-lookup"><span data-stu-id="25650-107">It can execute and debug a limited set of quantum algorithms written in Q# on your computer; for instance, oracles that evaluate Boolean functions can be implemented using these gates and so tested on vary large numbers of qubits using this simulator.</span></span>

<span data-ttu-id="25650-108">此量程模拟器通过 `ToffoliSimulator` 类公开。</span><span class="sxs-lookup"><span data-stu-id="25650-108">This quantum simulator is exposed via the `ToffoliSimulator` class.</span></span>
<span data-ttu-id="25650-109">若要使用模拟器，只需创建此类的一个实例，并将其传递给要执行的量程操作的 `Run` 方法，同时执行其余的参数：</span><span class="sxs-lookup"><span data-stu-id="25650-109">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a><span data-ttu-id="25650-110">其他操作</span><span class="sxs-lookup"><span data-stu-id="25650-110">Other Operations</span></span>

<span data-ttu-id="25650-111">当结果操作等于 `X` 或标识时，`ToffoliSimulator` 支持旋转和指数化 Paulis，如 `R` 和 `Exp`。</span><span class="sxs-lookup"><span data-stu-id="25650-111">The `ToffoliSimulator` supports rotations and exponentiated Paulis, such as `R` and `Exp`, when the resulting operation is equal to `X` or to the identity.</span></span>

<span data-ttu-id="25650-112">支持度量和断言，但仅在 Pauli `Z`。</span><span class="sxs-lookup"><span data-stu-id="25650-112">Measurement and assert are supported, but only in the Pauli `Z` basis.</span></span>
<span data-ttu-id="25650-113">请注意，某些度量值的概率始终为0或 1;Toffoli 模拟器中没有随机性。</span><span class="sxs-lookup"><span data-stu-id="25650-113">Note that the probability of some measurement is always either 0 or 1; there is no randomness in the Toffoli simulator.</span></span>

<span data-ttu-id="25650-114">支持 `DumpMachine` 和 `DumpRegister`。</span><span class="sxs-lookup"><span data-stu-id="25650-114">`DumpMachine` and `DumpRegister` are supported.</span></span>
<span data-ttu-id="25650-115">它们都输出每个 qubit 的当前 `Z`的状态，每行一个 qubit。</span><span class="sxs-lookup"><span data-stu-id="25650-115">They both output the current `Z`-basis state of each qubit, one qubit per line.</span></span>

## <a name="qubitcount"></a><span data-ttu-id="25650-116">QubitCount</span><span class="sxs-lookup"><span data-stu-id="25650-116">QubitCount</span></span>

<span data-ttu-id="25650-117">默认情况下，`ToffoliSimulator` 为 65536 qubits 分配空间。</span><span class="sxs-lookup"><span data-stu-id="25650-117">By default, the `ToffoliSimulator` allocates space for 65,536 qubits.</span></span>
<span data-ttu-id="25650-118">如果你的算法需要超过此值，则可以通过向构造函数提供 `qubitCount` 参数的值来更改 qubit 计数。</span><span class="sxs-lookup"><span data-stu-id="25650-118">If your algorithm requires more than this, you can change the qubit count by providing a value for the `qubitCount` parameter to the constructor.</span></span>
<span data-ttu-id="25650-119">每个额外的 qubit 都需要额外的内存字节，因此，估计过高所需的 qubits 数量不会产生很大的代价。</span><span class="sxs-lookup"><span data-stu-id="25650-119">Each additional qubit requires an additional byte of memory, so there is no significant cost to overestimating the number of qubits you'll need.</span></span>

<span data-ttu-id="25650-120">例如：</span><span class="sxs-lookup"><span data-stu-id="25650-120">For example:</span></span>

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
