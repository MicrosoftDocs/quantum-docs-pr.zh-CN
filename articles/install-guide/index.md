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
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="36431-103">安装 Microsoft Quantum 开发工具包 (QDK)</span><span class="sxs-lookup"><span data-stu-id="36431-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="36431-104">了解如何安装 Microsoft Quantum 开发工具包 (QDK)，以便可以开始进行量子编程。</span><span class="sxs-lookup"><span data-stu-id="36431-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="36431-105">QDK 包括：</span><span class="sxs-lookup"><span data-stu-id="36431-105">The QDK consists of:</span></span>

- <span data-ttu-id="36431-106">Q# 编程语言</span><span class="sxs-lookup"><span data-stu-id="36431-106">the Q# programming language</span></span>
- <span data-ttu-id="36431-107">在 Q# 中对复杂功能进行抽象化的一组库</span><span class="sxs-lookup"><span data-stu-id="36431-107">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="36431-108">适用于 Python 和 .NET 语言（C#、F# 和 VB.NET）的 API，用于运行以 Q# 编写的量子程序</span><span class="sxs-lookup"><span data-stu-id="36431-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="36431-109">用于促进开发的工具</span><span class="sxs-lookup"><span data-stu-id="36431-109">tools to facilitate your development</span></span>

<span data-ttu-id="36431-110">Q# 程序通常与通过 .NET 语言（通常为 C#）或 Python 编写的主机程序配合使用。</span><span class="sxs-lookup"><span data-stu-id="36431-110">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="36431-111">因此，我们可以从经典程序内部调用量子操作。</span><span class="sxs-lookup"><span data-stu-id="36431-111">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="36431-112">此外，QDK 还针对具有 IQ# Jupyter 内核的 Jupyter Notebook 提供了 Q# 支持。</span><span class="sxs-lookup"><span data-stu-id="36431-112">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="36431-113">QDK 可用于多个开发环境。</span><span class="sxs-lookup"><span data-stu-id="36431-113">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="36431-114">请从以下部分选择首选设置：</span><span class="sxs-lookup"><span data-stu-id="36431-114">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="36431-115">[Q# 命令行应用程序：](xref:microsoft.quantum.install.standalone)如果想要从命令行使用 Q#，请选择此方法。</span><span class="sxs-lookup"><span data-stu-id="36431-115">[Q# command line application:](xref:microsoft.quantum.install.standalone) choose this approach if you want to work with Q# from the command line.</span></span> <span data-ttu-id="36431-116">这不会像以下选项一样需要驱动程序或主机程序。</span><span class="sxs-lookup"><span data-stu-id="36431-116">This does not require a driver or a host program like the below options.</span></span>
- <span data-ttu-id="36431-117">[安装用于 Jupyter Notebook 的 Q#：](xref:microsoft.quantum.install.jupyter)选择此环境即可在包含嵌入文本的单元中执行 Q# 代码，或创建量子计算交互式教程。</span><span class="sxs-lookup"><span data-stu-id="36431-117">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> 
- <span data-ttu-id="36431-118">[使用 Q# 和 Python 进行开发：](xref:microsoft.quantum.install.python)如果想要将 Python 和 Q# 结合使用来创建可调用 Q# 操作的 Python 主机程序，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="36431-118">[Develop with Q# and Python:](xref:microsoft.quantum.install.python) if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="36431-119">[使用 Q# 和 C# 或 F# 进行开发：](xref:microsoft.quantum.install.cs)如果想要将 C# 或 F# 和 Q# 结合使用来创建可调用 Q# 操作的 .NET 主机程序，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="36431-119">[Develop with Q# and C# or F#:](xref:microsoft.quantum.install.cs) if you want to combine C# or F# and Q# to create a .NET host program that calls Q# operations.</span></span>
