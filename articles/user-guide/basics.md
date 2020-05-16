---
title: 'Q # 基础知识'
description: Q 的基本概念#
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
ms.openlocfilehash: fd0ea47f00b1456ec460808ef7d451c8427677cd
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431149"
---
# <a name="q-basics"></a>Q # 基础知识

在本部分中，我们将简要介绍 Q # 的基本构建基块。

若要快速了解 Q # 的作用，以及它作为量程开发工具包的基础组件在哪里，可以查看[问 #？](xref:microsoft.quantum.overview.q-sharp)。 

## <a name="what-is-a-quantum-program"></a>什么是量程计划？

从技术角度看，可以将量程程序视为一组特定的传统子例程，在调用该程序时，会在量程系统上执行特定操作。
此视图的一个重要结果是，以 Q # 编写的程序不会直接对 qubits 建模，而是介绍传统的控制计算机如何与这些 qubits 交互。
按照设计，Q # 不会直接定义量子机制的量程状态或其他属性。
例如，考虑 {0} {1} {2} [量程计算概念](xref:microsoft.quantum.concepts.intro)指南中讨论的状态 $ \ket{+} = \left （\ket + \ket \right）/\sqrt $。
若要在 Q # 中准备此状态，我们将使用在 $ \ket $ 状态下初始化 qubits 的事实 {0} ，并使用 $ \ket{+} = H\ket {0} $，其中 $H $ 是由 [ `H` operation] （] （Hadamard：）实现的 x 转换：

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0⟩.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0⟩ = |+⟩, as we wanted.
}
```

## <a name="quantum-states-in-q"></a>问答中的量程状态#

重要的是，在编写上述程序时，我们未显式引用 Q # 中的状态，而是说明了该状态是由程序*转换*的。
这使我们完全不知道量程状态在每台目标计算机*上的*状态，这可能会根据计算机的不同解释。 

Q # 程序无法 introspect 到 qubit 的状态。
相反，程序可以调用等操作 [`Measure`](xref:microsoft.quantum.intrinsic.measure) 来了解 qubit 中的信息，并调用操作（例如和） [`X`](xref:microsoft.quantum.intrinsic.x) [`H`](xref:microsoft.quantum.intrinsic.h) 来处理 qubit 的状态。
这些操作实际*执行*的操作仅由我们用于运行特定 Q # 程序的目标计算机进行具体操作。
例如，如果在我们的[全状态模拟器](xref:microsoft.quantum.machines.full-state-simulator)上运行程序，模拟器将对模拟的量程系统执行相应的数学运算。
但在将来，如果目标计算机是一台真实的量程计算机，则在 Q # 中调用此类操作将指示量程计算机在*实际*的量程系统上执行相应的*实际*操作（例如，精确地计时激光脉冲）。

Q # 计划 recombines 目标计算机定义的操作，以创建新的更高级操作来表示量程计算。
通过这种方式，使用 Q # 可以轻松地表达逻辑底层的量程和混合量子–传统算法，同时对目标计算机或模拟器的结构也很普遍。

## <a name="q-operations-and-functions"></a>Q # 操作和函数

具体而言，Q # 程序由*操作*、*函数*和任何用户定义的类型组成。 

操作用于描述量程系统的转换，是最基本的 Q # 程序构建基块。 在 Q # 中定义的每个操作都可以调用任意数量的其他操作。

与操作不同的是，函数用于描述纯*确定性*的传统行为，在计算传统值之外不会有任何影响。 例如，假设我们想要在程序的末尾测量 qubits，并将测量结果添加到数组中。
在这种情况下， `Measure` *操作*会指示目标计算机对（real 或模拟） qubits 执行度量，将返回结果添加到数组的传统过程将由*函数*进行处理。

同时，操作和函数称为*callables*，它们的基础结构和行为是在 "Q #" 页的 "[操作和函数" 中](xref:microsoft.quantum.guide.operationsfunctions)引入的。


## <a name="q-syntax-overview"></a>Q # 语法概述

语言的语法描述形成语法正确的程序的符号的不同组合。
在 Q # 中，我们可以将其语法的元素分类为三个不同的组：类型、表达式和语句。

### <a name="types"></a>类型
Q # 是一种强类型语言，因此，仔细使用类型有助于编译器在编译时提供有关 Q # 程序的强大保证。
除了标准和特定于量程的内置基元类型（如、、 `Int` `Bool` `Qubit` 和 `Result` ），Q # 还提供对用户定义类型的支持。
所有 Q # 的各种基元类型都在 " [q #](xref:microsoft.quantum.guide.types) " 页上的 "类型" 中进行了介绍，以及有关数组和元组类型的详细信息，以及如何在 Q # 文件中定义新类型。

### <a name="expressions"></a>表达式
编程语言中的表达式是编程语言解释并计算为特定值的一个或多个常量、变量、运算符和函数的组合。
大多数情况下，对于语言中的每个类型，该类型的表达式可以是*文本*，也可以是绑定到该类型的值的符号。
例如， `5` 是一个 `Int` 文本（也是类型为的表达式 `Int` ），如果符号 `count` 绑定到整数值 `5` ，则 `count` 也是整数表达式。

此外，表达式还可以包含与特定运算符组合在一起的其他表达式。
因此，计算结果为的表达式的另一个示例 `Int` `5` 是 `2+3` 。

可以使用 Q # 中的类型表达式以及可用于形成它们的兼容运算符，详细介绍了 "Q #" 页中的[类型表达式](xref:microsoft.quantum.guide.expressions)。 

### <a name="statements"></a>语句 
语句是命令式编程语言的语法单元，表示要执行的操作。语句与中的表达式相比，语句不会返回结果，而是只为其副作用而执行，而表达式始终返回结果，并且通常根本没有副作用。
这种区别经常以措辞来观察：计算表达式，而执行语句。

Q # 中的语句的一个非常基本的示例是为表达式赋值：
```qsharp
let count = 5;
```

更有趣的例子是 `for` 支持迭代的语句，并包含*语句块*。
假设 `qubits` 符号绑定到 qubits 的寄存器（技术上的类型 `Qubit[]` ，即类型的数组 `Qubit` ）。 Then
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
是一个语句，它循环访问寄存器中的每个 qubit，并 `H` 对每个执行操作。 请注意，也 `H(qubit);` 是一条语句。

事实上，任何类型的调用表达式 `Unit` （不返回任何信息的 callables）都可以用作语句。
这主要是在对返回的 qubits 调用操作时使用的， `Unit` 因为语句的目的是修改隐式量程状态。
表达式计算语句需要终止分号。

问答 # 程序的几乎每个方面都是使用语句构建的，因此，任何一个页面都不能包含与它们相关的所有信息。
但是，其词法结构和格式在 q [# 文件结构](xref:microsoft.quantum.guide.filestructure)页、符号绑定分配和[q # 中的变量](xref:microsoft.quantum.guide.variables)的范围和控制流循环（如 `for` [q # 中的控制流）中](xref:microsoft.quantum.guide.controlflow)进行了介绍。


## <a name="whats-next"></a>后续步骤
在本指南的其余部分，我们将向您展示如何使用 Q # 通过操作、函数和类型的基本构建块来构建复杂的量程程序。

若要开始，可以开始了解[Q # 中的类型](xref:microsoft.quantum.guide.types)。

如果有兴趣了解有关 Q # 背后的基础和动机的详细信息，请查看[我们为什么需要 q #？](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)。
