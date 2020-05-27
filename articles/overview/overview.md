---
title: 量子计算简介
description: 了解量子计算是什么、量子计算机可以做些什么，以及如何学习量子计算。
author: bradben
ms.author: bradben
ms.date: 05/05/2020
ms.topic: overview
uid: microsoft.quantum.overview.introduction
ms.openlocfilehash: 7c55420bd35f9b6e0e7ec80ddffe8a861cb7df39
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430775"
---
# <a name="introduction-to-quantum-computing-and-the-quantum-development-kit"></a>量子计算和 Quantum 开发工具包简介

Microsoft Quantum 开发工具包 (QDK) 是一组开放源代码工具，旨在帮助开发人员学习量子算法和编写量子程序。 量子计算有望解决我们这个星球上在以下领域遇到的一些最大的挑战 - 环境、农业、医疗保健、能源、气候、材料科学领域，以及我们尚未遇到的其他领域方面的问题。  

对于其中的一些问题，即使是最强大的计算机也束手无策。 尽管量子技术才刚刚开始影响计算领域，但它的影响将会变得深远，并改变我们对计算的看法。

## <a name="what-is-quantum-computing"></a>什么是量子计算？

在现代用法中，量子一词是指任何物理属性中最小的离散单位，通常是指原子或次原子粒子的属性。 量子计算机使用实际的量子粒子、人工原子或量子粒子的集合属性作为处理单元，并且是大型、复杂且昂贵的设备。

通过利用量子物理学的独特行为并将其应用于计算，量子计算机利用叠加、纠缠和量子干涉等量子物理学行为，为传统的编程方法引入了新概念。

## <a name="what-can-a-quantum-computer-do"></a>量子计算机有何用途？

量子计算机并不是可以更快地执行所有操作的超级计算机，但是量子计算机在某些领域表现得非常出色。

- [量子模拟](xref:microsoft.quantum.overview.introduction#quantum-simulation)
- [加密](xref:microsoft.quantum.overview.introduction#cryptography-and-shors-algorithm)
- [搜索](xref:microsoft.quantum.overview.introduction#search-and-grovers-algorithm)
- [优化](xref:microsoft.quantum.overview.introduction#quantum-inspired-computing-and-optimization)
- [机器学习](xref:microsoft.quantum.overview.introduction#quantum-machine-learning)

## <a name="quantum-simulation"></a>量子模拟

由于量子计算机在计算中使用量子现象，因此非常适合用于对其他量子系统进行建模。 光合作用、超导性和复杂的分子形成都是量子程序可以模拟的量子机制的例子。

## <a name="cryptography-and-shors-algorithm"></a>密码学和秀尔算法

1994 年，彼得·秀尔展示了一种可缩放的量子计算机，该计算机可以破解广泛使用的加密技术，例如 RSA 算法。 经典密码学依赖于整数分解或离散对数等问题的难处理性，其中许多问题都可以使用量子计算机更有效地得以解决。

## <a name="search-and-grovers-algorithm"></a>搜索和 Grover 算法

1996 年，Lov Grover 开发了一种量子算法，该算法极大地加速了对非结构化数据搜索的解决方案，与传统算法相比，其搜索步骤更少。

## <a name="quantum-inspired-computing-and-optimization"></a>受量子启发的计算和优化

受量子启发的算法使用量子原理来提高速度和准确性，但可在经典计算机系统上实现。 这种方法使开发人员可以利用当今的新量子技术的强大功能，而无需等待仍是新兴产业的量子硬件。

优化是在给定问题的预期结果和约束条件的情况下找到问题最佳解决方案的过程。 成本、质量或生产时间等因素都会影响工业和科学界做出的关键决策。 目前在经典计算机上运行的受量子启发的优化算法可以找到迄今为止尚无法实现的解决方案。 除了优化交通流量以减少拥堵外，还提供飞机登机门分配、包裹递送、作业计划等。 随着材料科学的突破，将出现新型能源、更大容量的电池以及更轻便且更耐用的材料。

> [!NOTE]
> 详细了解[材料科学](https://cloudblogs.microsoft.com/quantum/2020/01/21/oti-lumionics-accelerating-materials-design-microsoft-azure-quantum/)、[风险管理](https://cloudblogs.microsoft.com/quantum/2019/05/22/microsoft-quantum-collaborates-with-willis-towers-watson-to-transform-risk-management-solutions/)和[医学](https://blogs.microsoft.com/blog/2018/05/18/microsoft-quantum-helps-case-western-reserve-university-advance-mri-research/)领域如何使用 Microsoft 受量子启发的计算。

## <a name="quantum-machine-learning"></a>量子机器学习

经典计算机上的机器学习正在彻底改变科学和商业领域。 然而，训练模型带来的高计算成本阻碍了该领域的发展和范围。 量子机器学习领域探讨了如何设计和实现可使机器学习比传统计算机运行速度更快的量子软件。

Quantum 开发工具包随附[量子机器学习库](xref:microsoft.quantum.machine-learning.concepts.intro)，使你能够运行混合量子/经典机器学习试验。 该库包括示例和教程，并提供了实现新的混合算法，即经典算法（以电路为中心的量子分类器）所需的工具，以解决监督分类问题。

## <a name="q-and-the-microsoft-quantum-development-kit-qdk"></a>Q# 和 Microsoft Quantum 开发工具包 (QDK)

Q# 是用于开发和运行量子算法的 Microsoft 开放源代码编程语言。 它是 [QDK](https://docs.microsoft.com/quantum/)（一种功能完善的 Q# 开发工具包）的一部分，可与标准工具和语言一起使用，以开发可在各种环境（包括内置的状态量子模拟器）中运行的量子应用程序。

这里提供有 Visual Studio 和 VS Code 的扩展，以及用于 Python 和 Jupyter Notebook 的包。

QDK 包括一个标准库以及专门的化学库、机器学习库和数字库。

该文档包括 Q# 语言指南、教程和示例代码，以帮助你快速入门，并提供丰富的文章来帮助你更深入地了解量子计算概念。  

## <a name="microsoft-quantum-hardware-partners"></a>Microsoft 量子硬件合作伙伴

Microsoft 正在与量子硬件公司合作，为开发人员提供对量子硬件的云访问权限。 通过利用 [Azure Quantum](https://azure.microsoft.com/services/quantum/) 平台和 Q# 语言，开发人员将能够探索量子算法，并在不同类型的量子硬件上运行其量子程序。

[IonQ](https://ionq.com/news/november-4-2019-microsoft-partnership) 和 [Honeywell](https://www.honeywell.com/en-us/newsroom/news/2019/11/the-future-of-quantum-computing) 都使用捕获的基于离子的处理器并利用在电场中捕获的单个离子，而 [QCI](https://quantumcircuits.com/news-and-publications/quantum-circuits-partners-with-microsoft-on-azure-quantum) 使用超导电路。

## <a name="next-steps"></a>后续步骤

[量子计算的主要概念](xref:microsoft.quantum.overview.understanding)
[快速入门](xref:microsoft.quantum.welcome)