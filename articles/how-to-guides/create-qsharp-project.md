---
title: '了解如何使用量程开发工具包（QDK）创建 Q # 项目'
description: '使用所选开发环境中的 QDK 和 Q # 初始化项目以进行量程开发'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: 8af8e3288aab731520ede984d5f89644de292385
ms.sourcegitcommit: c8ebc5d7d8581444754f5d7bfaca2f25601f1b14
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "84578205"
---
# <a name="create-a-q-project-in-your-development-environment"></a><span data-ttu-id="de68e-103">在开发环境中创建 Q # 项目</span><span class="sxs-lookup"><span data-stu-id="de68e-103">Create a Q# project in your development environment</span></span>

<span data-ttu-id="de68e-104">了解如何使用 QDK 创建 Q # 项目。</span><span class="sxs-lookup"><span data-stu-id="de68e-104">Learn how to create a Q# project with the QDK.</span></span>

<span data-ttu-id="de68e-105">Q # 项目包含包含量程代码的 Q # 文件，以及运行量程程序的主机程序。</span><span class="sxs-lookup"><span data-stu-id="de68e-105">A Q# project contains Q# files containing quantum code, as well as a host program to run the quantum program.</span></span> <span data-ttu-id="de68e-106">可以用 .NET 语言（如 c # 或 Python）编写宿主程序。</span><span class="sxs-lookup"><span data-stu-id="de68e-106">You can write the host program in .NET languages such as C#, or in Python.</span></span> <span data-ttu-id="de68e-107">你还可以使用 IQ # 内核在 Jupyter Notebook 中运行 Q # 代码。</span><span class="sxs-lookup"><span data-stu-id="de68e-107">You can also run Q# code in a Jupyter Notebook using the IQ# kernel.</span></span>

<span data-ttu-id="de68e-108">从以下部分选择你的开发环境和语言：</span><span class="sxs-lookup"><span data-stu-id="de68e-108">Choose your development environment and language from the sections below:</span></span>

* [<span data-ttu-id="de68e-109">Python</span><span class="sxs-lookup"><span data-stu-id="de68e-109">Python</span></span>](#create-a-python-project)
* [<span data-ttu-id="de68e-110">Q# Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="de68e-110">Q# Jupyter Notebooks</span></span>](#create-a-q-jupyter-notebook-project)
* [<span data-ttu-id="de68e-111">C # 与 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="de68e-111">C# with Visual Studio</span></span>](#create-a-c-project-on-windows-using-visual-studio)
* [<span data-ttu-id="de68e-112">C # 与 VS Code</span><span class="sxs-lookup"><span data-stu-id="de68e-112">C# with VS Code</span></span>](#create-a-c-project-using-vs-code)
* [<span data-ttu-id="de68e-113">C # 与命令行</span><span class="sxs-lookup"><span data-stu-id="de68e-113">C# with the command line</span></span>](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a><span data-ttu-id="de68e-114">创建 Python 项目</span><span class="sxs-lookup"><span data-stu-id="de68e-114">Create a Python project</span></span>

1. <span data-ttu-id="de68e-115">先决条件</span><span class="sxs-lookup"><span data-stu-id="de68e-115">Pre-requisites</span></span>

     * <span data-ttu-id="de68e-116">安装[适用于 Python 的量程开发工具包](xref:microsoft.quantum.install.python)</span><span class="sxs-lookup"><span data-stu-id="de68e-116">Install the [Quantum Development Kit for Python](xref:microsoft.quantum.install.python)</span></span>

1. <span data-ttu-id="de68e-117">为项目创建一个文件夹，并导航到该文件夹</span><span class="sxs-lookup"><span data-stu-id="de68e-117">Create a folder for your project, and navigate to that folder</span></span>

1. <span data-ttu-id="de68e-118">创建一个名为的 Q # 文件 `Operation.qs` ，并向其添加 q # 代码。</span><span class="sxs-lookup"><span data-stu-id="de68e-118">Create a Q# file called `Operation.qs`, and add your Q# code to it.</span></span> <span data-ttu-id="de68e-119">例如：</span><span class="sxs-lookup"><span data-stu-id="de68e-119">For example:</span></span>

    ```qsharp
    namespace HelloWorld {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation SayHello() : Result {
            Message("Hello from quantum world!");
            return Zero;
        }
    }
    ```

1. <span data-ttu-id="de68e-120">创建一个名为的 python 主机文件 `host.py` 来调用 Q # 操作。</span><span class="sxs-lookup"><span data-stu-id="de68e-120">Create a python host file called `host.py` to call your Q# operation.</span></span> <span data-ttu-id="de68e-121">例如：</span><span class="sxs-lookup"><span data-stu-id="de68e-121">For example:</span></span>

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. <span data-ttu-id="de68e-122">运行该程序：</span><span class="sxs-lookup"><span data-stu-id="de68e-122">Run the program:</span></span>

    ```
    python host.py
    ```

1. <span data-ttu-id="de68e-123">验证输出。</span><span class="sxs-lookup"><span data-stu-id="de68e-123">Verify the output.</span></span> <span data-ttu-id="de68e-124">程序应输出以下行：</span><span class="sxs-lookup"><span data-stu-id="de68e-124">Your program should output the following lines:</span></span>

    ```
    Hello from quantum world!
    0
    ```

<span data-ttu-id="de68e-125">现在，你可以继续开发量程计划。</span><span class="sxs-lookup"><span data-stu-id="de68e-125">You can now continue to develop your quantum program.</span></span>

## <a name="create-a-q-jupyter-notebook-project"></a><span data-ttu-id="de68e-126">创建 Q # Jupyter Notebook 项目</span><span class="sxs-lookup"><span data-stu-id="de68e-126">Create a Q# Jupyter Notebook project</span></span>

1. <span data-ttu-id="de68e-127">先决条件</span><span class="sxs-lookup"><span data-stu-id="de68e-127">Pre-requisites</span></span>

    * <span data-ttu-id="de68e-128">安装[适用于 Jupyter 笔记本的量程开发工具包](xref:microsoft.quantum.install.jupyter)</span><span class="sxs-lookup"><span data-stu-id="de68e-128">Install the [Quantum Development Kit for Jupyter Notebooks](xref:microsoft.quantum.install.jupyter)</span></span>

1. <span data-ttu-id="de68e-129">运行以下命令以启动 Notebook 服务器：</span><span class="sxs-lookup"><span data-stu-id="de68e-129">Run the following command to start the notebook server:</span></span>

    ```
    jupyter notebook
    ```

1. <span data-ttu-id="de68e-130">浏览到命令行上显示的 URL。</span><span class="sxs-lookup"><span data-stu-id="de68e-130">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="de68e-131">例如：[http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span><span class="sxs-lookup"><span data-stu-id="de68e-131">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

1. <span data-ttu-id="de68e-132">浏览器中将出现一个 Jupyter 页。</span><span class="sxs-lookup"><span data-stu-id="de68e-132">A Jupyter page appears in the browser.</span></span> <span data-ttu-id="de68e-133">在 "**文件**" 选项卡上，选择 "**新建**  >  **q #** " 以创建带有 Q # 内核的 Jupyter Notebook。</span><span class="sxs-lookup"><span data-stu-id="de68e-133">On the **Files** tab, select **New** > **Q#** to create a Jupyter Notebook with a Q# kernel.</span></span> <span data-ttu-id="de68e-134">将以下代码添加到第一个笔记本单元：</span><span class="sxs-lookup"><span data-stu-id="de68e-134">Add the following code to the first notebook cell:</span></span>

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. <span data-ttu-id="de68e-135">选择**单元格**  >  **运行单元格**以运行笔记本。</span><span class="sxs-lookup"><span data-stu-id="de68e-135">Select **Cell** > **Run Cells** to run the notebook.</span></span> <span data-ttu-id="de68e-136">`SayHello`单元格输出中很快会出现：</span><span class="sxs-lookup"><span data-stu-id="de68e-136">`SayHello` will soon appear in the cell output:</span></span>

    ![带有 Q # 代码的单元格 Jupyter Notebook](~/media/install-guide-jupyter.png)

    <span data-ttu-id="de68e-138">在 Jupyter 笔记本中运行时，将编译 Q # 代码，然后笔记本将输出找到的操作的名称。</span><span class="sxs-lookup"><span data-stu-id="de68e-138">When running in Jupyter Notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

1. <span data-ttu-id="de68e-139">在新单元格中，模拟执行刚刚使用 `%simulate` magic 创建的量子计算机操作：</span><span class="sxs-lookup"><span data-stu-id="de68e-139">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

    ![具有% 模拟幻数的 Jupyter Notebook 单元](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="de68e-141">应会看到在屏幕上显示的消息以及所调用操作的结果（在本例中为空）。</span><span class="sxs-lookup"><span data-stu-id="de68e-141">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>

<span data-ttu-id="de68e-142">你现在可以添加其他 Q # 操作来继续进行量程开发。</span><span class="sxs-lookup"><span data-stu-id="de68e-142">You can now add other Q# operations to continue your quantum development.</span></span>

## <a name="create-a-c-project-on-windows-using-visual-studio"></a><span data-ttu-id="de68e-143">使用 Visual Studio 在 Windows 上创建 c # 项目</span><span class="sxs-lookup"><span data-stu-id="de68e-143">Create a C# project on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="de68e-144">先决条件</span><span class="sxs-lookup"><span data-stu-id="de68e-144">Pre-requisites</span></span>

    * <span data-ttu-id="de68e-145">安装[适用于 Visual Studio 的量程开发工具包扩展](xref:microsoft.quantum.install.cs)</span><span class="sxs-lookup"><span data-stu-id="de68e-145">Install the [Quantum Development Kit extension for Visual Studio](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="de68e-146">创建新的 Q# 应用程序</span><span class="sxs-lookup"><span data-stu-id="de68e-146">Create a new Q# application</span></span>

    * <span data-ttu-id="de68e-147">中转到 "**文件**" "  ->  **新建**  ->  **项目**"</span><span class="sxs-lookup"><span data-stu-id="de68e-147">Go to **File** -> **New** -> **Project**</span></span>
    * <span data-ttu-id="de68e-148">在搜索框中键入 `Q#`</span><span class="sxs-lookup"><span data-stu-id="de68e-148">Type `Q#` in the search box</span></span>
    * <span data-ttu-id="de68e-149">选择“Q# 应用程序”\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="de68e-149">Select **Q# Application**</span></span>
    * <span data-ttu-id="de68e-150">选择“下一步”</span><span class="sxs-lookup"><span data-stu-id="de68e-150">Select **Next**</span></span>
    * <span data-ttu-id="de68e-151">为应用程序选择名称和位置</span><span class="sxs-lookup"><span data-stu-id="de68e-151">Choose a name and location for your application</span></span>
    * <span data-ttu-id="de68e-152">选择“创建”</span><span class="sxs-lookup"><span data-stu-id="de68e-152">Select **Create**</span></span>

1. <span data-ttu-id="de68e-153">检查项目</span><span class="sxs-lookup"><span data-stu-id="de68e-153">Inspect the project</span></span>

    <span data-ttu-id="de68e-154">应该会看到已创建两个文件：`Driver.cs`，它是 C# 主机应用程序；以及 `Operation.qs`，它是定义将消息打印到控制台的简单操作的 Q# 程序。</span><span class="sxs-lookup"><span data-stu-id="de68e-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

1. <span data-ttu-id="de68e-155">运行应用程序</span><span class="sxs-lookup"><span data-stu-id="de68e-155">Run the application</span></span>

    * <span data-ttu-id="de68e-156">选择 "**调试**开始" （  ->  **不调试**）</span><span class="sxs-lookup"><span data-stu-id="de68e-156">Select **Debug** -> **Start Without Debugging**</span></span>
    * <span data-ttu-id="de68e-157">应该会看到打印到控制台窗口的文本 `Hello quantum world!`。</span><span class="sxs-lookup"><span data-stu-id="de68e-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

<span data-ttu-id="de68e-158">你现在可以使用 Visual Studio 继续进行量程开发</span><span class="sxs-lookup"><span data-stu-id="de68e-158">You can now continue your quantum development using Visual Studio</span></span>

> [!NOTE]
> * <span data-ttu-id="de68e-159">如果一个 Visual Studio 解决方案中具有多个项目，解决方案中包含的所有项目都需要位于解决方案所在的同一文件夹中，或位于其中一个子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="de68e-159">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="create-a-c-project-using-vs-code"></a><span data-ttu-id="de68e-160">使用 VS Code 创建 c # 项目</span><span class="sxs-lookup"><span data-stu-id="de68e-160">Create a C# project, using VS Code</span></span>

1. <span data-ttu-id="de68e-161">先决条件</span><span class="sxs-lookup"><span data-stu-id="de68e-161">Pre-requisites</span></span>

    * <span data-ttu-id="de68e-162">安装[VS Code 的量程开发工具包扩展](xref:microsoft.quantum.install.cs)</span><span class="sxs-lookup"><span data-stu-id="de68e-162">Install the [Quantum Development Kit extension for VS Code](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="de68e-163">创建新项目：</span><span class="sxs-lookup"><span data-stu-id="de68e-163">Create a new project:</span></span>

    * <span data-ttu-id="de68e-164">中转到 "**视图**"  ->  **命令面板**</span><span class="sxs-lookup"><span data-stu-id="de68e-164">Go to **View** -> **Command Palette**</span></span>
    * <span data-ttu-id="de68e-165">选择**Q #：创建新项目**</span><span class="sxs-lookup"><span data-stu-id="de68e-165">Select **Q#: Create New Project**</span></span>
    * <span data-ttu-id="de68e-166">选择**独立控制台应用程序**</span><span class="sxs-lookup"><span data-stu-id="de68e-166">Select **Standalone console application**</span></span>
    * <span data-ttu-id="de68e-167">导航到要在其中创建应用程序的文件系统上的位置</span><span class="sxs-lookup"><span data-stu-id="de68e-167">Navigate to the location on the file system where you would like to create the application</span></span>
    * <span data-ttu-id="de68e-168">创建项目后，单击“打开新项目...”\*\*\*\* 按钮</span><span class="sxs-lookup"><span data-stu-id="de68e-168">Click on the **Open new project...** button, once the project has been created</span></span>

1. <span data-ttu-id="de68e-169">运行应用程序：</span><span class="sxs-lookup"><span data-stu-id="de68e-169">Run the application:</span></span>

    * <span data-ttu-id="de68e-170">中转到**终端**  ->  **新终端**</span><span class="sxs-lookup"><span data-stu-id="de68e-170">Go to **Terminal** -> **New Terminal**</span></span>
    * <span data-ttu-id="de68e-171">输入 `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="de68e-171">Enter `dotnet run`</span></span>
    * <span data-ttu-id="de68e-172">应在输出窗口 `Hello quantum world!` 中看到以下文本</span><span class="sxs-lookup"><span data-stu-id="de68e-172">You should see the following text in the output window `Hello quantum world!`</span></span>

<span data-ttu-id="de68e-173">你现在可以使用 Visual Studio Code 继续进行量程开发。</span><span class="sxs-lookup"><span data-stu-id="de68e-173">You can now continue your quantum development using Visual Studio Code.</span></span>

> [!NOTE]
> * <span data-ttu-id="de68e-174">Visual Studio Code 扩展当前不支持具有多个根文件夹的工作区。</span><span class="sxs-lookup"><span data-stu-id="de68e-174">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="de68e-175">如果一个 VS Code 工作区中具有多个项目，则所有项目都必须包含在同一个根文件夹中。</span><span class="sxs-lookup"><span data-stu-id="de68e-175">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a><span data-ttu-id="de68e-176">使用命令行工具创建 c # 项目 `dotnet`</span><span class="sxs-lookup"><span data-stu-id="de68e-176">Create a C# project, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="de68e-177">先决条件</span><span class="sxs-lookup"><span data-stu-id="de68e-177">Pre-requisites</span></span>

    * <span data-ttu-id="de68e-178">安装[命令行的量程开发工具包](xref:microsoft.quantum.install.standalone)</span><span class="sxs-lookup"><span data-stu-id="de68e-178">Install the [Quantum Development Kit for the command line](xref:microsoft.quantum.install.standalone)</span></span>

1. <span data-ttu-id="de68e-179">创建新应用程序</span><span class="sxs-lookup"><span data-stu-id="de68e-179">Create a new application</span></span>

    ```dotnetcli
    dotnet new console -lang Q# -o <project name>
    ```

1. <span data-ttu-id="de68e-180">导航到新的应用程序目录</span><span class="sxs-lookup"><span data-stu-id="de68e-180">Navigate to the new application directory</span></span>

    ```
    cd <project name>
    ```

    <span data-ttu-id="de68e-181">应该会看到已创建两个文件，以及应用程序的项目文件：Q# 文件 (`Operation.qs`) 和 C# 主机文件 (`Driver.cs`)。</span><span class="sxs-lookup"><span data-stu-id="de68e-181">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

1. <span data-ttu-id="de68e-182">运行应用程序</span><span class="sxs-lookup"><span data-stu-id="de68e-182">Run the application</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="de68e-183">应该会看到以下输出：`Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="de68e-183">You should see the following output: `Hello quantum world!`</span></span>

<span data-ttu-id="de68e-184">现在，使用命令行工具继续进行量程开发。</span><span class="sxs-lookup"><span data-stu-id="de68e-184">You now continue your quantum development, using command line tools.</span></span>

## <a name="next-steps"></a><span data-ttu-id="de68e-185">后续步骤</span><span class="sxs-lookup"><span data-stu-id="de68e-185">Next steps</span></span>

<span data-ttu-id="de68e-186">现在您已在首选环境中创建了一个项目，您可以继续进行量程开发。</span><span class="sxs-lookup"><span data-stu-id="de68e-186">Now that you have created a project in your preferred environment, you can continue your quantum development.</span></span>
