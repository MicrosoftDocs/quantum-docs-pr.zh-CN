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
# <a name="q-quantum-programming-language"></a>Q # 量程编程语言

[问答 # 语言指南](xref:microsoft.quantum.qsharp.index)中详细介绍了有关 q # 编程语言的所有所需知识。 与其他内容一样，我们的 [语言设计过程](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) 是开源的，我们欢迎您进行贡献。
有关 Q # 背后的基础和动机的更多背景信息，请参阅 [为什么需要 q #？](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)。  
Q # 作为量子开发工具包的一部分寄送 (QDK) 有关快速概述，请参阅 [什么是 QDK？](xref:microsoft.quantum.overview.q-sharp)。 

## <a name="what-is-a-quantum-program"></a>什么是量程计划？

量程程序可以被视为一组特定的传统子例程，在调用时，可以通过与量程系统交互来执行计算;用 Q # 编写的程序不会直接对量程状态进行建模，而是说明传统控制计算机如何与 qubits 交互。
这使我们完全不知道量程状态在每台目标计算机 *上的* 状态，这可能会根据计算机的不同解释。 

这一重要的结果是，Q # 无法直接 introspect 到 qubit 的状态或量程机制的其他属性，这可以保证可以在量程计算机上实际执行 Q # 程序。
相反，程序可以调用等操作 [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) 来从 qubit 中提取传统信息。

分配后，可以将 qubit 传递到操作和函数，也称为 *callables*。 在某种意义上，这是一个 Q # 程序可以对 qubit 执行的所有操作;针对 qubit 状态的任何直接操作都由 *内部* callables 定义 [`X`](xref:Microsoft.Quantum.Intrinsic.X) ，例如和 [`H`](xref:Microsoft.Quantum.Intrinsic.H) -即 callables，其实现未在 Q # 内定义，而是由目标计算机定义。 这些操作实际 *执行* 的操作仅由我们用于运行特定 Q # 程序的目标计算机进行具体操作。

例如，如果在我们的 [全状态模拟器](xref:microsoft.quantum.machines.full-state-simulator)上运行程序，模拟器将对模拟的量程系统执行相应的数学运算。
但在将来，如果目标计算机是一台真实的量程计算机，那么在 Q # 中调用此类操作将指示量程计算机在 *实际* 的量程系统上执行相应的 *实际* 操作， (例如，精确地计时激光脉冲) 。

Q # 计划 recombines 目标计算机定义的操作，以创建新的更高级操作来表示量程计算。
通过这种方式，使用 Q # 可以轻松地表达逻辑底层的量程和混合量子–传统算法，同时对目标计算机或模拟器的结构也很普遍。

一个简单的示例是下面的程序，它在 $ \ket $ 状态下分配一个 qubit {0} ，然后对其应用 Hadamard 操作 `H` 并测量结果 `PauliZ` 。

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

我们的 [量程 Katas](https://github.com/microsoft/QuantumKatas#introduction) 提供了有关 [量程计算概念](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) （例如常见的量程操作）以及如何操作 qubits 的很好的介绍。 此外，还可以在 [内部操作和函数](xref:microsoft.quantum.libraries.standard.prelude)中找到更多示例。



