---
title: 了解如何安装 Microsoft Quantum 开发工具包 (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 2a098d89f13278d7137bf182a184a74afb9393be
ms.sourcegitcommit: 2ca4755d1a63431e3cb2d2918a10ad477ec2e368
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73462868"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="5bee7-102">安装 Microsoft Quantum 开发工具包 (QDK)</span><span class="sxs-lookup"><span data-stu-id="5bee7-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="5bee7-103">了解如何安装 Microsoft Quantum 开发工具包 (QDK)，以便可以开始进行量子编程。</span><span class="sxs-lookup"><span data-stu-id="5bee7-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="5bee7-104">QDK 包括：</span><span class="sxs-lookup"><span data-stu-id="5bee7-104">The QDK consists of:</span></span>

- <span data-ttu-id="5bee7-105">Q# 编程语言</span><span class="sxs-lookup"><span data-stu-id="5bee7-105">the Q# programming language</span></span>
- <span data-ttu-id="5bee7-106">在 Q# 中对复杂功能进行抽象化的一组库</span><span class="sxs-lookup"><span data-stu-id="5bee7-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="5bee7-107">运行以 Q# 编写的量子操作的主机应用程序（以 Python 或 .NET 语言编写）</span><span class="sxs-lookup"><span data-stu-id="5bee7-107">a host application (written in Python or a .NET language) that runs quantum operations written in Q#</span></span>
- <span data-ttu-id="5bee7-108">用于促进开发的工具</span><span class="sxs-lookup"><span data-stu-id="5bee7-108">tools to facilitate your development</span></span>

<span data-ttu-id="5bee7-109">根据所选的开发环境，有不同的安装步骤。</span><span class="sxs-lookup"><span data-stu-id="5bee7-109">Depending on your chosen development environment, there are different installation steps.</span></span> <span data-ttu-id="5bee7-110">从以下部分中选择环境。</span><span class="sxs-lookup"><span data-stu-id="5bee7-110">Choose your environment from the sections below.</span></span>

## <a name="develop-with-python"></a><span data-ttu-id="5bee7-111">使用 Python 进行开发</span><span class="sxs-lookup"><span data-stu-id="5bee7-111">Develop with Python</span></span>

<span data-ttu-id="5bee7-112">使用 Python 的 qsharp 包可以轻松地从 Python 内模拟 Q# 操作和函数。</span><span class="sxs-lookup"><span data-stu-id="5bee7-112">The qsharp package for Python makes it easy to simulate Q# operations and functions from within Python.</span></span> <span data-ttu-id="5bee7-113">IQ# （发音为 i-q-sharp）是主要由 Jupyter 和 Python 使用的扩展，它提供用于编译和模拟 Q# 操作的核心功能。</span><span class="sxs-lookup"><span data-stu-id="5bee7-113">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python that provides the core functionality for compiling and simulating Q# operations.</span></span>

1. <span data-ttu-id="5bee7-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="5bee7-114">Pre-requisites</span></span>

    - <span data-ttu-id="5bee7-115">[Python](https://www.python.org/downloads/) 3.6 或更高版本</span><span class="sxs-lookup"><span data-stu-id="5bee7-115">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="5bee7-116">[PIP](https://pip.pypa.io/en/stable/installing) Python 包管理器</span><span class="sxs-lookup"><span data-stu-id="5bee7-116">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="5bee7-117">.NET Core SDK 3.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="5bee7-117">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="5bee7-118">安装 `iqsharp` 包</span><span class="sxs-lookup"><span data-stu-id="5bee7-118">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="5bee7-119">安装 `qsharp` 包</span><span class="sxs-lookup"><span data-stu-id="5bee7-119">Install the `qsharp` package</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="5bee7-120">通过创建 `Hello World` 应用程序来验证安装</span><span class="sxs-lookup"><span data-stu-id="5bee7-120">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="5bee7-121">通过创建名为 `Operation.qs` 的文件并向其添加以下代码来创建最小 Q# 操作：</span><span class="sxs-lookup"><span data-stu-id="5bee7-121">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld
        {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Result {
                Message("Hello from quantum world!");
                return Zero;
            }
        }
        ```

    - <span data-ttu-id="5bee7-122">创建名为 `hello_world.py` 的 Python 程序来调用 Q# `SayHello()` 操作：</span><span class="sxs-lookup"><span data-stu-id="5bee7-122">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="5bee7-123">运行该程序：</span><span class="sxs-lookup"><span data-stu-id="5bee7-123">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="5bee7-124">验证输出。</span><span class="sxs-lookup"><span data-stu-id="5bee7-124">Verify the output.</span></span> <span data-ttu-id="5bee7-125">程序应输出以下行：</span><span class="sxs-lookup"><span data-stu-id="5bee7-125">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a><span data-ttu-id="5bee7-126">使用 Jupyter Notebook 进行开发</span><span class="sxs-lookup"><span data-stu-id="5bee7-126">Develop with Jupyter notebooks</span></span>

<span data-ttu-id="5bee7-127">Jupyter 笔记本包含非常受人喜爱的学术设置、科学实验室和基于联机的协作编程功能，提供就地代码执行（现在包括 Q# 代码）以及说明、注释和其他内容。</span><span class="sxs-lookup"><span data-stu-id="5bee7-127">A favorite of academic settings, scientific labs, and online-based collaborative programming, Jupyter Notebooks offer in-place code execution—now including Q# code—along with instructions, notes, and other content.</span></span>  <span data-ttu-id="5bee7-128">下面是开始创建自己的 Q# 笔记本时需要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="5bee7-128">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="5bee7-129">IQ#（发音为 i-q-sharp）是主要由 Jupyter 和 Python 使用的 .NET Core SDK 的扩展，它提供用于编译和模拟 Q# 操作的核心功能。</span><span class="sxs-lookup"><span data-stu-id="5bee7-129">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>


1. <span data-ttu-id="5bee7-130">先决条件</span><span class="sxs-lookup"><span data-stu-id="5bee7-130">Pre-requisites</span></span>

    - <span data-ttu-id="5bee7-131">[Python](https://www.python.org/downloads/) 3.6 或更高版本</span><span class="sxs-lookup"><span data-stu-id="5bee7-131">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="5bee7-132">Jupyter 笔记本</span><span class="sxs-lookup"><span data-stu-id="5bee7-132">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="5bee7-133">.NET Core SDK 3.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="5bee7-133">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="5bee7-134">安装 `iqsharp` 包</span><span class="sxs-lookup"><span data-stu-id="5bee7-134">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="5bee7-135">通过创建 `Hello World` 应用程序来验证安装</span><span class="sxs-lookup"><span data-stu-id="5bee7-135">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="5bee7-136">运行以下命令以启动 Notebook 服务器：</span><span class="sxs-lookup"><span data-stu-id="5bee7-136">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="5bee7-137">浏览到命令行上显示的 URL。</span><span class="sxs-lookup"><span data-stu-id="5bee7-137">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="5bee7-138">例如：[http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="5bee7-138">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

    - <span data-ttu-id="5bee7-139">使用 Q# 内核创建 Jupyter Notebook，并将以下代码添加到第一个 Notebook 单元格：</span><span class="sxs-lookup"><span data-stu-id="5bee7-139">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="5bee7-140">运行以下 Notebook 单元格：</span><span class="sxs-lookup"><span data-stu-id="5bee7-140">Run this cell of the notebook:</span></span>

        ![包含 Q# 代码的 Jupyter 笔记本单元格](~/media/install-guide-jupyter.png)

        <span data-ttu-id="5bee7-142">应在单元格的输出中看到 `SayHello`。</span><span class="sxs-lookup"><span data-stu-id="5bee7-142">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="5bee7-143">在 Jupyter Notebook 中运行时，将编译 Q# 代码，并且 Notebook 将输出找到的操作的名称。</span><span class="sxs-lookup"><span data-stu-id="5bee7-143">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="5bee7-144">在新单元格中，模拟执行刚刚使用 `%simulate` magic 创建的量子计算机操作：</span><span class="sxs-lookup"><span data-stu-id="5bee7-144">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

        ![包含 %simulate magic 的 Jupyter 笔记本单元格](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="5bee7-146">应会看到在屏幕上显示的消息以及所调用操作的结果（在本例中为空）。</span><span class="sxs-lookup"><span data-stu-id="5bee7-146">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>


## <a name="develop-with-c-on-windows-using-visual-studio"></a><span data-ttu-id="5bee7-147">在 Windows 上使用 C# 进行开发，使用 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5bee7-147">Develop with C# on Windows, using Visual Studio</span></span>

<span data-ttu-id="5bee7-148">Visual Studio 提供了用于开发 Q# 程序的丰富环境，并且提供了代码完成和语法突出显示等强大功能，以便指导开发人员构建其应用程序。</span><span class="sxs-lookup"><span data-stu-id="5bee7-148">Visual Studio offers a rich environment for developing Q# programs, offering great features like code completion and syntax highlighting that guide the developer in building their applications.</span></span>  <span data-ttu-id="5bee7-149">Q# Visual Studio 扩展包含用于 Q# 文件和项目的模板，以及语法突出显示和 IntelliSense 支持。</span><span class="sxs-lookup"><span data-stu-id="5bee7-149">The Q# Visual Studio extension contains templates for Q# files and projects as well as syntax highlighting and IntelliSense support.</span></span>


1. <span data-ttu-id="5bee7-150">先决条件</span><span class="sxs-lookup"><span data-stu-id="5bee7-150">Pre-requisites</span></span>

    - <span data-ttu-id="5bee7-151">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3，启用了 .NET Core 跨平台开发工作负载。</span><span class="sxs-lookup"><span data-stu-id="5bee7-151">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="5bee7-152">安装 Q# Visual Studio 扩展</span><span class="sxs-lookup"><span data-stu-id="5bee7-152">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="5bee7-153">下载 [Visual Studio 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="5bee7-153">Download the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="5bee7-154">将扩展添加到 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5bee7-154">Add the extension to Visual Studio</span></span>

1. <span data-ttu-id="5bee7-155">通过创建 `Hello World` 应用程序来验证安装</span><span class="sxs-lookup"><span data-stu-id="5bee7-155">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="5bee7-156">创建新的 Q# 应用程序</span><span class="sxs-lookup"><span data-stu-id="5bee7-156">Create a new Q# application</span></span>

        - <span data-ttu-id="5bee7-157">转到“文件” -> “新建” -> “项目”   </span><span class="sxs-lookup"><span data-stu-id="5bee7-157">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="5bee7-158">在搜索框中键入 `Q#`</span><span class="sxs-lookup"><span data-stu-id="5bee7-158">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="5bee7-159">选择“Q# 应用程序” </span><span class="sxs-lookup"><span data-stu-id="5bee7-159">Select **Q# Application**</span></span>
        - <span data-ttu-id="5bee7-160">选择“下一步” </span><span class="sxs-lookup"><span data-stu-id="5bee7-160">Select **Next**</span></span>
        - <span data-ttu-id="5bee7-161">为应用程序选择名称和位置</span><span class="sxs-lookup"><span data-stu-id="5bee7-161">Choose a name and location for your application</span></span>
        - <span data-ttu-id="5bee7-162">选择“创建” </span><span class="sxs-lookup"><span data-stu-id="5bee7-162">Select **Create**</span></span>

    - <span data-ttu-id="5bee7-163">检查项目</span><span class="sxs-lookup"><span data-stu-id="5bee7-163">Inspect the project</span></span>

        <span data-ttu-id="5bee7-164">应该会看到已创建两个文件：`Driver.cs`，它是 C# 主机应用程序；以及 `Operation.qs`，它是定义将消息打印到控制台的简单操作的 Q# 程序。</span><span class="sxs-lookup"><span data-stu-id="5bee7-164">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="5bee7-165">运行应用程序</span><span class="sxs-lookup"><span data-stu-id="5bee7-165">Run the application</span></span>

        - <span data-ttu-id="5bee7-166">选择“调试”   -> “在不调试的情况下启动” </span><span class="sxs-lookup"><span data-stu-id="5bee7-166">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="5bee7-167">应该会看到打印到控制台窗口的文本 `Hello quantum world!`。</span><span class="sxs-lookup"><span data-stu-id="5bee7-167">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="5bee7-168">如果一个 Visual Studio 解决方案中具有多个项目，解决方案中包含的所有项目都需要位于解决方案所在的同一文件夹中，或位于其中一个子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="5bee7-168">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="develop-with-c-using-visual-studio-code"></a><span data-ttu-id="5bee7-169">使用 Visual Studio Code 以 C# 进行开发</span><span class="sxs-lookup"><span data-stu-id="5bee7-169">Develop with C#, using Visual Studio Code</span></span>

<span data-ttu-id="5bee7-170">Visual Studio (VS Code) 提供了用于跨许多计算机环境（包括 Windows、Linux 和 Mac）开发 Q# 程序的丰富环境，并且提供了代码完成和语法突出显示等强大功能，以便指导开发人员构建其应用程序。</span><span class="sxs-lookup"><span data-stu-id="5bee7-170">Visual Studio Code (VS Code) offers a rich environment for developing Q# programs across many multiple computer environments, including Windows, Linux and Mac, offering great features like code completion and syntax highlighting that guide the developer in building their applications.</span></span>  <span data-ttu-id="5bee7-171">Q# VS Code 扩展包含语法突出显示和 Q# 代码片段。</span><span class="sxs-lookup"><span data-stu-id="5bee7-171">The Q# VS Code extension contains syntax highlighting, and Q# code snippets.</span></span>

1. <span data-ttu-id="5bee7-172">先决条件</span><span class="sxs-lookup"><span data-stu-id="5bee7-172">Pre-requisites</span></span>

   - [<span data-ttu-id="5bee7-173">VS Code</span><span class="sxs-lookup"><span data-stu-id="5bee7-173">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="5bee7-174">.NET Core SDK 3.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="5bee7-174">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="5bee7-175">安装量子 VS Code 扩展</span><span class="sxs-lookup"><span data-stu-id="5bee7-175">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="5bee7-176">安装 [VS Code 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span><span class="sxs-lookup"><span data-stu-id="5bee7-176">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="5bee7-177">安装量子项目模板：</span><span class="sxs-lookup"><span data-stu-id="5bee7-177">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="5bee7-178">转到“视图” -> “命令面板”  </span><span class="sxs-lookup"><span data-stu-id="5bee7-178">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="5bee7-179">选择  “Q#: 安装项目模板”</span><span class="sxs-lookup"><span data-stu-id="5bee7-179">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="5bee7-180">现已安装量子开发工具包，并且可以在自己的应用程序和库中使用。</span><span class="sxs-lookup"><span data-stu-id="5bee7-180">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="5bee7-181">通过创建 `Hello World` 应用程序来验证安装</span><span class="sxs-lookup"><span data-stu-id="5bee7-181">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="5bee7-182">创建新项目：</span><span class="sxs-lookup"><span data-stu-id="5bee7-182">Create a new project:</span></span>

        - <span data-ttu-id="5bee7-183">转到“视图” -> “命令面板”  </span><span class="sxs-lookup"><span data-stu-id="5bee7-183">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="5bee7-184">选择  “Q#: 创建新项目”</span><span class="sxs-lookup"><span data-stu-id="5bee7-184">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="5bee7-185">导航到要在其中创建应用程序的文件系统上的位置</span><span class="sxs-lookup"><span data-stu-id="5bee7-185">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="5bee7-186">创建项目后，单击“打开新项目...”  按钮</span><span class="sxs-lookup"><span data-stu-id="5bee7-186">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="5bee7-187">运行应用程序：</span><span class="sxs-lookup"><span data-stu-id="5bee7-187">Run the application:</span></span>

        - <span data-ttu-id="5bee7-188">转到“调试”   -> “在不调试的情况下启动” </span><span class="sxs-lookup"><span data-stu-id="5bee7-188">Go to **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="5bee7-189">应在输出窗口 `Hello quantum world!` 中看到以下文本</span><span class="sxs-lookup"><span data-stu-id="5bee7-189">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> * > * <span data-ttu-id="5bee7-190">Visual Studio Code 扩展当前不支持具有多个根文件夹的工作区。</span><span class="sxs-lookup"><span data-stu-id="5bee7-190">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="5bee7-191">如果一个 VS Code 工作区中具有多个项目，则所有项目都必须包含在同一个根文件夹中。</span><span class="sxs-lookup"><span data-stu-id="5bee7-191">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="5bee7-192">使用 C# 进行开发，使用 `dotnet` 命令行工具</span><span class="sxs-lookup"><span data-stu-id="5bee7-192">Develop with C#, using the `dotnet` command-line tool</span></span>

<span data-ttu-id="5bee7-193">当然，只需安装 .NET Core SDK 和 QDK 项目模板，就可以从命令行生成和运行 Q# 程序。</span><span class="sxs-lookup"><span data-stu-id="5bee7-193">Of course, you can also build and run Q# programs from the command line by simply installing the .NET Core SDK and the QDK project templates.</span></span> 

1. <span data-ttu-id="5bee7-194">先决条件</span><span class="sxs-lookup"><span data-stu-id="5bee7-194">Pre-requisites</span></span>

    - [<span data-ttu-id="5bee7-195">.NET Core SDK 3.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="5bee7-195">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="5bee7-196">安装适用于 .NET 的量子项目模板</span><span class="sxs-lookup"><span data-stu-id="5bee7-196">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="5bee7-197">现已安装量子开发工具包，并且可以在自己的应用程序和库中使用。</span><span class="sxs-lookup"><span data-stu-id="5bee7-197">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="5bee7-198">通过创建 `Hello World` 应用程序来验证安装</span><span class="sxs-lookup"><span data-stu-id="5bee7-198">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="5bee7-199">创建新应用程序</span><span class="sxs-lookup"><span data-stu-id="5bee7-199">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="5bee7-200">导航到新的应用程序目录</span><span class="sxs-lookup"><span data-stu-id="5bee7-200">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="5bee7-201">应该会看到已创建两个文件，以及应用程序的项目文件：Q# 文件 (`Operation.qs`) 和 C# 主机文件 (`Driver.cs`)。</span><span class="sxs-lookup"><span data-stu-id="5bee7-201">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="5bee7-202">运行应用程序</span><span class="sxs-lookup"><span data-stu-id="5bee7-202">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="5bee7-203">应该会看到以下输出：`Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="5bee7-203">You should see the following output: `Hello quantum world!`</span></span>

## <a name="whats-next"></a><span data-ttu-id="5bee7-204">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5bee7-204">What's next?</span></span>

<span data-ttu-id="5bee7-205">在首选环境中安装量子开发工具包后，可以编写并运行[第一个量子程序](xref:microsoft.quantum.write-program)。</span><span class="sxs-lookup"><span data-stu-id="5bee7-205">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
