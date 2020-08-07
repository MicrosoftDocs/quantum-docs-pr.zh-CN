---
title: Q#传授
description: 的基本概念Q#
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4f4a75cdaaa070fd763d7f75429b7c39357d25a5
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869641"
---
# <a name="no-locq-basics"></a>Q#传授

本文简要介绍了的基本构建基块 Q# 。

若要大致了解 Q# 作为量子开发工具包的基础组件的内容和位置，请参阅[什么是 Q# ？](xref:microsoft.quantum.overview.q-sharp)。 

## <a name="what-is-a-quantum-program"></a>什么是量程计划？

从技术角度来看，量子计划是一组特定的传统子例程，它们在被调用时对量程系统执行特定操作。
此视图的一个重要结果是， Q# 程序不直接对 qubits 建模，而是说明经典受控计算机如何与这些 qubits 进行交互。
按照设计，不 Q# 会直接定义量程机制的量程状态或其他属性。
例如，请考虑 "量程计算概念" 指南中讨论的状态 $ \ket{+} = \left ( \ket {0} + \ket {1} \right) /\sqrt {2} $。 [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro)
若要在中准备此状态 Q# ，请从在 $ \ket $ 状态下初始化 qubits 的事实开始 {0} ，使用 $ \ket{+} = H\ket {0} $，其中 $H $ 是由该[ `H` 操作](xref:microsoft.quantum.intrinsic.h)实现的[Hadamard 转换](xref:microsoft.quantum.glossary#hadamard)。 Q#用于初始化和转换 qubit 的基本代码如下所示：

```qsharp
using (qubit = Qubit()) {
    // At this point, the qubit is in the state |0⟩.
    H(qubit);
    // H is now applied, such that the qubit is in H|0⟩ = |+⟩, as desired.
}
```
有关初始化或*分配*qubits 的详细信息，请参阅使用[qubits](xref:microsoft.quantum.guide.qubits)。

## <a name="quantum-states-in-no-locq"></a>中的量程状态Q#

重要的是，上一程序不会显式引用中的状态， Q# 但会说明我们的程序如何*转换*状态。
使用此方法时，您可以完全不确定量程状态在每台目标*计算机上的*状态，这可能会根据计算机的不同解释。 

Q#程序无法 introspect 到 qubit 的状态。
相反，程序可以调用等操作 [`Measure`](xref:microsoft.quantum.intrinsic.measure) 来了解 qubit 中的信息，并调用操作（例如和） [`X`](xref:microsoft.quantum.intrinsic.x) [`H`](xref:microsoft.quantum.intrinsic.h) 来处理 qubit 的状态。
这些操作实际*执行*的操作仅由用于运行特定程序的目标计算机进行具体操作 Q# 。
例如，如果在我们的[全状态模拟器](xref:microsoft.quantum.machines.full-state-simulator)上运行程序，模拟器将对模拟的量程系统执行相应的数学运算。
但在将来，如果目标计算机是真实的量程计算机，则在中调用此类操作会 Q# 指示量程计算机在*真实*的量程系统上执行相应的*实际*操作，例如，精确地计时激光脉冲) 。

Q#程序按照目标计算机的定义对这些操作进行 recombines，以创建新的更高级操作来表示量程计算。
通过这种方式，可以 Q# 轻松地表达逻辑基础量程和混合量子–传统算法，同时也是对目标计算机或模拟器的结构的一般性。

## <a name="no-locq-operations-and-functions"></a>Q#操作和函数

具体而言， Q# 程序包含*操作*、*函数*和任何用户定义类型。 

操作用于描述量程系统的转换，是最基本的程序构建块 Q# 。 在中定义的每个操作 Q# 都可以调用任意数量的其他操作。

与操作不同的是，函数用于描述纯*确定性*的传统行为，在计算传统值之外不会有任何影响。 例如，假设要在程序的末尾测量 qubits，并将测量结果添加到数组中。
在这种情况下， `Measure` 是一项*操作*，指示目标计算机对 (real 或模拟) qubits 执行测量。 同时，*函数*会处理将返回结果添加到数组的传统过程。

操作和函数共同称为*callables*。 中介绍了其基础结构和行为，并详细介绍了[中 Q# 的操作和功能](xref:microsoft.quantum.guide.operationsfunctions)。


## <a name="no-locq-syntax-overview"></a>Q#语法概述

语言的语法描述形成语法正确的程序的符号的不同组合。
在中 Q# ，语法元素分为三个不同的组：类型、表达式和语句。

### <a name="types"></a>类型
Q#是一种强类型语言，因此，仔细使用类型有助于编译器在编译时提供有关程序的强大保证 Q# 。
除了标准和特定于量程的内置基元类型（如、、 `Int` 和）之外， `Bool` 还为 `Qubit` `Result` Q# 用户定义的类型提供支持。

有关所有基元类型、数组和元组类型的详细信息以及在文件中定义新类型的步骤的说明， Q# 请参阅[中 Q# 的类型](xref:microsoft.quantum.guide.types)。

### <a name="expressions"></a>表达式
编程语言中的表达式是编程语言解释并计算为特定值的一个或多个常量、变量、运算符和函数的组合。
大多数情况下，对于语言中的每个类型，该类型的表达式可以是*文本*，也可以是绑定到该类型的值的符号。
例如， `5` 是一个 `Int` 文字 (也是) 类型的表达式 `Int` ，如果符号 `count` 绑定到整数值 `5` ，则 `count` 也是整数表达式。

此外，表达式还可以包含由特定运算符组合的其他表达式。
例如，另一个 `Int` 计算结果为的表达式 `5` 为 `2+3` 。

有关中的表达式和兼容运算符的详细信息 Q# ，请参阅[中 Q# 的类型表达式](xref:microsoft.quantum.guide.expressions)。 

### <a name="statements"></a>语句 
语句是命令式编程语言的语法单元，表示要执行的操作。语句与中的表达式相比，语句不会返回结果，而只是为其副作用而执行。 然而，表达式始终返回一个结果，并且通常根本没有副作用。 简而言之， Q# 语句是在计算表达式时执行的。

中语句的一个简单示例 Q# 是将符号赋给表达式：
```qsharp
let count = 5;
```

更有趣的示例是 `for` 支持迭代并包含*语句块*的语句。
假设 `qubits` 符号绑定到) 的技术 (qubits 的寄存器 `Qubit[]` ，或类型的数组 `Qubit` 。 Then
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
是一个语句，它循环访问寄存器中的每个 qubit，并 `H` 对每个执行操作。 请注意，也 `H(qubit);` 是一条语句。

 (类型，可以使用任何类型的调用表达式， `Unit` `Unit` 不会将任何信息作为语句返回) 。
当对返回的 qubits 调用操作时，这种类型的表达式非常有用， `Unit` 因为语句的目的是修改隐式量程状态。
表达式计算语句需要终止分号。

您可以使用语句来构建程序的几乎每个方面 Q# ，而不能有任何一页包含与它们相关的所有信息。
有关其词法结构和格式设置的详细信息，请参阅[ Q# 文件结构](xref:microsoft.quantum.guide.filestructure); 有关符号绑定分配和作用域的详细信息，请参阅[ Q# 中的变量](xref:microsoft.quantum.guide.variables); 对于控制流循环（例如 `for` ），请参阅[中 Q# 的控制流](xref:microsoft.quantum.guide.controlflow)。

## <a name="next-steps"></a>后续步骤

开始了解[中的 Q# 类型](xref:microsoft.quantum.guide.types)。

有关基础知识和动机的更多背景信息 Q# ，请参阅[为什么需要这样做 Q# ？](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)。
