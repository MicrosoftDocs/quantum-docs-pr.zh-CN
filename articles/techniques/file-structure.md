---
title: 'Q # 计划概述-Q # 技术 |Microsoft Docs'
description: 'Q # 计划概述-Q # 技术'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.file-structure
ms.openlocfilehash: e8f52e6b0d4382331665a8e845ef19a3a1beabf9
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820821"
---
# <a name="q-program-overview"></a>Q# 编程概述

Q # 是一种可扩展的多模式域特定编程语言，用于量程计算。 Q # 是一种量程编程语言，因为它可用于描述在量程计算机上执行指令的方式。 可从模拟器到实际的量程硬件的目标计算机。 Q # 是可缩放的：它可用于编写简单的演示程序，如在几个 qubits 上运行的传送，但也支持编写大量复杂的程序，例如模拟复杂的分子，这些程序需要使用数百万的 qubits 大型计算机。 即使大型物理计算机仍在将来，Q # 也能让程序员立即对复杂的量程算法进行编程。 此外，Q # 支持各种任务，如调试、分析、资源估算，以及以可缩放方式进行的特定用途模拟。 

从技术角度看，可以将量程程序视为一组特定的传统函数，在调用这些函数时，会生成量程线路作为其副作用。 此视图的一个重要结果是，以 Q # 编写的程序不会直接对 qubits 建模，而是介绍传统的控制计算机如何与这些 qubits 交互。
按照设计，Q # 不会直接定义量程机制的量程状态或其他属性，而是通过语言中定义的各种子例程的操作间接定义。
例如，请考虑[量程计算概念](xref:microsoft.quantum.concepts.intro)指南中讨论的状态 $ \ket{+} = \left （\ket{0} + \ket{1}\right）/\sqrt{2}$。
若要在 Q # 中准备此状态，我们将使用在 $ \ket{0}$ 状态下初始化 qubits 的事实，并使用 $ \ket{+} = H\ket{0}$，其中 $H $ 是 Hadamard 转换：

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0〉.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0〉 = |+〉, as we wanted.
}
```
## <a name="q-tranformations-of-quantum-states"></a>Q # 状态的转换

重要的是，在编写上述程序时，我们未显式引用 Q # 中的状态，而是说明了该状态是由程序*转换*的。
因此，与图形着色器程序将转换说明累积到每个顶点的方式类似，Q # 中的量程计划将转换为量程状态。
这使我们完全不知道量程状态在每台目标计算机*上的*状态，这可能会根据计算机的不同解释。 

从 Q # 程序的角度来看，qubit 是对目标计算机内部结构的完全不透明引用。
Q # 程序无法 introspect qubit 的状态、其在目标计算机上的表示形式，甚至与该程序提供的任何其他 qubit 相同 qubit。
相反，程序可以调用 `Measure` 等操作来了解 qubit 中的信息，并调用操作（例如 `X` 和 `H`）来操作 qubit 的状态。
这些操作在语言中没有内部定义，只是用于运行特定 Q # 程序的目标计算机。
Q # 计划 recombines 目标计算机定义的操作，以创建新的更高级操作来表示量程计算。
通过这种方式，使用 Q # 可以轻松地表达逻辑基础量程和混合量子-传统算法，同时也是对目标计算机或模拟器的结构的一般性。

## <a name="q-operations-and-functions"></a>Q # 操作和函数

具体而言，Q # 程序由一个或多个*操作*、一个或多个*函数*和用户定义的类型组成。 操作用于描述量程计算机状态的转换，是 Q # 程序的最基本构建基块。 在 Q # 中定义的每个操作都可以调用任意数量的其他操作，包括由目标计算机实现的内置*内部*操作。
在编译时，每个操作都表示为可提供给目标计算机的 .NET 类类型。

与操作不同的是，函数用于描述纯粹的传统行为，在计算经典输出值以外，不会产生任何影响。 Q # 是一种强类型语言，附带一组内置的基元类型以及对用户定义类型的支持。 

在本指南的其余部分，我们将了解如何使用不同的语言概念和构造，帮助我们通过操作、函数和类型的基本构建块来定义复杂的量程程序。 

## <a name="structure-of-q-source-files"></a>Q # 源文件的结构

Q # 源文件至少包含一个*命名空间声明*，该声明指定 .net 命名空间，该命名空间将包含源文件中的定义。
可以使用 `open` 语句包含其他 Q # 源文件和库中的定义。
例如，大多数定义基本入口的操作都在 <xref:microsoft.quantum.intrinsic> 命名空间中定义。
为了使其可供我们的代码使用，只需在每个文件的顶部 `open` 该命名空间即可：

```qsharp
namespace Example {
    open Microsoft.Quantum.Intrinsic;

    // ...
}
```

在命名空间中，每个 Q # 源文件可以定义*操作*、*函数*和*用户定义类型*的任意组合。
本部分的其余部分将依次介绍每个，并提供一些示例，说明如何在实践中使用它们来做出有用的量程计划。
