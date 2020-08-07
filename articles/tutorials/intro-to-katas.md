---
title: Quantum Katas 介绍
description: 了解 Microsoft Quantum 开发工具包 (QDK) 随附的 katas（培训练习）
author: bradben
ms.author: bradben
ms.date: 06/02/2020
ms.topic: overview
uid: microsoft.quantum.overview.katas
no-loc:
- Q#
- $$v
ms.openlocfilehash: b2a3b25bf90109468f02c98c6c687befb83648bc
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869675"
---
# <a name="learn-quantum-computing-with-the-quantum-katas"></a>使用 Quantum Katas 学习量子计算

[量程 Katas](https://github.com/Microsoft/QuantumKatas/)是开源、自控进度的教程和编程试验，旨在同时讲授量程计算和编程的元素 Q# 。

## <a name="learning-by-doing"></a>从实践中学习

此项目中收集的教程和练习强调从实践中学习：提供的编程任务涵盖的特定主题一开始很简单，到最后会极具挑战性。 每项任务都要求你填写一些代码；头几项任务可能只要求填写一行，而后面的任务则可能要求填写相当大的代码片段。

最重要的是，katas 包括用于设置、运行和验证任务解决方案的测试框架。 这样你就可以获取解决方案的即时反馈，在其不正确的情况下重新考虑你的方法。

你可以在所选的环境中使用 katas 进行学习：

* Binder 环境中的联机 Jupyter Notebook
* 本地计算机上运行的 Jupyter Notebook
* Visual Studio
* Visual Studio Code

## <a name="what-can-i-learn-with-the-quantum-katas"></a>我可以通过 Quantum Katas 学习什么？

探索量程计算的基本知识和基础知识，或者深入了解量程算法和协议。 建议刚开始时按此学习路径进行学习，确保牢固掌握量子计算的基本概念。 当然，你可以跳过自己已掌握的主题（例如复杂的算术），按自己希望的顺序学习算法。

### <a name="introduction-to-quantum-computing-concepts"></a>量子计算概念简介

| Kata | 描述 |
|:-----|-------------|
|[复杂算术](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic)|本教程介绍了使用量程计算（如虚部和复数）所需的一些数学背景。|
|[线性代数](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra)|线性代数用于在量程计算中表示量程状态和操作。 本教程介绍基础知识，包括矩阵和矢量。|
|[量子位的概念](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/Qubit)|了解 qubits-量程计算的核心概念之一。 |
|[单量子位量子门](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/SingleQubitGates)|本教程介绍了 qubit 的量程入口，它充当量子算法的构建块并以各种方式转换量子 qubit 状态。|
|[多量子位系统](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/MultiQubitSystems)|本教程介绍了多 qubit 系统、其在数学符号和代码中的表示形式， Q# 以及牵连的概念。|
|[多 qubit 量程入口](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/MultiQubitGates)|本教程采用[qubit 量程入口](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/SingleQubitGates)教程，重点介绍如何向多 qubit 系统应用量程入口。|

### <a name="quantum-computing-fundamentals"></a>量子计算基础知识

| Kata | 描述 |
|:-----|-------------|
|[认识量子门](https://github.com/microsoft/QuantumKatas/tree/master/BasicGates)|旨在帮助你熟悉中的基本量程入口的一系列练习 Q# 。 包括基本的 qubit 和多 qubit 入口、adjoint 和控制入口的练习，以及如何使用入口来修改 qubit 的状态。|
|[创建量子叠加](https://github.com/microsoft/QuantumKatas/tree/master/Superposition)|使用这些练习，熟悉中 superposition 和编程的概念 Q# 。 包括对中基本的 qubit 和多 qubit 入口、superposition 以及 flow 控制和递归的练习 Q# 。|
|[使用度量来区分量子状态](https://github.com/microsoft/QuantumKatas/tree/master/Measurements)|解决这些练习，同时了解量程测量和正交和非正交状态。 |
|[联合度量](https://github.com/microsoft/QuantumKatas/tree/master/JointMeasurements)|了解联合奇偶校验度量值，以及如何使用[Measure](xref:microsoft.quantum.intrinsic.measure)运算来区分量程状态。|

### <a name="algorithms"></a>算法

| Kata | 描述 |
|:-----|-------------|
|[量子隐形传送](https://github.com/microsoft/QuantumKatas/tree/master/Teleportation)|此 kata 探讨了量子 teleportation-一种协议，该协议允许只使用传统通信和之前共享的量程牵连来传递量程状态。|
|[超密集编码](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)|Superdense 编码是一种协议，它允许通过使用之前共享的量程牵连只发送一个 qubit 来传输传统信息的两位。  |
|[Deutsch–Jozsa 算法](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ExploringDeutschJozsaAlgorithm)|此算法非常著名，就是一个量程算法的第一个示例，其速度比任何确定性的传统算法的速度都更快。|
|[探索 Grover 搜索算法的高级属性](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ExploringGroversAlgorithm)|对量程计算中最著名的算法之一进行了简要介绍。 它解决了在生成特定输出 (oracle) 中查找黑色框输入的问题。 |
|[实现 Grover 的搜索算法](https://github.com/microsoft/QuantumKatas/tree/master/GroversAlgorithm)|此 kata 深入更深入地探讨 Grover 的搜索算法，并介绍了如何编写 oracles，执行算法的步骤，最后将其全部放在一起。|
|[使用 Grover 的算法解决真实问题：周六问题](https://github.com/microsoft/QuantumKatas/tree/master/SolveSATWithGrover)|使用 Grover 算法解决现实问题的一系列练习，使用[布尔 satisfiability 问题](https://en.wikipedia.org/wiki/Boolean_satisfiability_problem) (周六) 作为示例。  |
|[使用 Grover 的算法解决真实问题：图形着色问题](https://github.com/microsoft/QuantumKatas/tree/master/GraphColoring)| 此 kata 进一步探讨了 Grover 的算法，这一次是解决[约束满意度问题](https://en.wikipedia.org/wiki/Constraint_satisfaction_problem)，使用图形着色问题作为示例。 |

### <a name="protocols-and-libraries"></a>协议和库

| Kata | 描述 |
|:-----|-------------|
|[用于量子密钥分发的 BB84 协议](https://github.com/microsoft/QuantumKatas/tree/master/KeyDistribution_BB84)|了解并使用 qubits 交换加密密钥，实现[BB84](https://en.wikipedia.org/wiki/BB84)的量程密钥分发协议。 |
|[位翻转纠错代码](https://github.com/microsoft/QuantumKatas/tree/master/QEC_BitFlipCode)|利用量程错误更正中最简单的量程错误更正来探索量程错误更正 (QEC) 代码-三 qubit 位翻转代码。|
|[相位估计](https://github.com/microsoft/QuantumKatas/blob/master/PhaseEstimation)|阶段估算算法是量程计算的一些最基本的构建基块。 通过这些练习来了解阶段估算，这些练习涵盖了量程阶段估算以及如何在中准备和运行阶段估算例程 Q# 。|
|[量程算法：构建 ripple-携带添加器](https://github.com/microsoft/QuantumKatas/blob/master/RippleCarryAdder)|探讨[波纹](https://en.wikipedia.org/wiki/Adder_(electronics)#Ripple-carry_adder)在量程计算机上添加的深入演练系列。 构建就地量程增加程序，使用不同的算法对其进行扩展，最后构建一个就地量程 subtractor。   |

### <a name="entanglement-games"></a>纠缠游戏

| Kata | 描述 |
|:-----|-------------|
|[CHSH 游戏](https://github.com/microsoft/QuantumKatas/tree/master/CHSHGame)|使用[CHSH](https://en.wikipedia.org/wiki/CHSH_inequality)游戏的实现来浏览量程牵连。 这一非本非[本地](https://en.wikipedia.org/wiki/Quantum_refereed_game)游戏显示了如何使用量程牵连来增加玩家的机会，使其超出了使用纯粹的传统策略可能会发生的可能性。|
|[GHZ 游戏](https://github.com/microsoft/QuantumKatas/tree/master/GHZGame)|GHZ 游戏是另一个非本地游戏，但涉及三个玩家。|
|[Mermin-Peres 魔方游戏](https://github.com/microsoft/QuantumKatas/tree/master/MagicSquareGame)|一系列练习，探讨了[量子伪 telepathy](https://en.wikipedia.org/wiki/Quantum_pseudo-telepathy#The_Mermin%E2%80%93Peres_magic_square_game)来解决幻方形游戏。  |

## <a name="resources"></a>资源

请参阅 [Quantum Katas](https://github.com/microsoft/QuantumKatas) 全套教程

[联机运行 kata](https://aka.ms/try-quantum-katas)
