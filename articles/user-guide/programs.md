---
title: 'Q # Introdution'
description: 问答中的量程程序简介#
author: beheim
ms.author: beheim
ms.date: 11/08/2020
ms.topic: article
uid: microsoft.quantum.guide.programs
ms.openlocfilehash: 975bcda5e0042406b465a83f17f1d2d3f5a1ec4f
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96233234"
---
# <a name="q-quantum-programming-language"></a><span data-ttu-id="364a5-103">Q # 量程编程语言</span><span class="sxs-lookup"><span data-stu-id="364a5-103">Q# Quantum Programming Language</span></span>

<span data-ttu-id="364a5-104">[问答 # 语言指南](xref:microsoft.quantum.qsharp.index)中详细介绍了有关 q # 编程语言的所有所需知识。</span><span class="sxs-lookup"><span data-stu-id="364a5-104">Everything you need to know about the Q# programming language is detailed in the [Q# language guide](xref:microsoft.quantum.qsharp.index).</span></span> <span data-ttu-id="364a5-105">与其他内容一样，我们的 [语言设计过程](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) 是开源的，我们欢迎您进行贡献。</span><span class="sxs-lookup"><span data-stu-id="364a5-105">Like anything else, our [language design process](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) is open source and we welcome contributions.</span></span>
<span data-ttu-id="364a5-106">有关 Q # 背后的基础和动机的更多背景信息，请参阅 [为什么需要 q #？](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)。</span><span class="sxs-lookup"><span data-stu-id="364a5-106">For more background about the foundations and motivation behind Q#, see [Why do we need Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span></span>  
<span data-ttu-id="364a5-107">Q # 作为量子开发工具包的一部分寄送 (QDK) 有关快速概述，请参阅 [什么是 QDK？](xref:microsoft.quantum.overview.q-sharp)。</span><span class="sxs-lookup"><span data-stu-id="364a5-107">Q# is shipped as part of the Quantum Development Kit (QDK) For a quick overview, check out [What is the QDK?](xref:microsoft.quantum.overview.q-sharp).</span></span> 

## <a name="what-is-a-quantum-program"></a><span data-ttu-id="364a5-108">什么是量程计划？</span><span class="sxs-lookup"><span data-stu-id="364a5-108">What is a quantum program?</span></span>

<span data-ttu-id="364a5-109">量程程序可以被视为一组特定的传统子例程，在调用时，可以通过与量程系统交互来执行计算;用 Q # 编写的程序不会直接对量程状态进行建模，而是说明传统控制计算机如何与 qubits 交互。</span><span class="sxs-lookup"><span data-stu-id="364a5-109">A quantum program can be seen as a particular set of classical subroutines which, when called, perform a computation by interacting with a quantum system; a program written in Q# does not directly model the quantum state, but rather describes how a classical control computer interacts with qubits.</span></span>
<span data-ttu-id="364a5-110">这使我们完全不知道量程状态在每台目标计算机 *上的* 状态，这可能会根据计算机的不同解释。</span><span class="sxs-lookup"><span data-stu-id="364a5-110">This allows us to be entirely agnostic about what a quantum state even *is* on each target machine, which might have different interpretations depending on the machine.</span></span> 

<span data-ttu-id="364a5-111">这一重要的结果是，Q # 无法直接 introspect 到 qubit 的状态或量程机制的其他属性，这可以保证可以在量程计算机上实际执行 Q # 程序。</span><span class="sxs-lookup"><span data-stu-id="364a5-111">An important consequence of that is that Q# has no ability to introspect into the state of a qubit or other properties of quantum mechanics directly, which guarantees that a Q# program can be physically executed on a quantum computer.</span></span>
<span data-ttu-id="364a5-112">相反，程序可以调用等操作 [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) 来从 qubit 中提取传统信息。</span><span class="sxs-lookup"><span data-stu-id="364a5-112">Instead, a program can call operations such as [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) to extract classical information from a qubit.</span></span>

<span data-ttu-id="364a5-113">分配后，可以将 qubit 传递到操作和函数，也称为 *callables*。</span><span class="sxs-lookup"><span data-stu-id="364a5-113">Once allocated, a qubit can be passed to operations and functions, also referred to as *callables*.</span></span> <span data-ttu-id="364a5-114">在某种意义上，这是一个 Q # 程序可以对 qubit 执行的所有操作;针对 qubit 状态的任何直接操作都由 *内部* callables 定义 [`X`](xref:Microsoft.Quantum.Intrinsic.X) ，例如和 [`H`](xref:Microsoft.Quantum.Intrinsic.H) -即 callables，其实现未在 Q # 内定义，而是由目标计算机定义。</span><span class="sxs-lookup"><span data-stu-id="364a5-114">In some sense, this is all that a Q# program can do with a qubit; Any direct actions on state of a qubit are all defined by *intrinsic* callables such as [`X`](xref:Microsoft.Quantum.Intrinsic.X) and [`H`](xref:Microsoft.Quantum.Intrinsic.H) - i.e. callables whose implementations are not defined within Q# but are instead defined by the target machine.</span></span> <span data-ttu-id="364a5-115">这些操作实际 *执行* 的操作仅由我们用于运行特定 Q # 程序的目标计算机进行具体操作。</span><span class="sxs-lookup"><span data-stu-id="364a5-115">What these operations actually *do* is only made concrete by the target machine we use to run the particular Q# program.</span></span>

<span data-ttu-id="364a5-116">例如，如果在我们的 [全状态模拟器](xref:microsoft.quantum.machines.full-state-simulator)上运行程序，模拟器将对模拟的量程系统执行相应的数学运算。</span><span class="sxs-lookup"><span data-stu-id="364a5-116">For example, if running the program on our [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), the simulator performs the corresponding mathematical operations to the simulated quantum system.</span></span>
<span data-ttu-id="364a5-117">但在将来，如果目标计算机是一台真实的量程计算机，那么在 Q # 中调用此类操作将指示量程计算机在 *实际* 的量程系统上执行相应的 *实际* 操作， (例如，精确地计时激光脉冲) 。</span><span class="sxs-lookup"><span data-stu-id="364a5-117">But looking toward the future, when the target machine is a real quantum computer, calling such operations in Q# will direct the quantum computer to perform the corresponding *real* operations on the *real* quantum system (e.g. precisely timed laser pulses).</span></span>

<span data-ttu-id="364a5-118">Q # 计划 recombines 目标计算机定义的操作，以创建新的更高级操作来表示量程计算。</span><span class="sxs-lookup"><span data-stu-id="364a5-118">A Q# program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.</span></span>
<span data-ttu-id="364a5-119">通过这种方式，使用 Q # 可以轻松地表达逻辑底层的量程和混合量子–传统算法，同时对目标计算机或模拟器的结构也很普遍。</span><span class="sxs-lookup"><span data-stu-id="364a5-119">In this way, Q# makes it easy to express the logic underlying quantum and hybrid quantum–classical algorithms, while also being general with respect to the structure of a target machine or simulator.</span></span>

<span data-ttu-id="364a5-120">一个简单的示例是下面的程序，它在 $ \ket $ 状态下分配一个 qubit {0} ，然后对其应用 Hadamard 操作 `H` 并测量结果 `PauliZ` 。</span><span class="sxs-lookup"><span data-stu-id="364a5-120">A simple example is the following program, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

```qsharp
@EntryPoint()
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // we reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, we return the result of the measurement.
        return result;
    }
}
```

<span data-ttu-id="364a5-121">我们的 [量程 Katas](https://github.com/microsoft/QuantumKatas#introduction) 提供了有关 [量程计算概念](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) （例如常见的量程操作）以及如何操作 qubits 的很好的介绍。</span><span class="sxs-lookup"><span data-stu-id="364a5-121">Our [Quantum Katas](https://github.com/microsoft/QuantumKatas#introduction) give a good introduction on [Quantum Computing Concepts](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) such as common quantum operations and how to manipulate qubits.</span></span> <span data-ttu-id="364a5-122">此外，还可以在 [内部操作和函数](xref:microsoft.quantum.libraries.standard.prelude)中找到更多示例。</span><span class="sxs-lookup"><span data-stu-id="364a5-122">More examples can also be found in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude).</span></span>



