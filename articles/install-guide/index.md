---
title: 了解如何安装 Microsoft Quantum 开发工具包 (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 0e9dd1c74316eeb1fa7bbbf657d2e78231ee4294
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036502"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="65db5-102">安装 Microsoft Quantum 开发工具包 (QDK)</span><span class="sxs-lookup"><span data-stu-id="65db5-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="65db5-103">了解如何安装 Microsoft Quantum 开发工具包 (QDK)，以便可以开始进行量子编程。</span><span class="sxs-lookup"><span data-stu-id="65db5-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="65db5-104">QDK 包括：</span><span class="sxs-lookup"><span data-stu-id="65db5-104">The QDK consists of:</span></span>

- <span data-ttu-id="65db5-105">Q# 编程语言</span><span class="sxs-lookup"><span data-stu-id="65db5-105">the Q# programming language</span></span>
- <span data-ttu-id="65db5-106">在 Q# 中对复杂功能进行抽象化的一组库</span><span class="sxs-lookup"><span data-stu-id="65db5-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="65db5-107">适用于 Python 和 .NET 语言（C#、F# 和 VB.NET）的 API，用于运行以 Q# 编写的量子程序</span><span class="sxs-lookup"><span data-stu-id="65db5-107">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="65db5-108">用于促进开发的工具</span><span class="sxs-lookup"><span data-stu-id="65db5-108">tools to facilitate your development</span></span>

<span data-ttu-id="65db5-109">Q# 程序通常与通过 .NET 语言（通常为 C#）或 Python 编写的主机程序配合使用。</span><span class="sxs-lookup"><span data-stu-id="65db5-109">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="65db5-110">因此，我们可以从经典程序内部调用量子操作。</span><span class="sxs-lookup"><span data-stu-id="65db5-110">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="65db5-111">此外，QDK 还针对具有 IQ# Jupyter 内核的 Jupyter Notebook 提供了 Q# 支持。</span><span class="sxs-lookup"><span data-stu-id="65db5-111">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="65db5-112">QDK 可用于多个开发环境。</span><span class="sxs-lookup"><span data-stu-id="65db5-112">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="65db5-113">请从以下部分选择首选设置：</span><span class="sxs-lookup"><span data-stu-id="65db5-113">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="65db5-114">[安装用于 C# 的 Q#：](xref:microsoft.quantum.install.cs)如果想要结合使用 C# 和 Q# 来创建可调用 Q# 操作的 C# 主机程序，请选择此环境。</span><span class="sxs-lookup"><span data-stu-id="65db5-114">[Install Q# for C#:](xref:microsoft.quantum.install.cs) choose this environment if you want to combine C# and Q# to create a C# host program that calls Q# operations.</span></span>
- <span data-ttu-id="65db5-115">[安装用于 Python 的 Q#：](xref:microsoft.quantum.install.python)如果想要结合使用 Python 和 Q# 来创建可调用 Q# 操作的 Python 主机程序，请选择此环境。</span><span class="sxs-lookup"><span data-stu-id="65db5-115">[Install Q# for Python:](xref:microsoft.quantum.install.python) choose this environment if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="65db5-116">[安装用于 Jupyter Notebook 的 Q#：](xref:microsoft.quantum.install.jupyter)选择此环境即可在包含嵌入文本的单元中执行 Q# 代码，或创建量子计算交互式教程。</span><span class="sxs-lookup"><span data-stu-id="65db5-116">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> <span data-ttu-id="65db5-117">如果要将 Q# 与外部经典主机程序配合使用，请勿选择此环境。</span><span class="sxs-lookup"><span data-stu-id="65db5-117">Do not choose this environment if you want to combine Q# with an external classical host program.</span></span>
