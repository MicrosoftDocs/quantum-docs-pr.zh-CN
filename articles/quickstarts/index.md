---
title: 安装 Microsoft Quantum 开发工具包 (QDK)
description: 如何为不同的环境安装 Microsoft 量子开发工具包。
author: bradben
ms.author: bradben
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 6a52eb0a9cdf699e8bb37578ffa3d73fe96a990e
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273239"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="947d5-103">安装 Microsoft 量子开发工具包 (QDK)</span><span class="sxs-lookup"><span data-stu-id="947d5-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="947d5-104">了解如何安装 Microsoft Quantum 开发工具包 (QDK)，以便可以开始进行量子编程。</span><span class="sxs-lookup"><span data-stu-id="947d5-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="947d5-105">QDK 包括：</span><span class="sxs-lookup"><span data-stu-id="947d5-105">The QDK consists of:</span></span>

- <span data-ttu-id="947d5-106">Q# 编程语言</span><span class="sxs-lookup"><span data-stu-id="947d5-106">The Q# programming language</span></span>
- <span data-ttu-id="947d5-107">在 Q# 中对复杂功能进行抽象化的一组库</span><span class="sxs-lookup"><span data-stu-id="947d5-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="947d5-108">适用于 Python 和 .NET 语言（C#、F# 和 VB.NET）的 API，用于运行以 Q# 编写的量子程序</span><span class="sxs-lookup"><span data-stu-id="947d5-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="947d5-109">可帮助开发的工具</span><span class="sxs-lookup"><span data-stu-id="947d5-109">Tools to facilitate your development</span></span>

<span data-ttu-id="947d5-110">可使用 Visual Studio Code 或 Visual Studio，或结合使用 Jupyter 笔记本和 IQ# Jupyter 内核将 Q# 程序作为独立的应用程序来运行。</span><span class="sxs-lookup"><span data-stu-id="947d5-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, or through Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="947d5-111">它们也可与用 .NET 语言（通常是 C#）或 Python 编写的程序配对，让你能够从经典程序内部调用量子操作。</span><span class="sxs-lookup"><span data-stu-id="947d5-111">They can also be paired with a host program written in a .NET language (typically C#) or Python, enabling you to call quantum operations from inside a classical program.</span></span>

<span data-ttu-id="947d5-112">QDK 可用于多个开发环境。</span><span class="sxs-lookup"><span data-stu-id="947d5-112">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="947d5-113">请从以下部分选择首选设置：</span><span class="sxs-lookup"><span data-stu-id="947d5-113">Select your preferred setup from:</span></span>

<span data-ttu-id="947d5-114">[使用 Q# 命令行应用程序进行开发](xref:microsoft.quantum.install.standalone) - 若要从命令行使用 Q#，请选择此方法。</span><span class="sxs-lookup"><span data-stu-id="947d5-114">[Develop with Q# command line applications](xref:microsoft.quantum.install.standalone) - Choose this approach to work with Q# from the command line.</span></span> <span data-ttu-id="947d5-115">这不会像以下选项一样需要驱动程序或主机程序。</span><span class="sxs-lookup"><span data-stu-id="947d5-115">This does not require a driver or a host program like the below options.</span></span>

<span data-ttu-id="947d5-116">[使用 Q# Jupyter 笔记本进行开发](xref:microsoft.quantum.install.jupyter) - 选择此环境可在包含嵌入文本的单元中运行 Q# 代码，或创建量子计算交互式教程。</span><span class="sxs-lookup"><span data-stu-id="947d5-116">[Develop with Q# Jupyter Notebooks](xref:microsoft.quantum.install.jupyter) - Select this environment to run Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> 

<span data-ttu-id="947d5-117">[使用 Q# 和 Python 进行开发](xref:microsoft.quantum.install.python) - 让你能够将 Python 和 Q# 结合使用来创建可调用 Q# 操作的 Python 主机程序。</span><span class="sxs-lookup"><span data-stu-id="947d5-117">[Develop with Q# and Python](xref:microsoft.quantum.install.python) - Enables you to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>

<span data-ttu-id="947d5-118">[使用 Q# 和 .NET 进行开发](xref:microsoft.quantum.install.cs) - 将 C#、F# 或 VB.NET 与 Q# 结合使用来创建可调用 Q# 操作的 .NET 主机程序。</span><span class="sxs-lookup"><span data-stu-id="947d5-118">[Develop with Q# and .NET](xref:microsoft.quantum.install.cs) - Combine C#, F#, or VB.NET with Q# to create a .NET host program that calls Q# operations.</span></span>
