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
ms.openlocfilehash: 74b9b3d8f694072f5b5f4d0eb520263387de8919
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834476"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="37fbe-103">设置 Microsoft Quantum 开发工具包 (QDK)</span><span class="sxs-lookup"><span data-stu-id="37fbe-103">Setting up the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="37fbe-104">了解如何为环境设置 Microsoft Quantum 开发工具包 (QDK)，以便可以开始进行量子编程。</span><span class="sxs-lookup"><span data-stu-id="37fbe-104">Learn how to set up the Microsoft Quantum Development Kit (QDK) for your environment, so that you can get started with quantum programming.</span></span> <span data-ttu-id="37fbe-105">QDK 包括：</span><span class="sxs-lookup"><span data-stu-id="37fbe-105">The QDK consists of:</span></span>

- <span data-ttu-id="37fbe-106">Q# 编程语言</span><span class="sxs-lookup"><span data-stu-id="37fbe-106">The Q# programming language</span></span>
- <span data-ttu-id="37fbe-107">以 Q# 对复杂功能进行抽象化的一组库</span><span class="sxs-lookup"><span data-stu-id="37fbe-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="37fbe-108">适用于 Python 和 .NET 语言（C#、F# 和 VB.NET）的 API，用于运行以 Q# 编写的量子程序</span><span class="sxs-lookup"><span data-stu-id="37fbe-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="37fbe-109">可帮助开发的工具</span><span class="sxs-lookup"><span data-stu-id="37fbe-109">Tools to facilitate your development</span></span>

<span data-ttu-id="37fbe-110">Q# 程序可以使用 Visual Studio Code 或 Visual Studio，通过具有 IQ# Jupyter 内核的 Jupyter Notebook，或与用 Python 或 .NET 语言（C#、F#）编写的主机程序配对来作为独立应用程序运行。</span><span class="sxs-lookup"><span data-stu-id="37fbe-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, through Jupyter Notebooks with the IQ# Jupyter kernel, or paired with a host program written in Python or a .NET language (C#, F#).</span></span> <span data-ttu-id="37fbe-111">你还可以使用 [Codespaces](https://online.visualstudio.com/)、[MyBinder.org](https://mybinder.org/) 或 [Docker](#use-the-qdk-with-docker) 联机运行 Q# 程序。</span><span class="sxs-lookup"><span data-stu-id="37fbe-111">You can also run Q# programs online using [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/), or [Docker](#use-the-qdk-with-docker).</span></span> 

## <a name="options-for-setting-up-the-qdk"></a><span data-ttu-id="37fbe-112">用于设置 QDK 的选项</span><span class="sxs-lookup"><span data-stu-id="37fbe-112">Options for setting up the QDK</span></span>

<span data-ttu-id="37fbe-113">可以通过以下三种方式使用 QDK：</span><span class="sxs-lookup"><span data-stu-id="37fbe-113">You can use the QDK in three ways:</span></span>

- [<span data-ttu-id="37fbe-114">本地安装 QDK</span><span class="sxs-lookup"><span data-stu-id="37fbe-114">Install the QDK locally</span></span>](#install-the-qdk-locally)
- [<span data-ttu-id="37fbe-115">联机使用 QDK</span><span class="sxs-lookup"><span data-stu-id="37fbe-115">Use the QDK online</span></span>](#use-the-qdk-online)
- [<span data-ttu-id="37fbe-116">使用 QDK Docker 映像</span><span class="sxs-lookup"><span data-stu-id="37fbe-116">Use a QDK Docker image</span></span>](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a><span data-ttu-id="37fbe-117">本地安装 QDK</span><span class="sxs-lookup"><span data-stu-id="37fbe-117">Install the QDK locally</span></span>

<span data-ttu-id="37fbe-118">你可以在大多数你喜欢的 IDE 中开发 Q# 代码，还可以将 Q# 与其他语言（例如 Python 和 .NET (C#、F#)）集成。</span><span class="sxs-lookup"><span data-stu-id="37fbe-118">You can develop Q# code in most of your favorites IDEs, as well as integrate Q# with other languages such as Python and .NET (C#, F#).</span></span>

|&nbsp; | <span data-ttu-id="37fbe-119">**VS Code<br>（2019 或更高版本）**</span><span class="sxs-lookup"><span data-stu-id="37fbe-119">**VS Code<br>(2019 or later)**</span></span>| <span data-ttu-id="37fbe-120">**Visual Studio<br>（2019 或更高版本）**</span><span class="sxs-lookup"><span data-stu-id="37fbe-120">**Visual Studio<br>(2019 or later)**</span></span> | <span data-ttu-id="37fbe-121">**Jupyter Notebook**</span><span class="sxs-lookup"><span data-stu-id="37fbe-121">**Jupyter Notebooks**</span></span> | <span data-ttu-id="37fbe-122">**命令行**</span><span class="sxs-lookup"><span data-stu-id="37fbe-122">**Command line**</span></span>|
|:-----|:-----:|:-----:|:-----:|:-----:|
|<span data-ttu-id="37fbe-123">操作系统 </span><span class="sxs-lookup"><span data-stu-id="37fbe-123">**OS**</span></span> |<span data-ttu-id="37fbe-124">Windows、macOS、Linux</span><span class="sxs-lookup"><span data-stu-id="37fbe-124">Windows, macOS, Linux</span></span> |<span data-ttu-id="37fbe-125">仅限 Windows</span><span class="sxs-lookup"><span data-stu-id="37fbe-125">Windows only</span></span> |<span data-ttu-id="37fbe-126">Windows、macOS、Linux</span><span class="sxs-lookup"><span data-stu-id="37fbe-126">Windows, macOS, Linux</span></span> |<span data-ttu-id="37fbe-127">Windows、macOS、Linux</span><span class="sxs-lookup"><span data-stu-id="37fbe-127">Windows, macOS, Linux</span></span> |
|<br><span data-ttu-id="37fbe-128">**Q# 独立**</span><span class="sxs-lookup"><span data-stu-id="37fbe-128">**Q# standalone**</span></span> |<br>[<span data-ttu-id="37fbe-129">安装</span><span class="sxs-lookup"><span data-stu-id="37fbe-129">Install</span></span>](xref:microsoft.quantum.install.standalone) |<br> [<span data-ttu-id="37fbe-130">安装</span><span class="sxs-lookup"><span data-stu-id="37fbe-130">Install</span></span>](xref:microsoft.quantum.install.standalone)  |<br> [<span data-ttu-id="37fbe-131">安装</span><span class="sxs-lookup"><span data-stu-id="37fbe-131">Install</span></span>](xref:microsoft.quantum.install.jupyter) |<br>[<span data-ttu-id="37fbe-132">安装</span><span class="sxs-lookup"><span data-stu-id="37fbe-132">Install</span></span>](xref:microsoft.quantum.install.standalone)|
|<span data-ttu-id="37fbe-133">**Q# 和 Python**</span><span class="sxs-lookup"><span data-stu-id="37fbe-133">**Q#  and Python**</span></span> |[<span data-ttu-id="37fbe-134">安装</span><span class="sxs-lookup"><span data-stu-id="37fbe-134">Install</span></span>](xref:microsoft.quantum.install.python) |[<span data-ttu-id="37fbe-135">安装</span><span class="sxs-lookup"><span data-stu-id="37fbe-135">Install</span></span>](xref:microsoft.quantum.install.python) |[<span data-ttu-id="37fbe-136">安装</span><span class="sxs-lookup"><span data-stu-id="37fbe-136">Install</span></span>](xref:microsoft.quantum.install.jupyter) |[<span data-ttu-id="37fbe-137">安装</span><span class="sxs-lookup"><span data-stu-id="37fbe-137">Install</span></span>](xref:microsoft.quantum.install.python) |
|<span data-ttu-id="37fbe-138">**Q# 和 .NET（C#、F#）**</span><span class="sxs-lookup"><span data-stu-id="37fbe-138">**Q# and .NET (C#, F#)**</span></span>|[<span data-ttu-id="37fbe-139">安装</span><span class="sxs-lookup"><span data-stu-id="37fbe-139">Install</span></span>](xref:microsoft.quantum.install.cs) |[<span data-ttu-id="37fbe-140">安装</span><span class="sxs-lookup"><span data-stu-id="37fbe-140">Install</span></span>](xref:microsoft.quantum.install.cs)|<span data-ttu-id="37fbe-141">&#10006;</span><span class="sxs-lookup"><span data-stu-id="37fbe-141">&#10006;</span></span> |[<span data-ttu-id="37fbe-142">安装</span><span class="sxs-lookup"><span data-stu-id="37fbe-142">Install</span></span>](xref:microsoft.quantum.install.cs) |

## <a name="use-the-qdk-online"></a><span data-ttu-id="37fbe-143">联机使用 QDK</span><span class="sxs-lookup"><span data-stu-id="37fbe-143">Use the QDK Online</span></span>

<span data-ttu-id="37fbe-144">你还可以通过以下选项开发 Q# 代码，而无需在本地安装任何内容：</span><span class="sxs-lookup"><span data-stu-id="37fbe-144">You can also develop Q# code without installing anything locally with these options:</span></span>

|<span data-ttu-id="37fbe-145">资源</span><span class="sxs-lookup"><span data-stu-id="37fbe-145">Resource</span></span>|<span data-ttu-id="37fbe-146">优点</span><span class="sxs-lookup"><span data-stu-id="37fbe-146">Advantages</span></span>|<span data-ttu-id="37fbe-147">限制</span><span class="sxs-lookup"><span data-stu-id="37fbe-147">Limitations</span></span>|
|---|---|---|
|[<span data-ttu-id="37fbe-148">**Visual Studio Codespaces**</span><span class="sxs-lookup"><span data-stu-id="37fbe-148">**Visual Studio Codespaces**</span></span>](xref:microsoft.quantum.install.standalone)|<span data-ttu-id="37fbe-149">丰富的联机开发环境</span><span class="sxs-lookup"><span data-stu-id="37fbe-149">A rich online development environment</span></span>  |<span data-ttu-id="37fbe-150">需要 Azure 订阅和套餐</span><span class="sxs-lookup"><span data-stu-id="37fbe-150">Requires an Azure subscription and plan</span></span> |
|[<span data-ttu-id="37fbe-151">**Binder**</span><span class="sxs-lookup"><span data-stu-id="37fbe-151">**Binder**</span></span>](xref:microsoft.quantum.install.binder) | <span data-ttu-id="37fbe-152">免费的联机笔记本体验</span><span class="sxs-lookup"><span data-stu-id="37fbe-152">Free online notebook experience</span></span> |<span data-ttu-id="37fbe-153">不具有持久性</span><span class="sxs-lookup"><span data-stu-id="37fbe-153">No persistence</span></span> |

## <a name="use-the-qdk-with-docker"></a><span data-ttu-id="37fbe-154">将 QDK 与 Docker 配合使用</span><span class="sxs-lookup"><span data-stu-id="37fbe-154">Use the QDK with Docker</span></span>

<span data-ttu-id="37fbe-155">你可以在本地 Docker 安装中使用我们的 QDK Docker 映像，或者通过任何支持 Docker 映像的服务（例如 ACI）在云中使用我们的 QDK Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="37fbe-155">You can use our QDK Docker image in your local Docker installation or in the cloud via any service that supports Docker images, such as ACI.</span></span>

<span data-ttu-id="37fbe-156">可以从 https://github.com/microsoft/iqsharp/#using-iq-as-a-container 下载 IQ# Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="37fbe-156">You can download the IQ# Docker image from https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span></span> 

<span data-ttu-id="37fbe-157">你还可以将 Docker 与 Visual Studio Code 远程开发容器结合使用来快速定义开发环境。</span><span class="sxs-lookup"><span data-stu-id="37fbe-157">You can also use Docker with a Visual Studio Code Remote Development Container to quickly define development environments.</span></span> <span data-ttu-id="37fbe-158">有关 VS Code 开发容器的详细信息，请参阅 https://github.com/microsoft/Quantum/tree/master/.devcontainer 。</span><span class="sxs-lookup"><span data-stu-id="37fbe-158">For more information about VS Code Development Containers, see https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="37fbe-159">后续步骤</span><span class="sxs-lookup"><span data-stu-id="37fbe-159">Next steps</span></span>

<span data-ttu-id="37fbe-160">在 [Q# 程序的运行方式](xref:microsoft.quantum.guide.host-programs)中，对其中每个设置的工作流都进行了描述和比较。</span><span class="sxs-lookup"><span data-stu-id="37fbe-160">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
