---
title: 'Q # 基础知识'
description: Q 的基本概念#
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
ms.openlocfilehash: 45e6f2f33dafc2aec177091d3cfa94aca14fbf0a
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415349"
---
# <a name="q-basics"></a>Q # 基础知识

本文简要介绍了 Q # 的基本构建基块。

若要大致了解 Q # 是什么，以及它作为量程开发工具包的基础组件，请参阅[什么是 q #？](xref:microsoft.quantum.overview.q-sharp)。 

## <a name="what-is-a-quantum-program"></a>什么是量程计划？

从技术角度来看，量子计划是一组特定的传统子例程，它们在被调用时对量程系统执行特定操作。
此视图的一个重要结果是，Q # 程序不直接对 qubits 建模，而是说明经典受控计算机如何与这些 qubits 进行交互。
按照设计，Q # 不会直接定义量子机制的量程状态或其他属性。
例如，考虑 {0} {1} {2} [量程计算概念](xref:microsoft.quantum.concepts.intro)指南中讨论的状态 $ \ket{+} = \left （\ket + \ket \right）/\sqrt $。
若要在 Q # 中准备此状态，请从 qubits 在 $ \ket $ 状态中初始化的事实开始 {0} ，使用 $ \ket{+} = H\ket {0} $，其中 $H $ 是由该[ `H` 操作](xref:microsoft.quantum.intrinsic.h)实现的[Hadamard 转换](xref:microsoft.quantum.glossary#hadamard)。 用于初始化和转换 qubit 的基本 Q # 代码将如下所示：

```qsharp
using (qubit = Qubit()) {
    // At this point, the qubit is in the state |0⟩.
    H(qubit);
    // H is now applied, such that the qubit is in H|0⟩ = |+⟩, as desired.
}
```
有关初始化或*分配*qubits 的详细信息，请参阅使用[qubits](xref:microsoft.quantum.guide.qubits)。

## <a name="quantum-states-in-q"></a>问答中的量程状态#

重要的是，上一程序不会显式引用 Q # 中的状态，而是说明了我们的程序如何*转换*状态。
使用此方法时，您可以完全不确定量程状态在每台目标*计算机上的*状态，这可能会根据计算机的不同解释。 

Q # 程序无法 introspect 到 qubit 的状态。
相反，程序可以调用等操作 [`Measure`](xref:microsoft.quantum.intrinsic.measure) 来了解 qubit 中的信息，并调用操作（例如和） [`X`](xref:microsoft.quantum.intrinsic.x) [`H`](xref:microsoft.quantum.intrinsic.h) 来处理 qubit 的状态。
这些操作实际*执行*的操作仅由用于运行特定 Q # 程序的目标计算机进行具体操作。
例如，如果在我们的[全状态模拟器](xref:microsoft.quantum.machines.full-state-simulator)上运行程序，模拟器将对模拟的量程系统执行相应的数学运算。
但在将来，如果目标计算机是一台真实的量程计算机，那么在 Q # 中调用此类操作会使量程计算机在*真实*的量程系统上执行相应的*实际*操作，例如，精确地计时激光脉冲。

Q # 计划 recombines 目标计算机定义的操作，以创建新的更高级操作来表示量程计算。
通过这种方式，使用 Q # 可以轻松地表达逻辑底层的量程和混合量子–传统算法，同时对目标计算机或模拟器的结构也很普遍。

## <a name="q-operations-and-functions"></a>Q # 操作和函数

具体而言，Q # 程序包含*操作*、*函数*和任何用户定义的类型。 

操作用于描述量程系统的转换，是最基本的 Q # 程序构建基块。 在 Q # 中定义的每个操作都可以调用任意数量的其他操作。

与操作不同的是，函数用于描述纯*确定性*的传统行为，在计算传统值之外不会有任何影响。 例如，假设要在程序的末尾测量 qubits，并将测量结果添加到数组中。
在这种情况下， `Measure` 是一项*操作*，指示目标计算机对（real 或模拟） qubits 执行测量。 同时，*函数*会处理将返回结果添加到数组的传统过程。

操作和函数共同称为*callables*。 [在 Q # 的操作和函数](xref:microsoft.quantum.guide.operationsfunctions)中引入了其基础结构和行为，并对其进行了详细介绍。


## <a name="q-syntax-overview"></a>Q # 语法概述

语言的语法描述形成语法正确的程序的符号的不同组合。
在 Q # 中，语法元素分为三个不同的组：类型、表达式和语句。

### <a name="types"></a>类型
Q # 是一种强类型语言，因此，仔细使用类型有助于编译器在编译时提供有关 Q # 程序的强大保证。
除了标准和特定于量程的内置基元类型，例如，、、 `Int` `Bool` `Qubit` 和 `Result` ，Q # 为用户定义的类型提供支持。

有关所有基元类型、数组和元组类型的详细信息以及在 Q # 文件中定义新类型的步骤的说明，请参阅[q # 中的类型](xref:microsoft.quantum.guide.types)。

### <a name="expressions"></a>表达式
编程语言中的表达式是编程语言解释并计算为特定值的一个或多个常量、变量、运算符和函数的组合。
大多数情况下，对于语言中的每个类型，该类型的表达式可以是*文本*，也可以是绑定到该类型的值的符号。
例如， `5` 是一个 `Int` 文本（也是类型为的表达式 `Int` ），如果符号 `count` 绑定到整数值 `5` ，则 `count` 也是整数表达式。

此外，表达式还可以包含由特定运算符组合的其他表达式。
例如，另一个 `Int` 计算结果为的表达式 `5` 为 `2+3` 。

有关 Q # 中表达式和兼容运算符的详细信息，请参阅[q # 中的类型表达式](xref:microsoft.quantum.guide.expressions)。 

### <a name="statements"></a>语句 
语句是命令式编程语言的语法单元，表示要执行的操作。语句与中的表达式相比，语句不会返回结果，而只是为其副作用而执行。 然而，表达式始终返回一个结果，并且通常根本没有副作用。 简而言之，执行 Q # 语句，而计算表达式。

Q # 中的语句的一个简单示例是向表达式赋值：
```qsharp
let count = 5;
```

更有趣的示例是 `for` 支持迭代并包含*语句块*的语句。
假设 `qubits` 符号绑定到 qubits 的寄存器（技术上的类型 `Qubit[]` 或类型的数组 `Qubit` ）。 Then
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
是一个语句，它循环访问寄存器中的每个 qubit，并 `H` 对每个执行操作。 请注意，也 `H(qubit);` 是一条语句。

您可以使用任何类型的调用表达式 `Unit` （ `Unit` 类型不会返回任何信息）作为语句。
当对返回的 qubits 调用操作时，这种类型的表达式非常有用， `Unit` 因为语句的目的是修改隐式量程状态。
表达式计算语句需要终止分号。

您可以使用语句来构建 Q # 程序的几乎每个方面，并且没有一个页面可以包含与之相关的所有信息。
有关其词法结构和格式的详细信息，请参阅[Q # 文件结构](xref:microsoft.quantum.guide.filestructure);有关符号绑定赋值和作用域，请参阅[Q # 中的变量](xref:microsoft.quantum.guide.variables)对于控制流循环（例如 `for` ），请参阅[Q # 中的控制流](xref:microsoft.quantum.guide.controlflow)。

## <a name="next-steps"></a>后续步骤

开始了解[Q # 中的类型](xref:microsoft.quantum.guide.types)。

有关 Q # 背后的基础和动机的更多背景信息，请参阅[为什么需要 q #？](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)。
