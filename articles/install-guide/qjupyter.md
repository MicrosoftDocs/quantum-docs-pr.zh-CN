---
title: '用 Q # Jupyter 笔记本进行开发'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 38db14ccc5f2406043ff4baee3f562385cdf47a8
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426379"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="41755-102">用 Q # Jupyter 笔记本进行开发</span><span class="sxs-lookup"><span data-stu-id="41755-102">Develop with Q# Jupyter notebooks</span></span>

<span data-ttu-id="41755-103">在 Q # Jupyter 笔记本上安装用于开发 Q # 操作的 QDK。</span><span class="sxs-lookup"><span data-stu-id="41755-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="41755-104">Jupyter 笔记本允许就地执行的代码与说明、注释和其他内容。</span><span class="sxs-lookup"><span data-stu-id="41755-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="41755-105">此环境非常适合用于编写带有嵌入的解释或量子计算交互式教程的 Q # 代码。</span><span class="sxs-lookup"><span data-stu-id="41755-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="41755-106">下面是开始创建自己的 Q# 笔记本时需要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="41755-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="41755-107">IQ#（发音为 i-q-sharp）是主要由 Jupyter 和 Python 使用的 .NET Core SDK 的扩展，它提供用于编译和模拟 Q# 操作的核心功能。</span><span class="sxs-lookup"><span data-stu-id="41755-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="41755-108">在 Q # Jupyter 笔记本中，只能运行 Q # 代码，不能从外部主机程序（例如 Python 或 c # 文件）中调用操作。</span><span class="sxs-lookup"><span data-stu-id="41755-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="41755-109">如果你的目标是将外部传统主机程序与量程计划结合使用，则此环境不适合。</span><span class="sxs-lookup"><span data-stu-id="41755-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="41755-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="41755-110">Pre-requisites</span></span>

    - <span data-ttu-id="41755-111">[Python](https://www.python.org/downloads/) 3.6 或更高版本</span><span class="sxs-lookup"><span data-stu-id="41755-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="41755-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="41755-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="41755-113">.NET Core SDK 3.1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="41755-113">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="41755-114">安装 `iqsharp` 包</span><span class="sxs-lookup"><span data-stu-id="41755-114">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="41755-115">通过创建 `Hello World` 应用程序来验证安装</span><span class="sxs-lookup"><span data-stu-id="41755-115">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="41755-116">运行以下命令以启动 Notebook 服务器：</span><span class="sxs-lookup"><span data-stu-id="41755-116">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="41755-117">若要打开 Jupyter 笔记本，请复制命令行提供的 URL 并将其粘贴到浏览器中。</span><span class="sxs-lookup"><span data-stu-id="41755-117">To open the Jupyter notebook copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="41755-118">使用 Q# 内核创建 Jupyter Notebook，并将以下代码添加到第一个 Notebook 单元格：</span><span class="sxs-lookup"><span data-stu-id="41755-118">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="41755-119">运行以下 Notebook 单元格：</span><span class="sxs-lookup"><span data-stu-id="41755-119">Run this cell of the notebook:</span></span>

        ![包含 Q# 代码的 Jupyter 笔记本单元格](~/media/install-guide-jupyter.png)

        <span data-ttu-id="41755-121">应在单元格的输出中看到 `SayHello`。</span><span class="sxs-lookup"><span data-stu-id="41755-121">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="41755-122">在 Jupyter Notebook 中运行时，将编译 Q# 代码，并且 Notebook 将输出找到的操作的名称。</span><span class="sxs-lookup"><span data-stu-id="41755-122">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="41755-123">在新单元中，使用命令执行你刚刚在模拟器中创建的操作 `%simulate` ：</span><span class="sxs-lookup"><span data-stu-id="41755-123">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![包含 %simulate magic 的 Jupyter 笔记本单元格](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="41755-125">应会看到在屏幕上打印的消息以及所调用操作的结果（在这里，我们将看到空元组， `()` 因为我们的操作只返回一个 `Unit` 类型）。</span><span class="sxs-lookup"><span data-stu-id="41755-125">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="41755-126">后续步骤</span><span class="sxs-lookup"><span data-stu-id="41755-126">Next steps</span></span>

<span data-ttu-id="41755-127">在首选环境中安装量子开发工具包后，可以编写并运行[第一个量子程序](xref:microsoft.quantum.quickstarts.qrng)。</span><span class="sxs-lookup"><span data-stu-id="41755-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
