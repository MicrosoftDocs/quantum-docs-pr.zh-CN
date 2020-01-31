---
title: 了解如何安装 Microsoft Quantum 开发工具包 (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: b209f0b600d973c3870c66060e1b484ec519322f
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820702"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>安装 Microsoft Quantum 开发工具包 (QDK)

了解如何安装 Microsoft Quantum 开发工具包 (QDK)，以便可以开始进行量子编程。 QDK 包括：

- Q# 编程语言
- 在 Q# 中对复杂功能进行抽象化的一组库
- 适用于 Python 和 .NET 语言（即：C#、F# 和 VB.NET）的 API，用于运行以 Q# 编写的量子程序
- 用于促进开发的工具

Q# 程序通常与通过 .NET 语言（通常为 C#）或 Python 编写的主机程序配合使用。 因此，我们可以从经典程序内部调用量子操作。
此外，QDK 还针对具有 IQ# Jupyter 内核的 Jupyter Notebook 提供了 Q# 支持。

QDK 可用于多个开发环境。 请从以下部分选择首选设置：

- [安装用于 C# 的 Q#：](xref:microsoft.quantum.install.cs)如果想要结合使用 C# 和 Q# 来创建可调用 Q# 操作的 C# 主机程序，请选择此环境。
- [安装用于 Python 的 Q#：](xref:microsoft.quantum.install.python)如果想要结合使用 Python 和 Q# 来创建可调用 Q# 操作的 Python 主机程序，请选择此环境。
- [安装用于 Jupyter Notebook 的 Q#：](xref:microsoft.quantum.install.jupyter)选择此环境即可在包含嵌入文本的单元中执行 Q# 代码，或创建量子计算交互式教程。 如果要将 Q# 与外部经典主机程序配合使用，请勿选择此环境。
