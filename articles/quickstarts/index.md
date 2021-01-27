---
title: 设置 Microsoft Quantum 开发工具包 (QDK)
description: 了解如何为不同的环境设置 Microsoft Quantum 开发工具包。
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: quickstart
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 15067f1762f4468345beee38c98e1b943081fc1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859027"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a>设置 Microsoft Quantum 开发工具包 (QDK)

了解如何为环境设置 Microsoft Quantum 开发工具包 (QDK)，以便可以开始进行量子编程。 QDK 包括：

- Q# 编程语言
- 以 Q# 对复杂功能进行抽象化的一组库
- 适用于 Python 和 .NET 语言（C#、F# 和 VB.NET）的 API，用于运行以 Q# 编写的量子程序
- 可帮助开发的工具

Q# 程序可以使用 Visual Studio Code 或 Visual Studio，通过具有 IQ# Jupyter 内核的 Jupyter Notebook，或与用 Python 或 .NET 语言（C#、F#）编写的主机程序配对来作为独立应用程序运行。 你还可以使用 [Codespaces](https://online.visualstudio.com/)、[MyBinder.org](https://mybinder.org/) 或 [Docker](#use-the-qdk-with-docker) 联机运行 Q# 程序。 

## <a name="options-for-setting-up-the-qdk"></a>用于设置 QDK 的选项

可以通过以下三种方式使用 QDK：

- [本地安装 QDK](#install-the-qdk-locally)
- [联机使用 QDK](#use-the-qdk-online)
- [使用 QDK Docker 映像](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a>本地安装 QDK

你可以在大多数你喜欢的 IDE 中开发 Q# 代码，还可以将 Q# 与其他语言（例如 Python 和 .NET (C#、F#)）集成。

<table>
    <tr>
        <th width=10%>&nbsp;</th>
        <th>&nbsp;</th>
        <th align="center" width=18%><img src="~/media/vs_code.png" alt="VS Code" width="50"/><br><b>VS Code<br>(2019 年或以后)</b></th>
        <th align="center" width=18%><img src="~/media/vs_studio.png" alt="Visual Studio" width="50"/><br><b>Visual Studio<br>(2019 年或以后)</b></th>
        <th align="center" width=18%><img src="~/media/jupyter-wht.png" alt="jupyter install" width="65"/><br><b>Jupyter Notebook</b></th>
        <th align="center" width=18%><img src="~/media/blank.png" alt="blank spacer" width="65"/><br><b>命令行</b></th>
    </tr>
    <tr>
        <th>&nbsp;</th>
        <td align="left"><b>OS 支持：</b></td>
        <td align="center">Windows、macOS、Linux</td>
        <td align="center">仅限 Windows</td>
        <td align="center">Windows、macOS、Linux</td>
        <td align="center">Windows、macOS、Linux</td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/quantum-wht.png" alt="QDK" width="60"/></td>
        <td align="left"><b>Q# 独立</b></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">安装</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">安装</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.jupyter">安装</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">安装</a></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/python.png" alt="python install" width="50"/></td>
        <td align="left"><b>Q# 和 Python</b></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">安装</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">安装</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">安装</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">安装</a></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/dot_net.png" alt="dotnet install" width="50"/></td>
        <td align="left"><b>Q# 和 .NET（C#、F#）</b></td> 
        <td align="center"><a href="xref:microsoft.quantum.install.cs">安装</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.cs">安装</a></td>
        <td align="center">&#10006;</td>
        <td align="center"><a href="xref:microsoft.quantum.install.cs">安装</a></td>
   </tr>
</table>

## <a name="use-the-qdk-online"></a>联机使用 QDK

你还可以通过以下选项开发 Q# 代码，而无需在本地安装任何内容：

|资源|优点|限制|
|---|---|---|
|[**Visual Studio Codespaces**](xref:microsoft.quantum.install.standalone)|丰富的联机开发环境  |需要 Azure 订阅和套餐 |
|[**Binder**](xref:microsoft.quantum.install.binder) | 免费的联机笔记本体验 |不具有持久性 |

## <a name="use-the-qdk-with-docker"></a>将 QDK 与 Docker 配合使用

你可以在本地 Docker 安装中使用我们的 QDK Docker 映像，或者通过任何支持 Docker 映像的服务（例如 ACI）在云中使用我们的 QDK Docker 映像。

可以从 https://github.com/microsoft/iqsharp/#using-iq-as-a-container 下载 IQ# Docker 映像。 

你还可以将 Docker 与 Visual Studio Code 远程开发容器结合使用来快速定义开发环境。 有关 VS Code 开发容器的详细信息，请参阅 https://github.com/microsoft/Quantum/tree/master/.devcontainer 。

## <a name="next-steps"></a>后续步骤

在 [Q# 程序的运行方式](xref:microsoft.quantum.guide.host-programs)中，对其中每个设置的工作流都进行了描述和比较。
