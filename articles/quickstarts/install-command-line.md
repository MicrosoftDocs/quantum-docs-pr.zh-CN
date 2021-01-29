---
title: 在 IDE 中使用 Q# 应用程序进行开发
description: 了解如何创建从命令提示符运行的 Q# 应用程序。
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: quickstart
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3e4f1e97477ecb0547b1586b1c7603c8a9954584
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844320"
---
# <a name="develop-with-no-locq-applications-in-an-ide"></a><span data-ttu-id="1381b-103">在 IDE 中使用 Q# 应用程序进行开发</span><span class="sxs-lookup"><span data-stu-id="1381b-103">Develop with Q# applications in an IDE</span></span>

<span data-ttu-id="1381b-104">Q# 程序可自己运行，无需采用 C#、F# 或 Python 等主机语言的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="1381b-104">Q# programs can run on their own, without a driver in a host language like C#, F#, or Python.</span></span> <span data-ttu-id="1381b-105">可在 Visual Studio Code (VS Code)、Visual Studio、Visual Studio Codespaces 中，或者使用任何编辑器/IDE 来开发 Q# 应用程序，并通过 .NET 控制台运行这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="1381b-105">You can develop Q# applications in Visual Studio Code (VS Code), Visual Studio, Visual Studio Codespaces, or with any editor/IDE and run applications from the .NET console.</span></span> 

## <a name="prerequisites-for-all-environments"></a><span data-ttu-id="1381b-106">面向所有环境的先决条件</span><span class="sxs-lookup"><span data-stu-id="1381b-106">Prerequisites for all environments</span></span>

- [<span data-ttu-id="1381b-107">.NET Core SDK 3.1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="1381b-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="1381b-108">安装</span><span class="sxs-lookup"><span data-stu-id="1381b-108">Installation</span></span>

<span data-ttu-id="1381b-109">在任何 IDE 中构建 Q# 应用程序时，建议使用 Visual Studio Code (VS Code) 或 Visual Studio IDE 在本地开发 Q# 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1381b-109">While you can build Q# applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your Q# applications locally.</span></span> <span data-ttu-id="1381b-110">若要通过 Web 浏览器在云中开发，建议使用 Visual Studio Codespaces。</span><span class="sxs-lookup"><span data-stu-id="1381b-110">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="1381b-111">在这些环境中进行开发会使用 QDK 扩展的丰富功能，这包括警告、语法突出显示和项目模板等。</span><span class="sxs-lookup"><span data-stu-id="1381b-111">Developing in these environments leverages the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

### <a name="to-configure-for-vs-code"></a><span data-ttu-id="1381b-112">若要为 VS Code 进行配置：</span><span class="sxs-lookup"><span data-stu-id="1381b-112">To configure for VS Code:</span></span>

1. <span data-ttu-id="1381b-113">下载并安装 [VS Code](https://code.visualstudio.com/download)（Windows、Linux 和 Mac）。</span><span class="sxs-lookup"><span data-stu-id="1381b-113">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="1381b-114">安装[适用于 VS Code 的 Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)。</span><span class="sxs-lookup"><span data-stu-id="1381b-114">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

### <a name="to-configure-for-visual-studio"></a><span data-ttu-id="1381b-115">若要为 Visual Studio 进行配置：</span><span class="sxs-lookup"><span data-stu-id="1381b-115">To configure for Visual Studio:</span></span>

1. <span data-ttu-id="1381b-116">下载并安装 [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 或更高版本，并启用 .NET Core 跨平台开发工作负载。</span><span class="sxs-lookup"><span data-stu-id="1381b-116">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="1381b-117">下载并安装 [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)。</span><span class="sxs-lookup"><span data-stu-id="1381b-117">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

### <a name="to-configure-for-another-environment"></a><span data-ttu-id="1381b-118">若要为另一环境进行配置：</span><span class="sxs-lookup"><span data-stu-id="1381b-118">To configure for another environment:</span></span> 

1. <span data-ttu-id="1381b-119">在命令提示符处输入以下内容</span><span class="sxs-lookup"><span data-stu-id="1381b-119">Enter the following at the command prompt</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

### <a name="to-configure-for-visual-studio-codespaces"></a><span data-ttu-id="1381b-120">若要为 Visual Studio Codespaces 进行配置：</span><span class="sxs-lookup"><span data-stu-id="1381b-120">To configure for Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="1381b-121">创建 [Azure 帐户](https://azure.microsoft.com/free/)。</span><span class="sxs-lookup"><span data-stu-id="1381b-121">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="1381b-122">创建一个 Codespaces 环境。</span><span class="sxs-lookup"><span data-stu-id="1381b-122">Create a Codespaces environment.</span></span> <span data-ttu-id="1381b-123">请按照[快速入门指南](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser)操作。</span><span class="sxs-lookup"><span data-stu-id="1381b-123">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span></span> <span data-ttu-id="1381b-124">创建 Codespace 时，建议在“Git 存储库”中输入 `microsoft/Quantum` 来加载 QDK 特定的设置。</span><span class="sxs-lookup"><span data-stu-id="1381b-124">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="1381b-125">现可启动新环境，通过 [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments) 在浏览器中开始开发。</span><span class="sxs-lookup"><span data-stu-id="1381b-125">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="1381b-126">或者，可使用 VS Code 的本地安装并将 Codespaces 用作[远程环境](https://docs.microsoft.com/visualstudio/online/how-to/vscode)。</span><span class="sxs-lookup"><span data-stu-id="1381b-126">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>

## <a name="develop-with-no-locq"></a><span data-ttu-id="1381b-127">使用 Q# 进行开发</span><span class="sxs-lookup"><span data-stu-id="1381b-127">Develop with Q#</span></span>

<span data-ttu-id="1381b-128">按照你的开发环境所对应的选项卡上的说明操作。</span><span class="sxs-lookup"><span data-stu-id="1381b-128">Follow the instructions on the tab corresponding to your development environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="1381b-129">VS Code</span><span class="sxs-lookup"><span data-stu-id="1381b-129">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="1381b-130">创建新项目：</span><span class="sxs-lookup"><span data-stu-id="1381b-130">To create a new project:</span></span>

1. <span data-ttu-id="1381b-131">单击“查看” -> “命令面板” ，然后选择“Q#:Create New Project”。</span><span class="sxs-lookup"><span data-stu-id="1381b-131">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="1381b-132">单击“独立控制台应用程序”。</span><span class="sxs-lookup"><span data-stu-id="1381b-132">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="1381b-133">导航到要保存项目的位置。</span><span class="sxs-lookup"><span data-stu-id="1381b-133">Navigate to the location to save the project.</span></span> <span data-ttu-id="1381b-134">输入项目名称，然后单击“创建项目”。</span><span class="sxs-lookup"><span data-stu-id="1381b-134">Enter the project name and click **Create Project**.</span></span>
4. <span data-ttu-id="1381b-135">成功创建项目后，单击右下方的“打开新项目…”。</span><span class="sxs-lookup"><span data-stu-id="1381b-135">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="1381b-136">检查项目。</span><span class="sxs-lookup"><span data-stu-id="1381b-136">Inspect the project.</span></span> <span data-ttu-id="1381b-137">你应该会看到一个名为 `Program.qs` 的源文件，该文件是一个 Q# 程序，用于定义将消息输出到控制台的简单操作。</span><span class="sxs-lookup"><span data-stu-id="1381b-137">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="1381b-138">运行应用程序：</span><span class="sxs-lookup"><span data-stu-id="1381b-138">To run the application:</span></span>

1. <span data-ttu-id="1381b-139">单击“终端” -> “新终端” 。</span><span class="sxs-lookup"><span data-stu-id="1381b-139">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="1381b-140">在终端提示符下，输入 `dotnet run`。</span><span class="sxs-lookup"><span data-stu-id="1381b-140">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="1381b-141">应在输出窗口 `Hello quantum world!` 中看到以下文本</span><span class="sxs-lookup"><span data-stu-id="1381b-141">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> <span data-ttu-id="1381b-142">VS Code Q# 扩展当前不支持具有多个根文件夹的工作区。</span><span class="sxs-lookup"><span data-stu-id="1381b-142">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="1381b-143">如果一个 VS Code 工作区中具有多个项目，则所有项目都必须包含在同一个根文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1381b-143">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="1381b-144">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1381b-144">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="1381b-145">创建 Q# `Hello World` 应用程序来验证 Visual Studio 安装。</span><span class="sxs-lookup"><span data-stu-id="1381b-145">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="1381b-146">若要创建新的 Q# 应用程序：</span><span class="sxs-lookup"><span data-stu-id="1381b-146">To create a new Q# application:</span></span>

1. <span data-ttu-id="1381b-147">打开 Visual Studio，单击“文件” -> “新建” -> “项目”  。</span><span class="sxs-lookup"><span data-stu-id="1381b-147">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="1381b-148">在“搜索”框中键入 `Q#`，选择“Q# 应用程序”，然后单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="1381b-148">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="1381b-149">输入应用程序的“名称”和“位置”，然后单击“创建”。</span><span class="sxs-lookup"><span data-stu-id="1381b-149">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="1381b-150">检查项目。</span><span class="sxs-lookup"><span data-stu-id="1381b-150">Inspect the project.</span></span> <span data-ttu-id="1381b-151">你应该会看到一个名为 `Program.qs` 的源文件，该文件是一个 Q# 程序，用于定义将消息输出到控制台的简单操作。</span><span class="sxs-lookup"><span data-stu-id="1381b-151">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="1381b-152">运行应用程序：</span><span class="sxs-lookup"><span data-stu-id="1381b-152">To run the application:</span></span>

1. <span data-ttu-id="1381b-153">选择“调试” -> “在不调试的情况下启动”。</span><span class="sxs-lookup"><span data-stu-id="1381b-153">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="1381b-154">应该会看到打印到控制台窗口的文本 `Hello quantum world!`。</span><span class="sxs-lookup"><span data-stu-id="1381b-154">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="1381b-155">如果一个 Visual Studio 解决方案中具有多个项目，解决方案中包含的所有项目都需要位于解决方案所在的同一文件夹中，或位于其中一个子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1381b-155">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-prompt"></a>[<span data-ttu-id="1381b-156">其他使用命令提示符的编辑器</span><span class="sxs-lookup"><span data-stu-id="1381b-156">Other editors with the command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="1381b-157">创建 Q# `Hello World` 应用程序来验证安装项。</span><span class="sxs-lookup"><span data-stu-id="1381b-157">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="1381b-158">创建新的应用程序：</span><span class="sxs-lookup"><span data-stu-id="1381b-158">Create a new application:</span></span>

    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. <span data-ttu-id="1381b-159">导航到应用程序目录：</span><span class="sxs-lookup"><span data-stu-id="1381b-159">Navigate to the application directory:</span></span>

    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="1381b-160">该目录现在应该会包含一个 `Program.qs` 文件，它是 Q# 程序，用于定义将消息输出到控制台的简单操作。</span><span class="sxs-lookup"><span data-stu-id="1381b-160">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="1381b-161">你可使用文本编辑器来修改此模板，并用你自己的量子应用程序来覆盖它。</span><span class="sxs-lookup"><span data-stu-id="1381b-161">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="1381b-162">运行该程序：</span><span class="sxs-lookup"><span data-stu-id="1381b-162">Run the program:</span></span>

    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="1381b-163">应会看到以下输出文本：`Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="1381b-163">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="1381b-164">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1381b-164">Next steps</span></span>

<span data-ttu-id="1381b-165">在首选环境中安装量子开发工具包后，可以编写并运行[第一个量子程序](xref:microsoft.quantum.quickstarts.qrng)。</span><span class="sxs-lookup"><span data-stu-id="1381b-165">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
