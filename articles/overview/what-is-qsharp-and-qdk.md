---
title: 什么是 Q# 编程语言和 QDK？
description: 了解 Microsoft Quantum 开发工具包、Q# 编程语言以及如何创建量子程序。
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.q-sharp
ms.openlocfilehash: 55ac946aa935d3748b36ac99096a89d0db686835
ms.sourcegitcommit: a03d79ca3f0774161a9f86a15528d36e1291acce
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83433021"
---
# <a name="what-are-the-q-programming-language-and-qdk"></a>什么是 Q# 编程语言和 QDK？

Q# 是用于开发和运行量子算法的 Microsoft 开放源代码编程语言。 它是 Quantum 开发工具包 (QDK) 的一部分，其中包括 [Q# 库](xref:microsoft.quantum.libraries)、[量子模拟器](xref:microsoft.quantum.machines)[其他编程环境的扩展](xref:microsoft.quantum.install)和 [API 文档](xref:microsoft.quantum.standardlibsintro)。 除了标准 Q# 库，QDK 还包括化学库、机器学习库和数字库。

作为一种编程语言，Q# 从 Python、C# 和 F# 中汲取了熟悉的元素，并支持使用循环、if/then 语句和常用数据类型编写程序的基本过程模型。 它还介绍了新的特定于量子的数据结构和操作。

## <a name="what-can-i-do-with-the-qdk"></a>QDK 有什么作用？

QDK 是功能完善的 Q# 开发工具包，可与常用工具和语言结合使用来开发可在各种环境中运行的量子应用程序。 Q# 程序可以通过 Jupyter Notebook 以命令行应用的形式运行，也可以使用 Python 或 .NET 主机程序运行。

### <a name="develop-in-common-tools-and-environments"></a>在常用工具和环境中进行开发

将量子开发与 [Visual Studio、Visual Studio Code](xref:microsoft.quantum.install.standalone) 和 [Jupyter Notebook](xref:microsoft.quantum.install.jupyter) 集成。 使用内置的 API 将程序与 [Python](xref:microsoft.quantum.install.python) 和 [.NET](xref:microsoft.quantum.install.cs) 主机语言配对。

### <a name="try-quantum-operations-and-domain-specific-libraries"></a>尝试使用量子操作和特定领域的库

编写和测试量子算法，以探索量子叠加、纠缠和其他量子操作。 使用 Q# 库，可以运行复杂的量子操作，而不必设计低级别的操作序列。

### <a name="run-programs-in-simulators"></a>在模拟器中运行程序

在完整状态的量子模拟器、有限范围的 Toffoli 模拟器上运行量子程序，或在各种资源估算器中测试 Q# 代码。 

## <a name="where-can-i-learn-more"></a>可以从何处了解详细信息？

|||
| ---- | ---- |
| **我对量子计算不熟悉** | 回顾[关键概念](xref:microsoft.quantum.overview.understanding)中的量子物理学和量子计算的一些基础知识。|
| **我想更深入地了解 Q# 语言** | 请在 [Q# 用户指南](xref:microsoft.quantum.guide)中了解类型、表达式、变量和量子程序结构。|
| **我只想开始编写量子程序** | 请参阅[快速入门](xref:microsoft.quantum.install)了解如何设置 Q# 环境并开始编写量子程序。|

## <a name="how-does-q-work"></a>Q# 的工作原理是什么？

Q# 程序可以编译为独立的命令行应用程序，也可以由使用 Python 或 .NET 语言编写的主机程序调用。

编译并运行该程序时，它将创建量子模拟器的实例，并向其传递 Q# 代码。 该模拟器使用 Q# 代码创建量子比特（量子粒子的模拟）并应用转换来修改其状态。 然后将模拟器中的量子操作结果返回到程序。  

在模拟器中隔离 Q# 代码可确保算法遵循量子物理学定律，并且可以在量子计算机上正确运行。

![qsharp-code-flow](~/media/qsharp-code-flow.png)

## <a name="how-do-i-use-the-qdk"></a>如何使用 QDK？

编写和运行 Q# 程序所需的一切（包括 Q# 编译器、Q# 库和量子模拟器）都可以在本地计算机上安装和运行。 最终，你将能够在实际的量子计算机上远程运行 Q# 程序，但在此之前，可借助 QDK 随附的量子模拟器提供准确而可靠的结果。

- [通过命令行运行 Q#](xref:microsoft.quantum.install.standalone) 是最快的入门方法。

- [运行使用 IQ# 的独立 Jupyter Notebook](xref:microsoft.quantum.install.jupyter)，这是用于编译、模拟和可视化 Q# 程序的 Jupyter 扩展。

- 如果你熟悉 [Python](xref:microsoft.quantum.install.python)，则可以将其用作主机编程平台来入门。 Python 不仅深受开发人员喜爱，而且也深受科学家、研究人员和教师的喜爱。

- 如果你可以熟练使用 [C#、F# 或 VB.NET](xref:microsoft.quantum.install.cs)且熟悉 Visual Studio 开发环境，则只需在 Visual Studio 中添加一些扩展，即可为 Q# 做好准备。  

## <a name="summary"></a>总结

Q# 是用于开发量子程序的开放源代码编程语言。 它具有可用于创建复杂量子操作的库，以及可精确运行和测试程序的量子模拟器。 Q# 程序可以作为独立应用运行，也可以通过 Python 或 .NET 主机程序进行调用，并且可以从本地计算机进行编写、运行和测试。

## <a name="next-steps"></a>后续步骤

> [!div class="nextstepaction"]
> [用于量子计算的线性代数](xref:microsoft.quantum.overview.algebra)
