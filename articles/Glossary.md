---
title: 量程计算术语表 |Microsoft Docs
description: 量程术语术语表
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: ce15fee2be68d41f0b806be50320b562a749c3b7
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442541"
---
# <a name="quantum-computing-glossary"></a>量程计算术语表

|条款|定义|
|-------------|----------|
|Adjoint|操作的复杂共轭转置。 对于实现单一运算符的操作，adjoint 是操作的反向操作。|
|多次|操作和函数统称为 " *callables*"。|
|标准版|在 Q # 中定义的操作和函数是在 prelude 中定义的逻辑上构建的。 标准库实现对于目标计算机而言不可知。|
|Clifford 组|占用 Bloch 球的 octants 的一组操作。 其中包括： `X`、`Y`、`Z`、`H` 和 `S`|
|操控|一个量程操作，它将一个或多个 qubits 作为目标操作的启用程序。|
|Dirac 表示法|量程状态的简写形式。 有关更多详细信息，请参阅[Dirac 表示法](xref:microsoft.quantum.concepts.dirac)部分。|
|本征值和本征向量|有关详细信息，请参阅[高级矩阵部分](xref:microsoft.quantum.concepts.matrix-advanced)。|
|EPR 对|也称为[电铃状态](https://en.wikipedia.org/wiki/Bell_state)|
|演变|状态随时间变化的方式。 有关示例，请参阅 <xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials> 的部分。 |
|函数|Q # 语言中纯粹的传统例程|
| <a id="global-phase"></a>全局阶段 | 如果两个状态与一个复数 $e ^ {i\phi} $ 的倍数相同，则意味着全局阶段会有所不同。 与本地阶段不同，全局阶段不能通过任何度量来观察。 有关详细信息，请参阅[Pauli 度量值](xref:microsoft.quantum.concepts.pauli)。 |
|度量|从 qubit （或一组 qubits）获取传统位。 有关更多详细信息，请参阅[Qubit 概念](xref:microsoft.quantum.concepts.qubit)部分。|
|可变|其值在创建后可以更改的变量。|
|命名空间|相关名称集合（通常为操作、函数和类型）的标签。 例如，命名空间[`Microsoft.Quantum.Preparation`](xref:microsoft.quantum.preparation)标签在标准库中定义的可帮助准备初始状态的所有符号。|
|Operation|Q # 中的量程执行的基本单位。 它大致等效于 C、C++ 或 Python 中的函数，或者 C# 或 Java 中的静态方法。|
|操作员应用程序|执行量程运算。 这通常会将一个单一矩阵应用于当前状态向量。 有关更多详细信息，请参阅[量程概念介绍](xref:microsoft.quantum.concepts.intro)。|
|Oracle|在运行时提供量程算法的数据相关信息的子例程。 通常，目标是提供与 superposition 中的输入对应的输出 superposition。   |
|部分应用程序|调用不包含所有必需参数的函数或操作。 返回一个新的可调用，它只需要在未来的应用程序中提供的缺少参数。|
|Pauli 运算符|`X`、`Y` 和 `Z` 量程入口。|
|Prelude|由每个单独的目标计算机定义的一组基元和传统操作和函数，而不是在 Q # 级别。|
|量程线路|用于量程计算机的程序的表示形式。 有关更多详细信息，请参阅 <xref:microsoft.quantum.concepts.circuits> 部分。|
|量程状态|系统中 qubits 的表示形式。 这通常表示为复杂列向量。 有关详细信息，请参阅 <xref:microsoft.quantum.concepts.vectors>。 |
|qubit|量程存储的单位。 有关更多详细信息，请参阅 <xref:microsoft.quantum.concepts.qubit> 部分。|
|重复执行-成功|Probabilistic 成功的量程算法。 如果失败，例程将重试，直到成功（或已达到限制）。 |
|软件堆栈|一组完整的传统和量程软件以及操作量程计算机所需的编译器、模拟器和运行时。 有关更多详细信息，请参阅 <xref:microsoft.quantum.concepts.software-stack> 部分。 |
|目标计算机|一种编译目标，它将抽象的量程程序降低到硬件或模拟。 这通常包括重新编写以实现多种目的，包括门替换、用于纠错的编码、几何布局和其他功能。|
|聚合|用逗号分隔的以逗号分隔的类型。 |
|用户定义类型|可能称为单个单元的内置或以前定义的类型的集合。|

