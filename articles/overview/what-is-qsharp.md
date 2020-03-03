---
title: 什么是 Q# 和 QDK？
description: 了解 Q#，这是 Microsoft 创建的一种用来开发量子计算机应用程序的编程语言，并且是 Microsoft Quantum 开发工具包的关键组件
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.qsharp
ms.openlocfilehash: a4bf21887e34ac85f75e5e0b9a033138464fd09d
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906995"
---
# <a name="what-are-q-and-the-qdk"></a>什么是 Q# 和 QDK？

Q# 是一种编程语言，具有专门设计用于量子计算的功能。
作为 Microsoft Quantum 开发工具包 (QDK) 的关键组件，它为量子程序员提供了一个框架，使他们能够专注于算法，而无需担心技术细节，如门序列优化或量子计算机的物理实现。

QDK 包含各种工具，这些工具为开发人员提供开始编写量子程序所需的一切。
除了 Q# 语言，QDK 还包括：
* *Q# 库*，它使开发人员可以立即成功上手并创建现实世界的量子应用程序
* 可运行 Q# 程序的各种*目标计算机*。 其中包括适用于较大量子程序的资源估算器和模拟器，以及作为无干扰量子计算机运行的全状态量子模拟器。 后者非常适用于改进构想、调试程序和了解量子物理学，但仅对量子位相对较少的程序有效。 我们非常期待将来可以使量子计算硬件用作目标计算机。
* *工具*，用于使得使用 Q# 尽可能顺畅，如 Visual Studio 和 VS Code 的扩展，以及用于 Python 和 Jupyter Notebook 的包。
* *API 文档*，用于将 Q# 与经典宿主语言（例如 Python 和 C#）配对

使用 Microsoft Quantum 开发工具包开发的应用程序通常由两个部分组成：
1. 使用 Q# 量子编程语言实现并由经典宿主程序调用的一个或多个量子算法。 其中包括 
    - Q# 操作：包含量子操作的子例程；以及 
    - Q# 函数：在量子算法内使用的经典子例程。
2. 充当主入口点的经典程序（使用 Python 或 C# 等编程语言实现）将在需要执行量子算法时调用 Q# 运算。

## <a name="write-quantum-programs-not-quantum-circuits"></a>编写量子程序，而不是量子线路

早期的量子计算时代，算法以图形（类似于经典计算中的线路图）方式表示。
虽然线路模型在量子计算研究方面一直有用，但 Microsoft 认为，开发者可以超越量子电路，使用 Q# 开发量子算法和应用程序。
使用 Q# 语言时，可以直接利用我们在数十年的经典软件开发中学到的经验，并且它还为量子开发者提供了针对量子计算的高级语言功能。

## <a name="how-does-q-work"></a>Q# 的工作原理是什么？

Q# 编程语言提供了一组直观的类型、运算和逻辑表达式来开发算法，因此使用者无需担心量子计算机的内部逻辑。

Q# 的基本构建基块之一是 `Qubit` 类型，它不能复制，也不能直接访问，就像真实的量子位。
相反，我们可以对其进行度量并将度量结果存储在 `Result` 变量中，这种 Q# 类型可以采用两个可能的值：`Zero` 和 `One`。
此类构造可保证算法始终遵守量子物理学定律，并可在量子计算机或模拟器上正常运行。

Q# 还包括经典逻辑功能（如条件和循环），这些功能又有些微不同，以确保遵循所有量子定律。
例如，约束执行循环的方式，以确保不在可能只包含确定性经典子例程的函数中调用量子运算。

Q# 程序通常与用 C# 或 Python 编写的主机程序配对使用，可以方便地整理经典代码和量子代码。
除了支持 C# 和 Python 之类的语言，QDK 还提供 IQ# Jupyter 内核，因此支持 Jupyter Notebook。

## <a name="what-can-i-use-q-for"></a>Q# 有哪些用途？

### <a name="use-q-to-learn-quantum-computing"></a>使用 Q# 学习量子计算

到目前为止，要学习量子计算，需要学习电路模型以理解量子门和度量有序序列形式的算法。 使用 Q# 时，你也可以采用另一种方式：通过编写量子程序来学习量子计算。

### <a name="use-q-to-design-quantum-algorithms"></a>使用 Q# 设计量子算法

Q# 提供了越来越多的库和用户定义类型，有助于实现各种工具并生成高级量子算法。 例如，你需要纠缠双量子位 q1 和 q2。 可以使用已内置的运算 `PrepareEntangledState([q1], [q2])`，而不是单独应用必要的门来纠缠量子位。

### <a name="use-q-to-estimate-quantum-resources"></a>使用 Q# 估算量子资源

可以使用 Quantum 开发工具包 (QDK) 随附的全状态量子模拟器模拟 Q# 程序的执行。  QDK 还提供资源模拟器，让你了解那些因太大而无法在模拟器上运行的 Q# 程序的性能。  这对算法设计者来说具有很高的价值，因为他们可以调整其程序，让其使用较少的资源（运行较少数目的量子位来执行较少数目的操作）在早期的规模较小的量子硬件上运行。

### <a name="use-q-to-validate-hardware-performance"></a>使用 Q# 验证硬件性能

Q# 的优点是，一个程序只需编写一次，然后即可在量子模拟器上进行调试性运行，以及在不同的量子计算机硬件上运行。  随着量子计算机的发展和新的量子计算机的发布，可以运行以 Q# 编写的基准程序来验证硬件性能并对结果进行比较。  

## <a name="next-steps"></a>后续步骤

* [如何了解量子计算？](xref:microsoft.quantum.overview.learn)
* [Microsoft Quantum 开发工具包入门](xref:microsoft.quantum.welcome)
