---
title: 了解如何安装 Microsoft Quantum 开发工具包 (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 3ec53934436b47908fd4d794a98933010f6059a7
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035279"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="cfb96-102">安装 Microsoft Quantum 开发工具包 (QDK)</span><span class="sxs-lookup"><span data-stu-id="cfb96-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="cfb96-103">了解如何安装 Microsoft Quantum 开发工具包 (QDK)，以便可以开始进行量子编程。</span><span class="sxs-lookup"><span data-stu-id="cfb96-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="cfb96-104">QDK 包括：</span><span class="sxs-lookup"><span data-stu-id="cfb96-104">The QDK consists of:</span></span>

- <span data-ttu-id="cfb96-105">Q# 编程语言</span><span class="sxs-lookup"><span data-stu-id="cfb96-105">the Q# programming language</span></span>
- <span data-ttu-id="cfb96-106">在 Q# 中对复杂功能进行抽象化的一组库</span><span class="sxs-lookup"><span data-stu-id="cfb96-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="cfb96-107">运行以 Q# 编写的量子操作的主机应用程序（以 Python 或 .NET 语言编写）</span><span class="sxs-lookup"><span data-stu-id="cfb96-107">a host application (written in Python or a .NET language) that runs quantum operations written in Q#</span></span>
- <span data-ttu-id="cfb96-108">用于促进开发的工具</span><span class="sxs-lookup"><span data-stu-id="cfb96-108">tools to facilitate your development</span></span>

<span data-ttu-id="cfb96-109">根据所选的开发环境，有不同的安装步骤。</span><span class="sxs-lookup"><span data-stu-id="cfb96-109">Depending on your chosen development environment, there are different installation steps.</span></span> <span data-ttu-id="cfb96-110">从以下部分中选择环境。</span><span class="sxs-lookup"><span data-stu-id="cfb96-110">Choose your environment from the sections below.</span></span>

## <a name="develop-with-python"></a><span data-ttu-id="cfb96-111">使用 Python 进行开发</span><span class="sxs-lookup"><span data-stu-id="cfb96-111">Develop with Python</span></span>

1. <span data-ttu-id="cfb96-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="cfb96-112">Pre-requisites</span></span>

    - <span data-ttu-id="cfb96-113">[Python](https://www.python.org/downloads/) 3.6 或更高版本</span><span class="sxs-lookup"><span data-stu-id="cfb96-113">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="cfb96-114">[PIP](https://pip.pypa.io/en/stable/installing) Python 包管理器</span><span class="sxs-lookup"><span data-stu-id="cfb96-114">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="cfb96-115">.NET Core SDK 2.1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="cfb96-115">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="cfb96-116">安装 `iqsharp` 包</span><span class="sxs-lookup"><span data-stu-id="cfb96-116">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="cfb96-117">安装 `qsharp` 包</span><span class="sxs-lookup"><span data-stu-id="cfb96-117">Install the `qsharp` package</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="cfb96-118">通过创建 `Hello World` 应用程序来验证安装</span><span class="sxs-lookup"><span data-stu-id="cfb96-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="cfb96-119">通过创建名为 `Operation.qs` 的文件并向其添加以下代码来创建最小 Q# 操作：</span><span class="sxs-lookup"><span data-stu-id="cfb96-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

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

    - <span data-ttu-id="cfb96-120">创建名为 `hello_world.py` 的 Python 程序来调用 Q# `SayHello()` 操作：</span><span class="sxs-lookup"><span data-stu-id="cfb96-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="cfb96-121">运行该程序：</span><span class="sxs-lookup"><span data-stu-id="cfb96-121">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="cfb96-122">验证输出。</span><span class="sxs-lookup"><span data-stu-id="cfb96-122">Verify the output.</span></span> <span data-ttu-id="cfb96-123">程序应输出以下行：</span><span class="sxs-lookup"><span data-stu-id="cfb96-123">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a><span data-ttu-id="cfb96-124">使用 Jupyter Notebook 进行开发</span><span class="sxs-lookup"><span data-stu-id="cfb96-124">Develop with Jupyter notebooks</span></span>

1. <span data-ttu-id="cfb96-125">先决条件</span><span class="sxs-lookup"><span data-stu-id="cfb96-125">Pre-requisites</span></span>

    - <span data-ttu-id="cfb96-126">[Python](https://www.python.org/downloads/) 3.6 或更高版本</span><span class="sxs-lookup"><span data-stu-id="cfb96-126">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="cfb96-127">Jupyter 笔记本</span><span class="sxs-lookup"><span data-stu-id="cfb96-127">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="cfb96-128">.NET Core SDK 2.1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="cfb96-128">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="cfb96-129">安装 `iqsharp` 包</span><span class="sxs-lookup"><span data-stu-id="cfb96-129">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="cfb96-130">通过创建 `Hello World` 应用程序来验证安装</span><span class="sxs-lookup"><span data-stu-id="cfb96-130">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="cfb96-131">运行以下命令以启动 Notebook 服务器：</span><span class="sxs-lookup"><span data-stu-id="cfb96-131">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="cfb96-132">浏览到命令行上显示的 URL。</span><span class="sxs-lookup"><span data-stu-id="cfb96-132">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="cfb96-133">例如：[http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="cfb96-133">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

    - <span data-ttu-id="cfb96-134">使用 Q# 内核创建 Jupyter Notebook，并将以下代码添加到第一个 Notebook 单元格：</span><span class="sxs-lookup"><span data-stu-id="cfb96-134">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="cfb96-135">运行以下 Notebook 单元格：</span><span class="sxs-lookup"><span data-stu-id="cfb96-135">Run this cell of the notebook:</span></span>

        ![Jupyter Notebook 单元格](~/media/install-guide-jupyter.png)

        <span data-ttu-id="cfb96-137">应在单元格的输出中看到 `SayHello`。</span><span class="sxs-lookup"><span data-stu-id="cfb96-137">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="cfb96-138">在 Jupyter Notebook 中运行时，将编译 Q# 代码，并且 Notebook 将输出找到的操作的名称。</span><span class="sxs-lookup"><span data-stu-id="cfb96-138">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

## <a name="develop-with-c-on-windows-using-visual-studio"></a><span data-ttu-id="cfb96-139">在 Windows 上使用 C# 进行开发，使用 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cfb96-139">Develop with C# on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="cfb96-140">先决条件</span><span class="sxs-lookup"><span data-stu-id="cfb96-140">Pre-requisites</span></span>

    - <span data-ttu-id="cfb96-141">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3，启用了 .NET Core 跨平台开发工作负载。</span><span class="sxs-lookup"><span data-stu-id="cfb96-141">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="cfb96-142">安装 Q# Visual Studio 扩展</span><span class="sxs-lookup"><span data-stu-id="cfb96-142">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="cfb96-143">下载 [Visual Studio 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="cfb96-143">Download the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="cfb96-144">将扩展添加到 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cfb96-144">Add the extension to Visual Studio</span></span>

1. <span data-ttu-id="cfb96-145">通过创建 `Hello World` 应用程序来验证安装</span><span class="sxs-lookup"><span data-stu-id="cfb96-145">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="cfb96-146">创建新的 Q# 应用程序</span><span class="sxs-lookup"><span data-stu-id="cfb96-146">Create a new Q# application</span></span>

        - <span data-ttu-id="cfb96-147">转到“文件” -> “新建” -> “项目”   </span><span class="sxs-lookup"><span data-stu-id="cfb96-147">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="cfb96-148">在搜索框中键入 `Q#`</span><span class="sxs-lookup"><span data-stu-id="cfb96-148">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="cfb96-149">选择“Q# 应用程序” </span><span class="sxs-lookup"><span data-stu-id="cfb96-149">Select **Q# Application**</span></span>
        - <span data-ttu-id="cfb96-150">选择“下一步” </span><span class="sxs-lookup"><span data-stu-id="cfb96-150">Select **Next**</span></span>
        - <span data-ttu-id="cfb96-151">为应用程序选择名称和位置</span><span class="sxs-lookup"><span data-stu-id="cfb96-151">Choose a name and location for your application</span></span>
        - <span data-ttu-id="cfb96-152">选择“创建” </span><span class="sxs-lookup"><span data-stu-id="cfb96-152">Select **Create**</span></span>

    - <span data-ttu-id="cfb96-153">检查项目</span><span class="sxs-lookup"><span data-stu-id="cfb96-153">Inspect the project</span></span>

        <span data-ttu-id="cfb96-154">应该会看到已创建两个文件：`Driver.cs`，它是 C# 主机应用程序；以及 `Operation.qs`，它是定义将消息打印到控制台的简单操作的 Q# 程序。</span><span class="sxs-lookup"><span data-stu-id="cfb96-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="cfb96-155">运行应用程序</span><span class="sxs-lookup"><span data-stu-id="cfb96-155">Run the application</span></span>

        - <span data-ttu-id="cfb96-156">选择“调试”   -> “在不调试的情况下启动” </span><span class="sxs-lookup"><span data-stu-id="cfb96-156">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="cfb96-157">应该会看到打印到控制台窗口的文本 `Hello quantum world!`。</span><span class="sxs-lookup"><span data-stu-id="cfb96-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="cfb96-158">如果一个 Visual Studio 解决方案中具有多个项目，解决方案中包含的所有项目都需要位于解决方案所在的同一文件夹中，或位于其中一个子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="cfb96-158">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="develop-with-c-using-vs-code"></a><span data-ttu-id="cfb96-159">使用 C# 进行开发，使用 VS Code</span><span class="sxs-lookup"><span data-stu-id="cfb96-159">Develop with C#, using VS Code</span></span>

1. <span data-ttu-id="cfb96-160">先决条件</span><span class="sxs-lookup"><span data-stu-id="cfb96-160">Pre-requisites</span></span>

   - [<span data-ttu-id="cfb96-161">VS Code</span><span class="sxs-lookup"><span data-stu-id="cfb96-161">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="cfb96-162">.NET Core SDK 2.1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="cfb96-162">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="cfb96-163">安装量子 VS Code 扩展</span><span class="sxs-lookup"><span data-stu-id="cfb96-163">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="cfb96-164">安装 [VS Code 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span><span class="sxs-lookup"><span data-stu-id="cfb96-164">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="cfb96-165">安装量子项目模板：</span><span class="sxs-lookup"><span data-stu-id="cfb96-165">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="cfb96-166">转到“视图” -> “命令面板”  </span><span class="sxs-lookup"><span data-stu-id="cfb96-166">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="cfb96-167">选择  “Q#: 安装项目模板”</span><span class="sxs-lookup"><span data-stu-id="cfb96-167">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="cfb96-168">现已安装量子开发工具包，并且可以在自己的应用程序和库中使用。</span><span class="sxs-lookup"><span data-stu-id="cfb96-168">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="cfb96-169">通过创建 `Hello World` 应用程序来验证安装</span><span class="sxs-lookup"><span data-stu-id="cfb96-169">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="cfb96-170">创建新项目：</span><span class="sxs-lookup"><span data-stu-id="cfb96-170">Create a new project:</span></span>

        - <span data-ttu-id="cfb96-171">转到“视图” -> “命令面板”  </span><span class="sxs-lookup"><span data-stu-id="cfb96-171">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="cfb96-172">选择  “Q#: 创建新项目”</span><span class="sxs-lookup"><span data-stu-id="cfb96-172">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="cfb96-173">导航到要在其中创建应用程序的文件系统上的位置</span><span class="sxs-lookup"><span data-stu-id="cfb96-173">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="cfb96-174">创建项目后，单击“打开新项目...”  按钮</span><span class="sxs-lookup"><span data-stu-id="cfb96-174">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="cfb96-175">运行应用程序：</span><span class="sxs-lookup"><span data-stu-id="cfb96-175">Run the application:</span></span>

        - <span data-ttu-id="cfb96-176">转到“调试”   -> “在不调试的情况下启动” </span><span class="sxs-lookup"><span data-stu-id="cfb96-176">Go to **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="cfb96-177">应在输出窗口 `Hello quantum world!` 中看到以下文本</span><span class="sxs-lookup"><span data-stu-id="cfb96-177">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> * > * <span data-ttu-id="cfb96-178">Visual Studio Code 扩展当前不支持具有多个根文件夹的工作区。</span><span class="sxs-lookup"><span data-stu-id="cfb96-178">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="cfb96-179">如果一个 VS Code 工作区中具有多个项目，则所有项目都必须包含在同一个根文件夹中。</span><span class="sxs-lookup"><span data-stu-id="cfb96-179">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="cfb96-180">使用 C# 进行开发，使用 `dotnet` 命令行工具</span><span class="sxs-lookup"><span data-stu-id="cfb96-180">Develop with C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="cfb96-181">先决条件</span><span class="sxs-lookup"><span data-stu-id="cfb96-181">Pre-requisites</span></span>

    - [<span data-ttu-id="cfb96-182">.NET Core SDK 2.1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="cfb96-182">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="cfb96-183">安装适用于 .NET 的量子项目模板</span><span class="sxs-lookup"><span data-stu-id="cfb96-183">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="cfb96-184">现已安装量子开发工具包，并且可以在自己的应用程序和库中使用。</span><span class="sxs-lookup"><span data-stu-id="cfb96-184">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="cfb96-185">通过创建 `Hello World` 应用程序来验证安装</span><span class="sxs-lookup"><span data-stu-id="cfb96-185">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="cfb96-186">创建新应用程序</span><span class="sxs-lookup"><span data-stu-id="cfb96-186">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="cfb96-187">导航到新的应用程序目录</span><span class="sxs-lookup"><span data-stu-id="cfb96-187">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="cfb96-188">应该会看到已创建两个文件，以及应用程序的项目文件：Q# 文件 (`Operation.qs`) 和 C# 主机文件 (`Driver.cs`)。</span><span class="sxs-lookup"><span data-stu-id="cfb96-188">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="cfb96-189">运行应用程序</span><span class="sxs-lookup"><span data-stu-id="cfb96-189">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="cfb96-190">应该会看到以下输出：`Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="cfb96-190">You should see the following output: `Hello quantum world!`</span></span>

## <a name="whats-next"></a><span data-ttu-id="cfb96-191">后续步骤</span><span class="sxs-lookup"><span data-stu-id="cfb96-191">What's next?</span></span>

<span data-ttu-id="cfb96-192">在首选环境中安装量子开发工具包后，可以编写并运行[第一个量子程序](xref:microsoft.quantum.write-program)。</span><span class="sxs-lookup"><span data-stu-id="cfb96-192">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
