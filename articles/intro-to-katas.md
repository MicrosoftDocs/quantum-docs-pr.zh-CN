---
title: Quantum Katas 介绍
description: 了解 Microsoft Quantum 开发工具包 (QDK) 随附的 katas（培训练习）
author: natke
ms.author: nakersha
ms.date: 10/17/2019
ms.topic: overview
uid: microsoft.quantum.overview.katas
ms.openlocfilehash: 7fb8dba2a10f9a983ebee52e394260bbdc0d2f9c
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2019
ms.locfileid: "73444134"
---
# <a name="learn-quantum-computing-with-the-quantum-katas"></a>使用 Quantum Katas 学习量子计算

[Quantum Katas](https://github.com/Microsoft/QuantumKatas/) 是自定进度的开放源代码教程集合，包含一系列的编程练习，旨在同时教授量子计算的元素和 Q# 编程。

## <a name="learning-by-doing"></a>从实践中学习

此项目中收集的教程和 kata 强调从实践中学习：提供的编程任务涵盖的特定主题一开始很简单，到最后会极具挑战性。 每项任务都要求你填写一些代码；头几项任务可能只要求填写一行，而后面的任务则可能要求填写相当大的代码片段。

最重要的是，kata 包括用于设置、运行和验证任务解决方案的测试框架。 这样你就可以获取解决方案的即时反馈，在其不正确的情况下重新考虑你的方法。

可以使用 Katas 在所选环境中进行学习：

* Binder 环境中的联机 Jupyter Notebook
* 本地计算机上运行的 Jupyter Notebook
* Visual Studio
* Visual Studio Code

## <a name="what-can-i-learn-with-the-quantum-katas"></a>我可以通过 Quantum Katas 学习什么？

下面汇总了 Quantum Katas 中涵盖的主要主题。 建议刚开始时按此学习路径进行学习，确保牢固掌握量子计算的基本概念。 当然，你可以跳过自己已掌握的主题（例如复杂的算术），按自己希望的顺序学习算法。

### <a name="introduction-to-quantum-computing-concepts"></a>量子计算概念简介

* [复杂算术](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/ComplexArithmetic)
* [线性代数](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/LinearAlgebra)
* [量子位的概念](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/Qubit)
* [单量子位量子门](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/SingleQubitGates)

### <a name="quantum-computing-fundamentals"></a>量子计算基础知识

* [认识量子门](https://github.com/microsoft/QuantumKatas/tree/master/BasicGates)
* [创建量子叠加](https://github.com/microsoft/QuantumKatas/tree/master/Superposition)
* [使用度量来区分量子状态](https://github.com/microsoft/QuantumKatas/tree/master/Measurements)
* [联合度量](https://github.com/microsoft/QuantumKatas/tree/master/JointMeasurements)

### <a name="algorithms"></a>算法

* [量子隐形传送](https://github.com/microsoft/QuantumKatas/tree/master/Teleportation)
* [超密集编码](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)
* [Deutsch–Jozsa 算法](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/DeutschJozsaAlgorithm)
* [实现 Grover 的搜索算法](https://github.com/microsoft/QuantumKatas/tree/master/GroversAlgorithm)
* [探索 Grover 搜索算法的高级属性](https://github.com/microsoft/QuantumKatas/blob/master/tutorials/ExploringGroversAlgorithm)
* 使用 Grover 的算法解决实际问题：[SAT 问题](https://github.com/microsoft/QuantumKatas/blob/master/SolveSATWithGrover)和[图形着色问题](https://github.com/microsoft/QuantumKatas/blob/master/GraphColoring)

### <a name="protocols-and-libraries"></a>协议和库

* [用于量子密钥分发的 BB84 协议](https://github.com/microsoft/QuantumKatas/tree/master/KeyDistribution_BB84)
* 量子纠错：[位翻转纠错码](https://github.com/microsoft/QuantumKatas/tree/master/QEC_BitFlipCode)
* [相位估计](https://github.com/microsoft/QuantumKatas/blob/master/PhaseEstimation)
* 量子算术：[构建行波进位加法器](https://github.com/microsoft/QuantumKatas/blob/master/RippleCarryAdder)

### <a name="entanglement-games"></a>纠缠游戏

* [CHSH 游戏](https://github.com/microsoft/QuantumKatas/blob/master/CHSHGame)
* [GHZ 游戏](https://github.com/microsoft/QuantumKatas/blob/master/GHZGame)
* [Mermin-Peres 魔方游戏](https://github.com/microsoft/QuantumKatas/tree/master/MagicSquareGame)

## <a name="resources"></a>资源

* 请参阅 [Quantum Katas](https://github.com/microsoft/QuantumKatas) 全套教程
* [联机运行 kata](https://aka.ms/try-quantum-katas)
