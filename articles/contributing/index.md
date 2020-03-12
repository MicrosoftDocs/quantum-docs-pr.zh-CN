---
title: 为 Microsoft Quantum 开发工具包贡献内容
description: 了解如何为 Microsoft Quantum 开发工具包和量子开发社区贡献内容。
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing
ms.openlocfilehash: cf913a09395f0694a51645ec8f91171e5b1555c3
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2020
ms.locfileid: "79022477"
---
# <a name="contributing-to-the-quantum-development-kit"></a>对量子开发工具包做出贡献

量子开发工具包不仅是一组用于编写量子程序的工具。
它属于广泛的用户社区，可发现量子计算，对量子算法进行研究，为量子设备开发新应用程序，并致力于充分利用量子编程。
作为该社区的成员，量子开发工具包旨在为各种背景的量子开发人员提供所需的功能。
为量子开发工具包做出贡献有助于实现这一目标，方法是改进其他量子开发人员使用的工具和记录这些工具的方式，甚至创建有助于使整个量子编程社区更适合发现和创建的新特性和功能。
我们对你做出的贡献以及有机会与你合作来尽可能完善社区表示非常感谢。

在本指南中，我们将提供有关如何使你的贡献尽可能适用于更广泛的量子编程社区的一些建议。

## <a name="building-community"></a>构建社区

有关做出贡献的第一件事就是始终记住对其做出贡献的社区。
通过在量子编程社区中对合作伙伴做出恭敬且专业的行为，可以帮助确保构建最受欢迎的社区。

在这一过程中，所有量子开发工具包项目都采用了 [Microsoft 开放源代码行为准则](https://opensource.microsoft.com/codeofconduct/)。
有关详细信息，请参阅[行为准则常见问题解答](https://opensource.microsoft.com/codeofconduct/faq/)；若有其他任何问题或意见，请联系 [opencode@microsoft.com](mailto:opencode@microsoft.com)。

## <a name="what-kinds-of-contributions-help-the-community"></a>哪些类型的贡献可以帮助社区？

通过你的贡献来帮助量子编程社区有多种不同的方法。
在本指南中，我们将重点介绍与量子开发工具包密切相关的三种方法。
所有这些方法对于构建可提高用户能力的量子社区非常重要。
也就是说，这决不是一个详尽的清单，我们建议你探索其他方法，以便基于量子编程的承诺帮助构建社区！

- **报告 bug。** 修复 bug 和其他类型的问题的第一步是识别它们。 如果你在量子开发工具包中发现了 bug，请告知我们，这样有助于对其进行修复，并为量子编程社区创建更好的一组工具。
- **改进文档。** 任何文档集始终可以更好地提供更多详细信息，使其更易于访问。
- **贡献代码。** 当然，贡献的最直接方法之一就是将新代码添加到量子开发工具包。

这些不同类型的贡献都非常宝贵，非常感谢。
在本指南的其余部分，我们将提供有关如何做出各种贡献的建议。

## <a name="where-do-contributions-go"></a>贡献的目标位置在哪里？

量子开发工具包包含许多不同的部分，它们组合在一起来实现用于编写量子程序的平台。
其中每个不同部分都在不同的存储库中找到它的位置，因此，要进行排序的早期位置之一是每个贡献最适合的目标位置。

- [**microsoft/Quantum**](https://github.com/Microsoft/Quantum)：有助于开始使用量子开发工具包的示例和工具。
- [**microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries)：量子开发工具包的标准和域特定库。
- [**microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas)：用于学习量子计算和 Q# 编程语言的自定进度编程练习。
- [**microsoft/qsharp-compiler**](https://github.com/microsoft/qsharp-compiler)：Q# 编译器、Visual Studio 扩展和 Visual Studio Code 扩展。
- [**microsoft/qsharp-runtime**](https://github.com/microsoft/qsharp-runtime)：量子开发工具包的模拟框架、代码生成和模拟目标计算机。
- [**microsoft/iqsharp**](https://github.com/microsoft/iqsharp)：用于 Q# 的 Jupyter 内核和 Python 主机功能，以及用于在云环境中使用 IQ# 的 Docker 映像。
- [**MicrosoftDocs/quantum-docs-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr)： https://docs.microsoft.com/quantum 上发布的文档的源代码。

> [!NOTE]
> 遗憾的是，我们目前无法接受 [**microsoft/Quantum-NC**](https://github.com/microsoft/Quantum-NC) 存储库上的代码和文档内容，但我们仍非常感谢你提供 bug 报表。

还有其他一些更专门化的存储库，专注于不同的事件，或与 Quantum 开发工具包相关的辅助功能。

- [**msr-quarc/qsharp.sty**](https://github.com/msr-quarc/qsharp.sty)：格式化对 Q# 语法的支持的 LaTeX。
- [**msr-quarc/intern-workshop-2019**](https://github.com/msr-quarc/intern-workshop-2019)：2019 年实习生研讨会上提供的 IQ# Notebook for Deutsch–Jozsa 教程。

## <a name="next-steps"></a>后续步骤

感谢你成为量子开发工具包社区的一员，我们很高应你做出了贡献！
如果你想要了解有关贡献的详细信息，请继续阅读以下指南之一。

> [!div class="nextstepaction"]
> [了解如何报告 bug](xref:microsoft.quantum.contributing.reporting)

> [!div class="nextstepaction"]
> [了解如何提供文档](xref:microsoft.quantum.contributing.docs)

> [!div class="nextstepaction"]
> [了解如何打开拉取请求](xref:microsoft.quantum.contributing.pulls)
