---
uid: microsoft.quantum.welcome
title: Quantum 开发工具包 (QDK) 入门
description: 了解如何通过 Quantum 开发工具包 (QDK) 开始在 Q# 中编写量子项目程序。
author: bradben
ms.author: v-benbra
ms.date: 9/29/2020
ms.topic: quickstart
no-loc:
- Q#
- $$v
ms.openlocfilehash: 62910becb5b3c7415ac575217230b6c8be55fd7e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858861"
---
# <a name="get-started-with-the-quantum-development-kit-qdk"></a>Quantum 开发工具包 (QDK) 入门

欢迎使用 Microsoft Quantum 开发工具包！  

Quantum 开发工具包 (QDK) 包含使用 Q#（一种专为量子应用程序开发而设计的编程语言）构建你自己的量子程序和试验所需的所有工具。

若想直接开始使用，请先阅读 [QDK 设置指南](xref:microsoft.quantum.install)。
可以按照指南在 Windows、Linux 或 MacOS 计算机上设置 Quantum 开发工具包，以便编写你自己的量子程序。

如果你对量子计算不熟悉，请查看[概述](xref:microsoft.quantum.overview.introduction)部分，了解量子计算机可执行的操作以及量子计算的基本知识。

## <a name="get-started-programming"></a>编程入门

Quantum 开发工具包提供了许多方法，方便你了解如何使用 Q# 开发量子程序。
若要快速掌握量子计算的内容，你可以尝试使用以下教程：

* [量子随机数生成器](xref:microsoft.quantum.quickstarts.qrng) - 从“Q# Hello World”样式的应用程序开始，它简单介绍了量子概念，让你可在数分钟内构建并运行一个量子应用程序。
* [通过 Q# 探索纠缠](xref:microsoft.quantum.write-program) - 本教程指导你编写一个 Q# 程序，用于演示量子编程的一些基本概念。 如果尚未做好开始编码的准备，你仍可在不安装 QDK 的情况下继续阅读本指南，大致了解 Q# 编程语言和基本的量子计算概念。
* [Grover 搜索算法](xref:microsoft.quantum.quickstarts.search) - 探索此 Q# 程序示例，让你了解 Q# 以抽象低级量子操作的方式表达量子算法的强大功能。 本教程将指导你使用 Visual Studio 或 Visual Studio Code 将程序开发为 Q# 应用程序。

## <a name="learning-further"></a>深入学习
* Microsoft Learn 提供了关于量子计算的免费联机培训。 [Quantum 计算基础知识](https://docs.microsoft.com/learn/paths/quantum-computing-fundamentals/)学习路径介绍了量子计算和量子算法的基本概念，让你能够使用 Q# 开始构建量子程序。
* 若要深入了解 Q# 编程，请查看 [Quantum Katas](https://github.com/Microsoft/QuantumKatas) - 一系列自控进度的编程练习，介绍了如何通过 Q# 中的编程练习进行量子计算。 其中的许多 Katas 也作为 Q# Notebooks 提供。 
* 我们的[示例存储库](https://github.com/Microsoft/Quantum)展示了多个示例，这些示例介绍如何使用 Q# 编写量子程序。 这其中的大多数示例都使用开源[量子库](https://github.com/Microsoft/QuantumLibraries)编写，包括我们的[标准](xref:microsoft.quantum.libraries.standard.intro)库和[化学](xref:microsoft.quantum.chemistry.concepts.intro)库（详见下文）。

## <a name="key-concepts-for-quantum-computing"></a>量子计算的关键概念

如果你是量子开发方面的新手，可能会觉得这些问题有点令人头疼。 这些关键概念旨在帮助你走进量子世界，并了解量子计算与经典计算的不同之处。

* [了解量子计算](xref:microsoft.quantum.overview.understanding)
* [量子计算机和量子模拟器](xref:microsoft.quantum.overview.simulators)
* [什么是 Q# 编程语言和 QDK？](xref:microsoft.quantum.overview.q-sharp)
* [用于量子计算的线性代数](xref:microsoft.quantum.overview.algebra)

## <a name="quantum-development-kit-documentation"></a>Quantum 开发工具包文档

当前文档包括以下额外主题。

### <a name="no-locq-developer-guides"></a>Q# 开发人员指南

* [Q# 用户指南](xref:microsoft.quantum.guide)详细介绍了用于使用 Q# 创建量子程序的核心概念。
* [量子模拟器和主机应用程序](xref:microsoft.quantum.machines)介绍了量子算法是如何运行的、哪些量子计算机可供使用，以及如何为量子程序编写非 Q# 驱动程序。

### <a name="no-locq-libraries"></a>Q# 库

* [Q# 标准库](xref:microsoft.quantum.libraries.standard.intro)介绍了支持经典语言控件要求和 Q# 量子算法的操作和函数。 
    主题包括控制流、数据结构、错误更正、测试和调试。 
* [Q# 化学库](xref:microsoft.quantum.chemistry.concepts.intro)介绍了支持量子化学模拟（量子计算的关键应用）的操作和函数。 主题包括：模拟 Hamiltonian 动力学、量子相位估计，等等。
* [Q# 数字库](xref:microsoft.quantum.numerics.intro)介绍的操作和函数支持以目标计算机的本机操作来表达复杂的算术函数。
* [Q# 库参考](xref:microsoft.quantum.apiref-intro)包含按命名空间划分的库实体的参考信息。

### <a name="general-quantum-computing"></a>常规量子计算

* [量子计算概念](xref:microsoft.quantum.concepts.intro)包含下述主题：线性代数与量子计算的相关性、量子位的性质和使用、如何读取量子线路，等等。
* [量子计算术语表](xref:microsoft.quantum.glossary)是一个术语表，包含一些特定于量子计算和程序开发的重要术语。
    如果你不熟悉此领域，则可在阅读我们的文档时参考它。
* [延伸阅读](xref:microsoft.quantum.more-information)包含经过甄选的参考文档，深入介绍了各种量子计算主题。

### <a name="additional-info"></a>其他信息

* [Microsoft Quantum 开发工具包发行说明](xref:microsoft.quantum.relnotes)。


## <a name="be-a-part-of-the-no-locq-open-source-community"></a>加入 Q# 开源社区

Quantum 开发工具包是一种开源开发工具包，目的是方便开发人员进行量子计算，解决世界上最紧迫的一些难题。  需要开源软件的学术机构将能够部署 Q# 进行量子学习和开发。 将开发工具包开源也方便开发人员和领域专家通过其代码来贡献各种改进和创意。

你对 Quantum 开发工具包的反馈、参与和贡献很重要。  如需详细了解 Quantum 开发工具包源、提供反馈、了解如何参与这个不断发展的量子开发平台的决策并贡献力量，请参阅[为 Quantum 开发工具包做贡献](xref:microsoft.quantum.contributing)。

有关 Microsoft 推出的量子计算计划的更多常规信息，请参阅 [Microsoft Quantum](https://www.microsoft.com/en-us/quantum/)。
