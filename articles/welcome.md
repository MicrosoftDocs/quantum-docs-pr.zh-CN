---
uid: microsoft.quantum.welcome
title: Quantum 开发工具包 (QDK) 入门
description: 了解 QDK 入门方法。
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: overview
ms.openlocfilehash: 066981e3e2fb468c1ff2a4cf4d3e7cff057772ab
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036332"
---
# <a name="get-started-with-the-quantum-development-kit-qdk"></a>Quantum 开发工具包 (QDK) 入门

欢迎使用 Microsoft Quantum 开发工具包！  
QDK 包含使用 Q#（一种专为量子应用程序开发而设计的编程语言）构建你自己的量子程序和试验所需的所有工具。 

若要开始使用，可以转到 [QDK 安装指南](xref:microsoft.quantum.install)。
然后，可以按指南在 Windows、Linux 或 MacOS 计算机上安装 Quantum 开发工具包，以便编写你自己的量子程序。

如果不想立即开始编写代码，但想要详细了解量子计算和 Q#，建议继续阅读本文，了解可以使用的资源。 在[关于量子计算的五个问题](#five-questions-about-quantum-computing)部分，可以找到准确指向你要查找的内容的链接！

## <a name="get-started-programming"></a>编程入门

Quantum 开发工具包提供了许多方法，方便你了解如何使用 Q# 开发量子程序。
若要快速掌握量子计算的内容，可以试用*快速入门*：

* [量子随机数生成器](xref:microsoft.quantum.quickstarts.qrng)是“Q# Hello World”样式的应用程序，它简单介绍了量子概念，让你在数分钟内构建并运行一个量子应用程序。
* [Q# 的量子基础知识](xref:microsoft.quantum.write-program)指导你编写一个 Q# 程序，用于演示量子编程的一些基本概念。 
    如果尚未做好开始编码的准备，你仍然可以在不安装 QDK 的情况下继续阅读本指南，大致了解 Q# 编程语言和基本的量子计算概念。
* [Grover 搜索算法](xref:microsoft.quantum.quickstarts.search)提供了 Q# 程序示例，让你了解 Q# 以抽象低级量子操作的方式表达量子算法的强大功能。 
    本快速入门指导你使用各种编程环境（Python 主机、.NET 语言主机、Visual Studio 或 Visual Studio Code）来开发程序。

### <a name="learning-further"></a>深入学习
* 若要深入了解 Q# 编程，请查看[量子 Katas](https://github.com/Microsoft/QuantumKatas) - 一系列自控进度的编程练习，介绍了如何通过 Q# 中的编程练习进行量子计算。
    其中的许多 Katas 也作为 Q# Notebooks 提供。 
* 我们的[示例存储库](https://github.com/Microsoft/Quantum)展示了多个示例，这些示例介绍如何使用 Q# 编写量子程序。 这其中的大多数示例都使用开源[量子库](https://github.com/Microsoft/QuantumLibraries)编写，包括我们的[标准](xref:microsoft.quantum.libraries.standard.intro)库和[化学](xref:microsoft.quantum.chemistry.concepts.intro)库（详见下文）。

## <a name="five-questions-about-quantum-computing"></a>关于量子计算的五个问题

如果你是量子开发方面的新手，可能会觉得这些问题有点令人头疼。 我们提供了相关资源，帮助你开始了解量子计算。 在这些简短文章的帮助下，我们相信你会渴望立即开始编程。
* [什么是量子计算？](xref:microsoft.quantum.overview.what)
* [量子计算机有何用途？](xref:microsoft.quantum.overview.computers)
* [为何学习量子计算？](xref:microsoft.quantum.overview.why)
* [什么是 Q#？](xref:microsoft.quantum.overview.qsharp)
* [如何使用 Q# 学习量子计算](xref:microsoft.quantum.overview.learn)

## <a name="quantum-development-kit-documentation"></a>Quantum 开发工具包文档

当前文档包括以下额外主题。

### <a name="using-q"></a>使用 Q#
* [量子开发技术](xref:microsoft.quantum.techniques.intro)详述了用于在 Q# 中创建量子程序的核心概念。 主题包括文件结构、操作和函数、量子位的使用，以及一些高级主题。
* [Q# 语言参考](xref:microsoft.quantum.language.intro)详述了 Q# 语言，具体内容包括：类型模型、表达式、语句和编译器使用。
* [量子模拟器和主机应用程序](xref:microsoft.quantum.machines)介绍了如何执行量子算法、可用的量子计算机，以及如何为量子程序编写非 Q# 驱动程序。

### <a name="q-libraries"></a>Q# 库
* [Q# 标准库](xref:microsoft.quantum.libraries.standard.intro)介绍了支持经典语言控件要求和 Q# 量子算法的操作和函数。 
    主题包括控制流、数据结构、错误更正、测试和调试。 
* [Q# 化学库](xref:microsoft.quantum.chemistry.concepts.intro)介绍了支持量子化学模拟（量子计算的关键应用）的操作和函数。 主题包括：模拟 Hamiltonian 动力学、量子相位估计，等等。
* [Q# 数字库](xref:microsoft.quantum.numerics.intro)介绍的操作和函数支持以目标计算机的本机操作来表达复杂的算术函数。
* [Q# 库参考](xref:microsoft.quantum.standardlibsintro)包含按命名空间划分的库实体的参考信息。

### <a name="general-quantum-computing"></a>常规量子计算
* [量子计算概念](xref:microsoft.quantum.concepts.intro)包含下述主题：线性代数与量子计算的相关性、量子位的性质和使用、如何读取量子线路，等等。
* [量子计算术语表](xref:microsoft.quantum.glossary)是一个术语表，包含一些特定于量子计算和程序开发的重要术语。 
    如果你不熟悉此领域，则可在阅读我们的文档时参考它。
* [延伸阅读](xref:microsoft.quantum.more-information)包含经过甄选的参考文档，深入介绍了各种量子计算主题。

### <a name="additional-info"></a>其他信息
* [Microsoft Quantum 开发工具包发行说明](xref:microsoft.quantum.relnotes)。


## <a name="be-a-part-of-the-q-open-source-community"></a>加入 Q# 开源社区
Quantum 开发工具包是一种开源开发工具包，目的是方便开发人员进行量子计算，解决世界上最紧迫的一些难题。  需要开源软件的学术机构将能够部署 Q# 进行量子学习和开发。 将开发工具包开源也方便开发人员和领域专家通过其代码来贡献各种改进和创意。

你对 Quantum 开发工具包的反馈、参与和贡献很重要。  如需详细了解 Quantum 开发工具包源、提供反馈、了解如何参与这个不断发展的量子开发平台的决策并贡献力量，请参阅[为 Quantum 开发工具包做贡献](xref:microsoft.quantum.contributing)。

有关 Microsoft 推出的量子计算计划的更多常规信息，请参阅 [Microsoft Quantum](https://www.microsoft.com/en-us/quantum/)。
