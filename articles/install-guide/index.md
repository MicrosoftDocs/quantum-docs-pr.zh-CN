---
title: 安装 Microsoft Quantum 开发工具包 (QDK)
description: 如何为不同的环境安装 Microsoft 量子开发工具包。
author: natke
ms.author: nakersha
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: a5230f506bce02c331d22d6a428b3bd92052bbd4
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327555"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>安装 Microsoft Quantum 开发工具包 (QDK)

了解如何安装 Microsoft Quantum 开发工具包 (QDK)，以便可以开始进行量子编程。 QDK 包括：

- Q# 编程语言
- 在 Q# 中对复杂功能进行抽象化的一组库
- 适用于 Python 和 .NET 语言（C#、F# 和 VB.NET）的 API，用于运行以 Q# 编写的量子程序
- 可帮助开发的工具

可使用 Visual Studio Code 或 Visual Studio，或结合使用 Jupyter 笔记本和 IQ# Jupyter 内核将 Q# 程序作为独立的应用程序来运行。

它们也可与用 .NET 语言（通常是 C#）或 Python 编写的程序配对，让你能够从经典程序内部调用量子操作。

QDK 可用于多个开发环境。 请从以下部分选择首选设置：

[使用 Q# 命令行应用程序进行开发](xref:microsoft.quantum.install.standalone) - 若要从命令行使用 Q#，请选择此方法。 这不会像以下选项一样需要驱动程序或主机程序。

[使用 Q# Jupyter 笔记本进行开发](xref:microsoft.quantum.install.jupyter) - 选择此环境可在包含嵌入文本的单元中运行 Q# 代码，或创建量子计算交互式教程。 

[使用 Q# 和 Python 进行开发](xref:microsoft.quantum.install.python) - 让你能够将 Python 和 Q# 结合使用来创建可调用 Q# 操作的 Python 主机程序。

[使用 Q# 和 .NET 进行开发](xref:microsoft.quantum.install.cs) - 将 C#、F# 或 VB.NET 与 Q# 结合使用来创建可调用 Q# 操作的 .NET 主机程序。
