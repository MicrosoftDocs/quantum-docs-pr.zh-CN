---
title: 了解如何安装 Microsoft Quantum 开发工具包 (QDK)
description: 如何安装 C#、Python 和 Jupyter Notebook 环境的 Microsoft Quantum 开发工具包。
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: bca700660094b91f1c0dfa03f9bce1336073ca51
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680190"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>安装 Microsoft Quantum 开发工具包 (QDK)

了解如何安装 Microsoft Quantum 开发工具包 (QDK)，以便可以开始进行量子编程。 QDK 包括：

- Q# 编程语言
- 在 Q# 中对复杂功能进行抽象化的一组库
- 适用于 Python 和 .NET 语言（C#、F# 和 VB.NET）的 API，用于运行以 Q# 编写的量子程序
- 用于促进开发的工具

Q# 程序通常与通过 .NET 语言（通常为 C#）或 Python 编写的主机程序配合使用。 因此，我们可以从经典程序内部调用量子操作。
此外，QDK 还针对具有 IQ# Jupyter 内核的 Jupyter Notebook 提供了 Q# 支持。

QDK 可用于多个开发环境。 请从以下部分选择首选设置：

- [Q# 命令行应用程序：](xref:microsoft.quantum.install.standalone)如果想要从命令行使用 Q#，请选择此方法。 这不会像以下选项一样需要驱动程序或主机程序。
- [安装用于 Jupyter Notebook 的 Q#：](xref:microsoft.quantum.install.jupyter)选择此环境即可在包含嵌入文本的单元中执行 Q# 代码，或创建量子计算交互式教程。 
- [使用 Q# 和 Python 进行开发：](xref:microsoft.quantum.install.python)如果想要将 Python 和 Q# 结合使用来创建可调用 Q# 操作的 Python 主机程序，请选择此选项。
- [使用 Q# 和 C# 或 F# 进行开发：](xref:microsoft.quantum.install.cs)如果想要将 C# 或 F# 和 Q# 结合使用来创建可调用 Q# 操作的 .NET 主机程序，请选择此选项。
