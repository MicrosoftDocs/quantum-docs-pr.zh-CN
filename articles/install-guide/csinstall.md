---
title: '用 Q # + 开发C#'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 1fd829c684502092bb7491b0f46b5f690320c941
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831012"
---
# <a name="develop-with-q--c"></a><span data-ttu-id="ae2e8-102">用 Q # + 开发C#</span><span class="sxs-lookup"><span data-stu-id="ae2e8-102">Develop with Q# + C#</span></span>

<span data-ttu-id="ae2e8-103">安装 QDK 以开发C#主机程序以调用 Q # 操作。</span><span class="sxs-lookup"><span data-stu-id="ae2e8-103">Install the QDK to develop C# host programs to call Q# operations.</span></span>

<span data-ttu-id="ae2e8-104">Q # 构建为适用于 .NET 语言（特别是C#）。</span><span class="sxs-lookup"><span data-stu-id="ae2e8-104">Q# is built to play well with .NET languages--specifically C#.</span></span> <span data-ttu-id="ae2e8-105">可以在不同的开发环境中使用此配对：</span><span class="sxs-lookup"><span data-stu-id="ae2e8-105">You can work with this pairing inside different development environments:</span></span>

- [<span data-ttu-id="ae2e8-106">使用 Visual Studio C#的 Q # + （Windows）</span><span class="sxs-lookup"><span data-stu-id="ae2e8-106">Q# + C# using Visual Studio (Windows)</span></span>](#VS)
- [<span data-ttu-id="ae2e8-107">使用 Visual Studio Code 的C# Q # + （Windows、Linux 和 Mac）</span><span class="sxs-lookup"><span data-stu-id="ae2e8-107">Q# + C# using Visual Studio Code (Windows, Linux and Mac)</span></span>](#VSC)
- [<span data-ttu-id="ae2e8-108">使用 `dotnet` 命令C#行工具的 Q # +</span><span class="sxs-lookup"><span data-stu-id="ae2e8-108">Q# + C# using the `dotnet` command-line tool</span></span>](#command)

## <span data-ttu-id="ae2e8-109">使用 Visual Studio 通过 Q C# # + 进行开发<a name="VS"></a></span><span class="sxs-lookup"><span data-stu-id="ae2e8-109">Develop with Q# + C# using Visual Studio <a name="VS"></a></span></span>

<span data-ttu-id="ae2e8-110">Visual Studio 提供了一个用于开发 Q # 程序的丰富环境。</span><span class="sxs-lookup"><span data-stu-id="ae2e8-110">Visual Studio offers a rich environment for developing Q# programs.</span></span> <span data-ttu-id="ae2e8-111">Q # Visual Studio 扩展包含用于 Q # 文件和项目的模板，以及语法突出显示、代码完成和 IntelliSense 支持。</span><span class="sxs-lookup"><span data-stu-id="ae2e8-111">The Q# Visual Studio extension contains templates for Q# files and projects as well as syntax highlighting, code completion and IntelliSense support.</span></span>


1. <span data-ttu-id="ae2e8-112">必备组件</span><span class="sxs-lookup"><span data-stu-id="ae2e8-112">Pre-requisites</span></span>

    - <span data-ttu-id="ae2e8-113">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3，启用了 .NET Core 跨平台开发工作负载。</span><span class="sxs-lookup"><span data-stu-id="ae2e8-113">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="ae2e8-114">安装 Q# Visual Studio 扩展</span><span class="sxs-lookup"><span data-stu-id="ae2e8-114">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="ae2e8-115">下载并安装[Visual Studio 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="ae2e8-115">Download and install the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>

1. <span data-ttu-id="ae2e8-116">通过创建 `Hello World` 应用程序来验证安装</span><span class="sxs-lookup"><span data-stu-id="ae2e8-116">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="ae2e8-117">创建新的 Q# 应用程序</span><span class="sxs-lookup"><span data-stu-id="ae2e8-117">Create a new Q# application</span></span>

        - <span data-ttu-id="ae2e8-118">转到“文件” -> “新建” -> “项目”</span><span class="sxs-lookup"><span data-stu-id="ae2e8-118">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="ae2e8-119">在搜索框中键入 `Q#`</span><span class="sxs-lookup"><span data-stu-id="ae2e8-119">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="ae2e8-120">选择“Q# 应用程序”</span><span class="sxs-lookup"><span data-stu-id="ae2e8-120">Select **Q# Application**</span></span>
        - <span data-ttu-id="ae2e8-121">选择“下一步”</span><span class="sxs-lookup"><span data-stu-id="ae2e8-121">Select **Next**</span></span>
        - <span data-ttu-id="ae2e8-122">为应用程序选择名称和位置</span><span class="sxs-lookup"><span data-stu-id="ae2e8-122">Choose a name and location for your application</span></span>
        - <span data-ttu-id="ae2e8-123">选择“创建”</span><span class="sxs-lookup"><span data-stu-id="ae2e8-123">Select **Create**</span></span>

    - <span data-ttu-id="ae2e8-124">检查项目</span><span class="sxs-lookup"><span data-stu-id="ae2e8-124">Inspect the project</span></span>

        <span data-ttu-id="ae2e8-125">应该会看到已创建两个文件：`Driver.cs`，它是 C# 主机应用程序；以及 `Operation.qs`，它是定义将消息打印到控制台的简单操作的 Q# 程序。</span><span class="sxs-lookup"><span data-stu-id="ae2e8-125">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="ae2e8-126">运行应用程序</span><span class="sxs-lookup"><span data-stu-id="ae2e8-126">Run the application</span></span>

        - <span data-ttu-id="ae2e8-127">选择“调试” -> “在不调试的情况下启动”</span><span class="sxs-lookup"><span data-stu-id="ae2e8-127">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="ae2e8-128">应该会看到打印到控制台窗口的文本 `Hello quantum world!`。</span><span class="sxs-lookup"><span data-stu-id="ae2e8-128">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="ae2e8-129">如果一个 Visual Studio 解决方案中具有多个项目，解决方案中包含的所有项目都需要位于解决方案所在的同一文件夹中，或位于其中一个子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ae2e8-129">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <span data-ttu-id="ae2e8-130">使用 Q # + C#进行开发 Visual Studio Code<a name="VSC"></a></span><span class="sxs-lookup"><span data-stu-id="ae2e8-130">Develop with Q# + C# using Visual Studio Code <a name="VSC"></a></span></span>

<span data-ttu-id="ae2e8-131">Visual Studio Code （VS Code）提供了一个丰富的环境，用于在 Windows、Linux 和 Mac 上开发 Q # 程序。</span><span class="sxs-lookup"><span data-stu-id="ae2e8-131">Visual Studio Code (VS Code) offers a rich environment for developing Q# programs on Windows, Linux and Mac.</span></span>  <span data-ttu-id="ae2e8-132">Q # VS Code 扩展包括对 Q # 语法突出显示、代码完成和 Q # 代码片段的支持。</span><span class="sxs-lookup"><span data-stu-id="ae2e8-132">The Q# VS Code extension includes support for Q# syntax highlighting, code completion, and Q# code snippets.</span></span>

1. <span data-ttu-id="ae2e8-133">必备组件</span><span class="sxs-lookup"><span data-stu-id="ae2e8-133">Pre-requisites</span></span>

   - [<span data-ttu-id="ae2e8-134">VS Code</span><span class="sxs-lookup"><span data-stu-id="ae2e8-134">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="ae2e8-135">.NET Core SDK 3.1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="ae2e8-135">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="ae2e8-136">安装量子 VS Code 扩展</span><span class="sxs-lookup"><span data-stu-id="ae2e8-136">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="ae2e8-137">安装 [VS Code 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span><span class="sxs-lookup"><span data-stu-id="ae2e8-137">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="ae2e8-138">安装量子项目模板：</span><span class="sxs-lookup"><span data-stu-id="ae2e8-138">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="ae2e8-139">转到“视图” -> “命令面板”</span><span class="sxs-lookup"><span data-stu-id="ae2e8-139">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="ae2e8-140">选择**Q #：安装项目模板**</span><span class="sxs-lookup"><span data-stu-id="ae2e8-140">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="ae2e8-141">现已安装量子开发工具包，并且可以在自己的应用程序和库中使用。</span><span class="sxs-lookup"><span data-stu-id="ae2e8-141">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="ae2e8-142">通过创建 `Hello World` 应用程序来验证安装</span><span class="sxs-lookup"><span data-stu-id="ae2e8-142">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="ae2e8-143">创建新项目：</span><span class="sxs-lookup"><span data-stu-id="ae2e8-143">Create a new project:</span></span>

        - <span data-ttu-id="ae2e8-144">转到“视图” -> “命令面板”</span><span class="sxs-lookup"><span data-stu-id="ae2e8-144">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="ae2e8-145">选择**Q #：创建新项目**</span><span class="sxs-lookup"><span data-stu-id="ae2e8-145">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="ae2e8-146">选择**独立控制台应用程序**</span><span class="sxs-lookup"><span data-stu-id="ae2e8-146">Select **Standalone console application**</span></span>
        - <span data-ttu-id="ae2e8-147">导航到要在其中创建应用程序的文件系统上的位置</span><span class="sxs-lookup"><span data-stu-id="ae2e8-147">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="ae2e8-148">创建项目后，单击“打开新项目...”按钮</span><span class="sxs-lookup"><span data-stu-id="ae2e8-148">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="ae2e8-149">如果尚未安装 VS Code 的C#扩展，将显示一个弹出窗口。</span><span class="sxs-lookup"><span data-stu-id="ae2e8-149">If you don't already have the C# extension for VS Code installed, a pop-up will appear.</span></span> <span data-ttu-id="ae2e8-150">安装扩展。</span><span class="sxs-lookup"><span data-stu-id="ae2e8-150">Install the extension.</span></span> 

    - <span data-ttu-id="ae2e8-151">运行应用程序：</span><span class="sxs-lookup"><span data-stu-id="ae2e8-151">Run the application:</span></span>

        - <span data-ttu-id="ae2e8-152">中转到**终端** -> **新终端**</span><span class="sxs-lookup"><span data-stu-id="ae2e8-152">Go to **Terminal** -> **New Terminal**</span></span>
        - <span data-ttu-id="ae2e8-153">输入 `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="ae2e8-153">Enter `dotnet run`</span></span>
        - <span data-ttu-id="ae2e8-154">应在输出窗口 `Hello quantum world!` 中看到以下文本</span><span class="sxs-lookup"><span data-stu-id="ae2e8-154">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> * <span data-ttu-id="ae2e8-155">Visual Studio Code 扩展当前不支持具有多个根文件夹的工作区。</span><span class="sxs-lookup"><span data-stu-id="ae2e8-155">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="ae2e8-156">如果一个 VS Code 工作区中具有多个项目，则所有项目都必须包含在同一个根文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ae2e8-156">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <span data-ttu-id="ae2e8-157">使用 `dotnet` 命令行工具C#通过 Q # + 进行开发<a name="command"></a></span><span class="sxs-lookup"><span data-stu-id="ae2e8-157">Develop with Q# + C# using the `dotnet` command-line tool <a name="command"></a></span></span>

<span data-ttu-id="ae2e8-158">当然，只需安装 .NET Core SDK 和 QDK 项目模板，就可以从命令行生成和运行 Q# 程序。</span><span class="sxs-lookup"><span data-stu-id="ae2e8-158">Of course, you can also build and run Q# programs from the command line by simply installing the .NET Core SDK and the QDK project templates.</span></span> 

1. <span data-ttu-id="ae2e8-159">必备组件</span><span class="sxs-lookup"><span data-stu-id="ae2e8-159">Pre-requisites</span></span>

    - [<span data-ttu-id="ae2e8-160">.NET Core SDK 3.1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="ae2e8-160">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="ae2e8-161">安装适用于 .NET 的量子项目模板</span><span class="sxs-lookup"><span data-stu-id="ae2e8-161">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="ae2e8-162">现已安装量子开发工具包，并且可以在自己的应用程序和库中使用。</span><span class="sxs-lookup"><span data-stu-id="ae2e8-162">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="ae2e8-163">通过创建 `Hello World` 应用程序来验证安装</span><span class="sxs-lookup"><span data-stu-id="ae2e8-163">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="ae2e8-164">创建新应用程序</span><span class="sxs-lookup"><span data-stu-id="ae2e8-164">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="ae2e8-165">导航到新的应用程序目录</span><span class="sxs-lookup"><span data-stu-id="ae2e8-165">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="ae2e8-166">应该会看到已创建两个文件，以及应用程序的项目文件：Q# 文件 (`Operation.qs`) 和 C# 主机文件 (`Driver.cs`)。</span><span class="sxs-lookup"><span data-stu-id="ae2e8-166">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="ae2e8-167">运行应用程序</span><span class="sxs-lookup"><span data-stu-id="ae2e8-167">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="ae2e8-168">应该会看到以下输出：`Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="ae2e8-168">You should see the following output: `Hello quantum world!`</span></span>

    
## <a name="whats-next"></a><span data-ttu-id="ae2e8-169">还有什么？</span><span class="sxs-lookup"><span data-stu-id="ae2e8-169">What's next?</span></span>

<span data-ttu-id="ae2e8-170">在首选环境中安装量子开发工具包后，可以编写并运行[第一个量子程序](xref:microsoft.quantum.write-program)。</span><span class="sxs-lookup"><span data-stu-id="ae2e8-170">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
