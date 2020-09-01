---
title: 使用 Q# 应用程序进行开发
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6a287dd76162a05d72af7e9d1e46533425283e2a
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863667"
---
# <a name="develop-with-no-locq-applications"></a><span data-ttu-id="3973a-102">使用 Q# 应用程序进行开发</span><span class="sxs-lookup"><span data-stu-id="3973a-102">Develop with Q# applications</span></span>

<span data-ttu-id="3973a-103">Q# 程序可自己执行，无需采用 C#、F# 或 Python 等主机语言的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="3973a-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3973a-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="3973a-104">Prerequisites</span></span>

- [<span data-ttu-id="3973a-105">.NET Core SDK 3.1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3973a-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="3973a-106">安装</span><span class="sxs-lookup"><span data-stu-id="3973a-106">Installation</span></span>

<span data-ttu-id="3973a-107">在任何 IDE 中构建 Q# 应用程序时，建议使用 Visual Studio Code (VS Code) 或 Visual Studio IDE 在本地开发 Q# 应用程序。</span><span class="sxs-lookup"><span data-stu-id="3973a-107">While you can build Q# applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your Q# applications locally.</span></span> <span data-ttu-id="3973a-108">若要通过 Web 浏览器在云中开发，建议使用 Visual Studio Codespaces。</span><span class="sxs-lookup"><span data-stu-id="3973a-108">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="3973a-109">在这些环境中开发涉及到丰富的 QDK 扩展功能，其中包括警告、语法突出显示和项目模板等。</span><span class="sxs-lookup"><span data-stu-id="3973a-109">Developing in these environments includes the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

<span data-ttu-id="3973a-110">配置 VS Code：</span><span class="sxs-lookup"><span data-stu-id="3973a-110">To configure VS Code:</span></span>

1. <span data-ttu-id="3973a-111">下载并安装 [VS Code](https://code.visualstudio.com/download)（Windows、Linux 和 Mac）。</span><span class="sxs-lookup"><span data-stu-id="3973a-111">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="3973a-112">安装[适用于 VS Code 的 Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)。</span><span class="sxs-lookup"><span data-stu-id="3973a-112">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="3973a-113">配置 Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="3973a-113">To configure Visual Studio:</span></span>

1. <span data-ttu-id="3973a-114">下载并安装 [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 或更高版本，并启用 .NET Core 跨平台开发工作负载。</span><span class="sxs-lookup"><span data-stu-id="3973a-114">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="3973a-115">下载并安装 [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)。</span><span class="sxs-lookup"><span data-stu-id="3973a-115">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

<span data-ttu-id="3973a-116">若要配置 Visual Studio Codespaces：</span><span class="sxs-lookup"><span data-stu-id="3973a-116">To configure Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="3973a-117">创建 [Azure 帐户](https://azure.microsoft.com/free/)。</span><span class="sxs-lookup"><span data-stu-id="3973a-117">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="3973a-118">创建一个 Codespaces 环境。</span><span class="sxs-lookup"><span data-stu-id="3973a-118">Create a Codespaces environment.</span></span> <span data-ttu-id="3973a-119">请按照[快速入门指南](https://docs.microsoft.com/visualstudio/online/quickstarts/browser)操作。</span><span class="sxs-lookup"><span data-stu-id="3973a-119">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/online/quickstarts/browser).</span></span> <span data-ttu-id="3973a-120">创建 Codespace 时，建议在“Git 存储库”中输入 `microsoft/Quantum` 来加载 QDK 特定的设置。</span><span class="sxs-lookup"><span data-stu-id="3973a-120">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="3973a-121">现可启动新环境，通过 [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments) 在浏览器中开始开发。</span><span class="sxs-lookup"><span data-stu-id="3973a-121">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="3973a-122">或者，可使用 VS Code 的本地安装并将 Codespaces 用作[远程环境](https://docs.microsoft.com/visualstudio/online/how-to/vscode)。</span><span class="sxs-lookup"><span data-stu-id="3973a-122">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>


<span data-ttu-id="3973a-123">若要为另一环境安装 QDK，请在命令提示符处输入：</span><span class="sxs-lookup"><span data-stu-id="3973a-123">To install the QDK for another environment, enter at the command prompt:</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-no-locq"></a><span data-ttu-id="3973a-124">使用 Q# 进行开发</span><span class="sxs-lookup"><span data-stu-id="3973a-124">Develop with Q#</span></span>

<span data-ttu-id="3973a-125">按照你的环境所对应的选项卡上的说明操作。</span><span class="sxs-lookup"><span data-stu-id="3973a-125">Follow the instructions at the tab corresponding to your environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="3973a-126">VS Code</span><span class="sxs-lookup"><span data-stu-id="3973a-126">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="3973a-127">创建新项目：</span><span class="sxs-lookup"><span data-stu-id="3973a-127">To create a new project:</span></span>

1. <span data-ttu-id="3973a-128">单击“查看” -> “命令面板” ，然后选择“Q#:Create New Project”。</span><span class="sxs-lookup"><span data-stu-id="3973a-128">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="3973a-129">单击“独立控制台应用程序”。</span><span class="sxs-lookup"><span data-stu-id="3973a-129">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="3973a-130">导航到项目的保存位置，然后单击“创建项目”。</span><span class="sxs-lookup"><span data-stu-id="3973a-130">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="3973a-131">成功创建项目后，单击右下方的“打开新项目…”。</span><span class="sxs-lookup"><span data-stu-id="3973a-131">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="3973a-132">检查项目。</span><span class="sxs-lookup"><span data-stu-id="3973a-132">Inspect the project.</span></span> <span data-ttu-id="3973a-133">你应该会看到一个名为 `Program.qs` 的源文件，该文件是一个 Q# 程序，用于定义将消息输出到控制台的简单操作。</span><span class="sxs-lookup"><span data-stu-id="3973a-133">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="3973a-134">运行应用程序：</span><span class="sxs-lookup"><span data-stu-id="3973a-134">To run the application:</span></span>
1. <span data-ttu-id="3973a-135">单击“终端” -> “新终端” 。</span><span class="sxs-lookup"><span data-stu-id="3973a-135">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="3973a-136">在终端提示符下，输入 `dotnet run`。</span><span class="sxs-lookup"><span data-stu-id="3973a-136">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="3973a-137">应在输出窗口 `Hello quantum world!` 中看到以下文本</span><span class="sxs-lookup"><span data-stu-id="3973a-137">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="3973a-138">VS Code Q# 扩展当前不支持具有多个根文件夹的工作区。</span><span class="sxs-lookup"><span data-stu-id="3973a-138">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="3973a-139">如果一个 VS Code 工作区中具有多个项目，则所有项目都必须包含在同一个根文件夹中。</span><span class="sxs-lookup"><span data-stu-id="3973a-139">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="3973a-140">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3973a-140">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="3973a-141">创建 Q# `Hello World` 应用程序来验证 Visual Studio 安装。</span><span class="sxs-lookup"><span data-stu-id="3973a-141">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="3973a-142">若要创建新的 Q# 应用程序：</span><span class="sxs-lookup"><span data-stu-id="3973a-142">To create a new Q# application:</span></span>
1. <span data-ttu-id="3973a-143">打开 Visual Studio，单击“文件” -> “新建” -> “项目”  。</span><span class="sxs-lookup"><span data-stu-id="3973a-143">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="3973a-144">在“搜索”框中键入 `Q#`，选择“Q# 应用程序”，然后单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="3973a-144">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="3973a-145">输入应用程序的“名称”和“位置”，然后单击“创建”。</span><span class="sxs-lookup"><span data-stu-id="3973a-145">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="3973a-146">检查项目。</span><span class="sxs-lookup"><span data-stu-id="3973a-146">Inspect the project.</span></span> <span data-ttu-id="3973a-147">你应该会看到一个名为 `Program.qs` 的源文件，该文件是一个 Q# 程序，用于定义将消息输出到控制台的简单操作。</span><span class="sxs-lookup"><span data-stu-id="3973a-147">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="3973a-148">运行应用程序：</span><span class="sxs-lookup"><span data-stu-id="3973a-148">To run the application:</span></span>
1. <span data-ttu-id="3973a-149">选择“调试” -> “在不调试的情况下启动”。</span><span class="sxs-lookup"><span data-stu-id="3973a-149">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="3973a-150">应该会看到打印到控制台窗口的文本 `Hello quantum world!`。</span><span class="sxs-lookup"><span data-stu-id="3973a-150">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="3973a-151">如果一个 Visual Studio 解决方案中具有多个项目，解决方案中包含的所有项目都需要位于解决方案所在的同一文件夹中，或位于其中一个子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="3973a-151">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-prompt"></a>[<span data-ttu-id="3973a-152">其他使用命令提示符的编辑器</span><span class="sxs-lookup"><span data-stu-id="3973a-152">Other editors with the command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="3973a-153">创建 Q# `Hello World` 应用程序来验证安装项。</span><span class="sxs-lookup"><span data-stu-id="3973a-153">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="3973a-154">安装项目模板。</span><span class="sxs-lookup"><span data-stu-id="3973a-154">Install the project templates.</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. <span data-ttu-id="3973a-155">创建新的应用程序：</span><span class="sxs-lookup"><span data-stu-id="3973a-155">Create a new application:</span></span>
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. <span data-ttu-id="3973a-156">导航到应用程序目录：</span><span class="sxs-lookup"><span data-stu-id="3973a-156">Navigate to the application directory:</span></span>
    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="3973a-157">该目录现在应该会包含一个 `Program.qs` 文件，它是 Q# 程序，用于定义将消息输出到控制台的简单操作。</span><span class="sxs-lookup"><span data-stu-id="3973a-157">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="3973a-158">你可使用文本编辑器来修改此模板，并用你自己的量子应用程序来覆盖它。</span><span class="sxs-lookup"><span data-stu-id="3973a-158">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="3973a-159">运行该程序：</span><span class="sxs-lookup"><span data-stu-id="3973a-159">Run the program:</span></span>
    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="3973a-160">应会看到以下输出文本：`Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="3973a-160">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="3973a-161">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3973a-161">Next steps</span></span>

<span data-ttu-id="3973a-162">在首选环境中安装量子开发工具包后，可以编写并运行[第一个量子程序](xref:microsoft.quantum.quickstarts.qrng)。</span><span class="sxs-lookup"><span data-stu-id="3973a-162">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
