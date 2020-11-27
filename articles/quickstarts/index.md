---
title: 设置 Microsoft Quantum 开发工具包 (QDK)
description: 了解如何为不同的环境设置 Microsoft Quantum 开发工具包。
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: c6e128ea8b3845336fb692d2bceefda998b935d9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228812"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="0c31d-103">设置 Microsoft Quantum 开发工具包 (QDK)</span><span class="sxs-lookup"><span data-stu-id="0c31d-103">Setting up the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="0c31d-104">了解如何为环境设置 Microsoft Quantum 开发工具包 (QDK)，以便可以开始进行量子编程。</span><span class="sxs-lookup"><span data-stu-id="0c31d-104">Learn how to set up the Microsoft Quantum Development Kit (QDK) for your environment, so that you can get started with quantum programming.</span></span> <span data-ttu-id="0c31d-105">QDK 包括：</span><span class="sxs-lookup"><span data-stu-id="0c31d-105">The QDK consists of:</span></span>

- <span data-ttu-id="0c31d-106">Q# 编程语言</span><span class="sxs-lookup"><span data-stu-id="0c31d-106">The Q# programming language</span></span>
- <span data-ttu-id="0c31d-107">以 Q# 对复杂功能进行抽象化的一组库</span><span class="sxs-lookup"><span data-stu-id="0c31d-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="0c31d-108">适用于 Python 和 .NET 语言（C#、F# 和 VB.NET）的 API，用于运行以 Q# 编写的量子程序</span><span class="sxs-lookup"><span data-stu-id="0c31d-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="0c31d-109">可帮助开发的工具</span><span class="sxs-lookup"><span data-stu-id="0c31d-109">Tools to facilitate your development</span></span>

<span data-ttu-id="0c31d-110">Q# 程序可以使用 Visual Studio Code 或 Visual Studio，通过具有 IQ# Jupyter 内核的 Jupyter Notebook，或与用 Python 或 .NET 语言（C#、F#）编写的主机程序配对来作为独立应用程序运行。</span><span class="sxs-lookup"><span data-stu-id="0c31d-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, through Jupyter Notebooks with the IQ# Jupyter kernel, or paired with a host program written in Python or a .NET language (C#, F#).</span></span> <span data-ttu-id="0c31d-111">你还可以使用 [Codespaces](https://online.visualstudio.com/)、[MyBinder.org](https://mybinder.org/) 或 [Docker](#use-the-qdk-with-docker) 联机运行 Q# 程序。</span><span class="sxs-lookup"><span data-stu-id="0c31d-111">You can also run Q# programs online using [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/), or [Docker](#use-the-qdk-with-docker).</span></span> 

## <a name="options-for-setting-up-the-qdk"></a><span data-ttu-id="0c31d-112">用于设置 QDK 的选项</span><span class="sxs-lookup"><span data-stu-id="0c31d-112">Options for setting up the QDK</span></span>

<span data-ttu-id="0c31d-113">可以通过以下三种方式使用 QDK：</span><span class="sxs-lookup"><span data-stu-id="0c31d-113">You can use the QDK in three ways:</span></span>

- [<span data-ttu-id="0c31d-114">本地安装 QDK</span><span class="sxs-lookup"><span data-stu-id="0c31d-114">Install the QDK locally</span></span>](#install-the-qdk-locally)
- [<span data-ttu-id="0c31d-115">联机使用 QDK</span><span class="sxs-lookup"><span data-stu-id="0c31d-115">Use the QDK online</span></span>](#use-the-qdk-online)
- [<span data-ttu-id="0c31d-116">使用 QDK Docker 映像</span><span class="sxs-lookup"><span data-stu-id="0c31d-116">Use a QDK Docker image</span></span>](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a><span data-ttu-id="0c31d-117">本地安装 QDK</span><span class="sxs-lookup"><span data-stu-id="0c31d-117">Install the QDK locally</span></span>

<span data-ttu-id="0c31d-118">你可以在大多数你喜欢的 IDE 中开发 Q# 代码，还可以将 Q# 与其他语言（例如 Python 和 .NET (C#、F#)）集成。</span><span class="sxs-lookup"><span data-stu-id="0c31d-118">You can develop Q# code in most of your favorites IDEs, as well as integrate Q# with other languages such as Python and .NET (C#, F#).</span></span>

<table>
    <tr>
        <th width=10%>&nbsp;</th>
        <th>&nbsp;</th>
        <th align="center" width=18%><img src="~/media/vs_code.png" alt="VS Code" width="50"/><br><span data-ttu-id="0c31d-119"><b>VS Code</span><span class="sxs-lookup"><span data-stu-id="0c31d-119"><b>VS Code</span></span><br><span data-ttu-id="0c31d-120">(2019 年或以后)</b></span><span class="sxs-lookup"><span data-stu-id="0c31d-120">(2019 or later)</b></span></span></th>
        <th align="center" width=18%><img src="~/media/vs_studio.png" alt="Visual Studio" width="50"/><br><span data-ttu-id="0c31d-121"><b>Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0c31d-121"><b>Visual Studio</span></span><br><span data-ttu-id="0c31d-122">(2019 年或以后)</b></span><span class="sxs-lookup"><span data-stu-id="0c31d-122">(2019 or later)</b></span></span></th>
        <th align="center" width=18%><img src="~/media/jupyter-wht.png" alt="jupyter install" width="65"/><br><span data-ttu-id="0c31d-123"><b>Jupyter Notebook</b></span><span class="sxs-lookup"><span data-stu-id="0c31d-123"><b>Jupyter Notebooks</b></span></span></th>
        <th align="center" width=18%><img src="~/media/blank.png" alt="blank spacer" width="65"/><br><span data-ttu-id="0c31d-124"><b>命令行</b></span><span class="sxs-lookup"><span data-stu-id="0c31d-124"><b>Command line</b></span></span></th>
    </tr>
    <tr>
        <th>&nbsp;</th>
        <td align="left"><span data-ttu-id="0c31d-125"><b>OS 支持：</b></span><span class="sxs-lookup"><span data-stu-id="0c31d-125"><b>OS support:</b></span></span></td>
        <td align="center"><span data-ttu-id="0c31d-126">Windows、macOS、Linux</span><span class="sxs-lookup"><span data-stu-id="0c31d-126">Windows, macOS, Linux</span></span></td>
        <td align="center"><span data-ttu-id="0c31d-127">仅限 Windows</span><span class="sxs-lookup"><span data-stu-id="0c31d-127">Windows only</span></span></td>
        <td align="center"><span data-ttu-id="0c31d-128">Windows、macOS、Linux</span><span class="sxs-lookup"><span data-stu-id="0c31d-128">Windows, macOS, Linux</span></span></td>
        <td align="center"><span data-ttu-id="0c31d-129">Windows、macOS、Linux</span><span class="sxs-lookup"><span data-stu-id="0c31d-129">Windows, macOS, Linux</span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/quantum-wht.png" alt="QDK" width="60"/></td>
        <td align="left"><span data-ttu-id="0c31d-130"><b>Q# 独立</b></span><span class="sxs-lookup"><span data-stu-id="0c31d-130"><b>Q# standalone</b></span></span></td>
        <td align="center"><span data-ttu-id="0c31d-131"><a href="xref:microsoft.quantum.install.standalone">安装</a></span><span class="sxs-lookup"><span data-stu-id="0c31d-131"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="0c31d-132"><a href="xref:microsoft.quantum.install.standalone">安装</a></span><span class="sxs-lookup"><span data-stu-id="0c31d-132"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="0c31d-133"><a href="xref:microsoft.quantum.install.jupyter">安装</a></span><span class="sxs-lookup"><span data-stu-id="0c31d-133"><a href="xref:microsoft.quantum.install.jupyter">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="0c31d-134"><a href="xref:microsoft.quantum.install.standalone">安装</a></span><span class="sxs-lookup"><span data-stu-id="0c31d-134"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/python.png" alt="python install" width="50"/></td>
        <td align="left"><span data-ttu-id="0c31d-135"><b>Q# 和 Python</b></span><span class="sxs-lookup"><span data-stu-id="0c31d-135"><b>Q# and Python</b></span></span></td>
        <td align="center"><span data-ttu-id="0c31d-136"><a href="xref:microsoft.quantum.install.python">安装</a></span><span class="sxs-lookup"><span data-stu-id="0c31d-136"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="0c31d-137"><a href="xref:microsoft.quantum.install.python">安装</a></span><span class="sxs-lookup"><span data-stu-id="0c31d-137"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="0c31d-138"><a href="xref:microsoft.quantum.install.python">安装</a></span><span class="sxs-lookup"><span data-stu-id="0c31d-138"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="0c31d-139"><a href="xref:microsoft.quantum.install.python">安装</a></span><span class="sxs-lookup"><span data-stu-id="0c31d-139"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/dot_net.png" alt="dotnet install" width="50"/></td>
        <td align="left"><span data-ttu-id="0c31d-140"><b>Q# 和 .NET（C#、F#）</b></span><span class="sxs-lookup"><span data-stu-id="0c31d-140"><b>Q# and .NET (C#, F#)</b></span></span></td> 
        <td align="center"><span data-ttu-id="0c31d-141"><a href="xref:microsoft.quantum.install.cs">安装</a></span><span class="sxs-lookup"><span data-stu-id="0c31d-141"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="0c31d-142"><a href="xref:microsoft.quantum.install.cs">安装</a></span><span class="sxs-lookup"><span data-stu-id="0c31d-142"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="0c31d-143">&#10006;</span><span class="sxs-lookup"><span data-stu-id="0c31d-143">&#10006;</span></span></td>
        <td align="center"><span data-ttu-id="0c31d-144"><a href="xref:microsoft.quantum.install.cs">安装</a></span><span class="sxs-lookup"><span data-stu-id="0c31d-144"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
   </tr>
</table>

## <a name="use-the-qdk-online"></a><span data-ttu-id="0c31d-145">联机使用 QDK</span><span class="sxs-lookup"><span data-stu-id="0c31d-145">Use the QDK Online</span></span>

<span data-ttu-id="0c31d-146">你还可以通过以下选项开发 Q# 代码，而无需在本地安装任何内容：</span><span class="sxs-lookup"><span data-stu-id="0c31d-146">You can also develop Q# code without installing anything locally with these options:</span></span>

|<span data-ttu-id="0c31d-147">资源</span><span class="sxs-lookup"><span data-stu-id="0c31d-147">Resource</span></span>|<span data-ttu-id="0c31d-148">优点</span><span class="sxs-lookup"><span data-stu-id="0c31d-148">Advantages</span></span>|<span data-ttu-id="0c31d-149">限制</span><span class="sxs-lookup"><span data-stu-id="0c31d-149">Limitations</span></span>|
|---|---|---|
|[<span data-ttu-id="0c31d-150">**Visual Studio Codespaces**</span><span class="sxs-lookup"><span data-stu-id="0c31d-150">**Visual Studio Codespaces**</span></span>](xref:microsoft.quantum.install.standalone)|<span data-ttu-id="0c31d-151">丰富的联机开发环境</span><span class="sxs-lookup"><span data-stu-id="0c31d-151">A rich online development environment</span></span>  |<span data-ttu-id="0c31d-152">需要 Azure 订阅和套餐</span><span class="sxs-lookup"><span data-stu-id="0c31d-152">Requires an Azure subscription and plan</span></span> |
|[<span data-ttu-id="0c31d-153">**Binder**</span><span class="sxs-lookup"><span data-stu-id="0c31d-153">**Binder**</span></span>](xref:microsoft.quantum.install.binder) | <span data-ttu-id="0c31d-154">免费的联机笔记本体验</span><span class="sxs-lookup"><span data-stu-id="0c31d-154">Free online notebook experience</span></span> |<span data-ttu-id="0c31d-155">不具有持久性</span><span class="sxs-lookup"><span data-stu-id="0c31d-155">No persistence</span></span> |

## <a name="use-the-qdk-with-docker"></a><span data-ttu-id="0c31d-156">将 QDK 与 Docker 配合使用</span><span class="sxs-lookup"><span data-stu-id="0c31d-156">Use the QDK with Docker</span></span>

<span data-ttu-id="0c31d-157">你可以在本地 Docker 安装中使用我们的 QDK Docker 映像，或者通过任何支持 Docker 映像的服务（例如 ACI）在云中使用我们的 QDK Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="0c31d-157">You can use our QDK Docker image in your local Docker installation or in the cloud via any service that supports Docker images, such as ACI.</span></span>

<span data-ttu-id="0c31d-158">可以从 https://github.com/microsoft/iqsharp/#using-iq-as-a-container 下载 IQ# Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="0c31d-158">You can download the IQ# Docker image from https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span></span> 

<span data-ttu-id="0c31d-159">你还可以将 Docker 与 Visual Studio Code 远程开发容器结合使用来快速定义开发环境。</span><span class="sxs-lookup"><span data-stu-id="0c31d-159">You can also use Docker with a Visual Studio Code Remote Development Container to quickly define development environments.</span></span> <span data-ttu-id="0c31d-160">有关 VS Code 开发容器的详细信息，请参阅 https://github.com/microsoft/Quantum/tree/master/.devcontainer 。</span><span class="sxs-lookup"><span data-stu-id="0c31d-160">For more information about VS Code Development Containers, see https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0c31d-161">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0c31d-161">Next steps</span></span>

<span data-ttu-id="0c31d-162">在 [Q# 程序的运行方式](xref:microsoft.quantum.guide.host-programs)中，对其中每个设置的工作流都进行了描述和比较。</span><span class="sxs-lookup"><span data-stu-id="0c31d-162">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
