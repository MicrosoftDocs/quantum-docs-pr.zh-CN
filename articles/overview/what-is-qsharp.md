---
title: 什么是 Q#？
description: 了解如何使用 Microsoft 创建的编程语言 Q# 来开发量子计算机应用程序
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.qsharp
ms.openlocfilehash: 3fd288439c7db7f939240b4388c9cdb114b6535c
ms.sourcegitcommit: edcf15044d7bdf4f8b21fb8f6af4bde475eb13a0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2019
ms.locfileid: "73529986"
---
# <a name="what-is-q"></a>什么是 Q#？

Q# 是一种编程语言，具有量子计算特有的功能。

Q# 为量子程序员提供了一个框架，使他们能够专注于算法，而无需考虑技术细节，如门序列优化或量子计算机的物理实现。

Q# 编程语言提供了一组直观的类型、运算和逻辑表达式来开发算法，因此使用者无需担心量子计算机的内部逻辑。

## <a name="code-algorithms"></a>代码算法

早期的量子计算时代，算法以图形（类似于经典计算中的线路图）方式表示。  虽然线路模型在量子计算研究方面一直有用，但 Microsoft 认为，开发者可以超越量子电路，使用 Q# 开发量子算法和应用程序。 使用 Q# 语言时，可以直接利用我们在数十年的经典软件开发中学到的经验，并且它还为量子开发者提供了针对量子计算的高级语言功能。


## <a name="how-does-q-work"></a>Q# 的工作原理是什么？

Q# 的基本构建基块之一是 `Qubit` 类型，它不能复制，也不能直接访问，就像真实的量子位。 相反，我们可以对其进行度量并将度量结果存储在 `Result` 变量中，这种 Q# 类型可以采用两个可能的值：`Zero` 和 `One`。 此类构造可保证算法始终遵守量子物理学定律，并可在量子计算机或模拟器上正常运行。

Q# 还包括经典逻辑功能（如条件或循环），这些功能又有些微不同，以确保遵循所有量子定律。 例如，对循环执行方式进行约束，确保量子操作也是如此。

Q# 程序通常与用 C# 或 Python 编写的主机程序配对使用，可以方便地整理经典代码和量子代码。 除了支持 C# 和 Python 之类的语言，QDK 还提供 IQ# Jupyter 内核，因此支持 Jupyter Notebook。

## <a name="use-q-to-learn-quantum-computing"></a>使用 Q# 学习量子计算

到目前为止，要学习量子计算，需要学习电路模型以理解量子门和度量有序序列形式的算法。 使用 Q# 时，你也可以采用另一种方式：通过编写量子程序来学习量子计算。

## <a name="use-q-to-design-quantum-algorithms"></a>使用 Q# 设计量子算法

Q# 提供了越来越多的库和用户定义类型，有助于实现各种工具并生成高级量子算法。 例如，你需要纠缠双量子位 q1 和 q2。 可以使用已内置的运算 `PrepareEntangledState([q1], [q2])`，而不是单独应用必要的门来纠缠量子位。

## <a name="use-q-to-estimate-quantum-resources"></a>使用 Q# 估算量子资源

可以使用 Quantum 开发工具包 (QDK) 随附的全状态量子模拟器模拟 Q# 程序的执行。  QDK 还提供资源模拟器，让你了解那些因太大而无法在模拟器上运行的 Q# 程序的性能。  这对算法设计者来说具有很高的价值，因为他们可以调整其程序，让其使用较少的资源（运行较少数目的量子位来执行较少数目的操作）在早期的规模较小的量子硬件上运行。

## <a name="use-q-to-validate-hardware-performance"></a>使用 Q# 验证硬件性能

Q# 的优点是，一个程序只需编写一次，然后即可在量子模拟器上进行调试性运行，以及在不同的量子计算机硬件上运行。  随着量子计算机的发展和新的量子计算机的发布，可以运行以 Q# 编写的基准程序来验证硬件性能并对结果进行比较。  

## <a name="next-steps"></a>后续步骤

* [如何学习量子计算？](xref:microsoft.quantum.overview.learn)
* [Microsoft Quantum 开发工具包入门](xref:microsoft.quantum.welcome)
