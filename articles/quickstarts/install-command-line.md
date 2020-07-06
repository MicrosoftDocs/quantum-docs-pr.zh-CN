---
title: 开发 Q# 命令行应用程序
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 15015d1673f47faf5a13dde516f834916b4319d6
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884288"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="69122-102">开发 Q# 命令行应用程序</span><span class="sxs-lookup"><span data-stu-id="69122-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="69122-103">Q# 程序可以自己执行，而无需采用 C#、F# 或 Python 等主机语言的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="69122-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="69122-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="69122-104">Prerequisites</span></span>

- [<span data-ttu-id="69122-105">.NET Core SDK 3.1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="69122-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="69122-106">安装</span><span class="sxs-lookup"><span data-stu-id="69122-106">Installation</span></span>

<span data-ttu-id="69122-107">尽管可以在任何 IDE 中生成 Q# 命令行应用程序，但我们还是建议为 Q# 应用程序使用 Visual Studio Code (VS Code) 或 Visual Studio IDE。</span><span class="sxs-lookup"><span data-stu-id="69122-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="69122-108">在这些环境中开发涉及到丰富的 QDK 扩展功能，其中包括警告、语法突出显示和项目模板等。</span><span class="sxs-lookup"><span data-stu-id="69122-108">Developing in these environments includes the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span>

<span data-ttu-id="69122-109">配置 VS Code：</span><span class="sxs-lookup"><span data-stu-id="69122-109">To configure VS Code:</span></span>

1. <span data-ttu-id="69122-110">下载并安装 [VS Code](https://code.visualstudio.com/download)（Windows、Linux 和 Mac）。</span><span class="sxs-lookup"><span data-stu-id="69122-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="69122-111">安装[适用于 VS Code 的 Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)。</span><span class="sxs-lookup"><span data-stu-id="69122-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="69122-112">配置 Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="69122-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="69122-113">下载并安装 [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 或更高版本，并启用 .NET Core 跨平台开发工作负载。</span><span class="sxs-lookup"><span data-stu-id="69122-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="69122-114">下载并安装 [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)。</span><span class="sxs-lookup"><span data-stu-id="69122-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

<span data-ttu-id="69122-115">若要为另一环境安装 QDK，请输入命令行：</span><span class="sxs-lookup"><span data-stu-id="69122-115">To install the QDK for another environment, enter in the command line:</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-q"></a><span data-ttu-id="69122-116">使用 Q# 进行开发</span><span class="sxs-lookup"><span data-stu-id="69122-116">Develop with Q#</span></span>

<span data-ttu-id="69122-117">按照你的环境所对应的选项卡上的说明操作。</span><span class="sxs-lookup"><span data-stu-id="69122-117">Follow the instructions at the tab corresponding to your environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="69122-118">VS Code</span><span class="sxs-lookup"><span data-stu-id="69122-118">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="69122-119">安装 Q# 项目模板：</span><span class="sxs-lookup"><span data-stu-id="69122-119">Install the Q# project templates:</span></span>

1. <span data-ttu-id="69122-120">打开 VS Code。</span><span class="sxs-lookup"><span data-stu-id="69122-120">Open VS Code.</span></span>
2. <span data-ttu-id="69122-121">单击“查看” -> “命令面板” 。</span><span class="sxs-lookup"><span data-stu-id="69122-121">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="69122-122">选择安装项目模板。</span><span class="sxs-lookup"><span data-stu-id="69122-122">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="69122-123">如果显示“已成功安装项目模板”，可以为自己的应用程序和库使用 QDK。</span><span class="sxs-lookup"><span data-stu-id="69122-123">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="69122-124">创建新项目：</span><span class="sxs-lookup"><span data-stu-id="69122-124">To create a new project:</span></span>

1. <span data-ttu-id="69122-125">单击“查看” -> “命令面板”，然后选择 Q#  **：** Create New Project”。</span><span class="sxs-lookup"><span data-stu-id="69122-125">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="69122-126">单击“独立控制台应用程序”。</span><span class="sxs-lookup"><span data-stu-id="69122-126">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="69122-127">导航到项目的保存位置，然后单击“创建项目”。</span><span class="sxs-lookup"><span data-stu-id="69122-127">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="69122-128">成功创建项目后，单击右下方的“打开新项目…”。</span><span class="sxs-lookup"><span data-stu-id="69122-128">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="69122-129">检查项目。</span><span class="sxs-lookup"><span data-stu-id="69122-129">Inspect the project.</span></span> <span data-ttu-id="69122-130">你应该会看到一个名为 `Program.qs` 的源文件，该文件是一个 Q# 程序，用于定义将消息输出到控制台的简单操作。</span><span class="sxs-lookup"><span data-stu-id="69122-130">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="69122-131">运行应用程序：</span><span class="sxs-lookup"><span data-stu-id="69122-131">To run the application:</span></span>
1. <span data-ttu-id="69122-132">单击“终端” -> “新终端” 。</span><span class="sxs-lookup"><span data-stu-id="69122-132">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="69122-133">在终端提示符下，输入 `dotnet run`。</span><span class="sxs-lookup"><span data-stu-id="69122-133">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="69122-134">应在输出窗口 `Hello quantum world!` 中看到以下文本</span><span class="sxs-lookup"><span data-stu-id="69122-134">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="69122-135">VS Code Q# 扩展当前不支持具有多个根文件夹的工作区。</span><span class="sxs-lookup"><span data-stu-id="69122-135">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="69122-136">如果一个 VS Code 工作区中具有多个项目，则所有项目都必须包含在同一个根文件夹中。</span><span class="sxs-lookup"><span data-stu-id="69122-136">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="69122-137">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="69122-137">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="69122-138">创建 Q# `Hello World` 应用程序，验证 Visual Studio 安装。</span><span class="sxs-lookup"><span data-stu-id="69122-138">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="69122-139">创建新的 Q# 应用程序：</span><span class="sxs-lookup"><span data-stu-id="69122-139">To create a new Q# application:</span></span>
1. <span data-ttu-id="69122-140">打开 Visual Studio，单击“文件” -> “新建” -> “项目”  。</span><span class="sxs-lookup"><span data-stu-id="69122-140">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="69122-141">在“搜索”框中键入 `Q#`，选择“Q# 应用程序”，然后单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="69122-141">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="69122-142">输入应用程序的“名称”和“位置”，然后单击“创建”。</span><span class="sxs-lookup"><span data-stu-id="69122-142">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="69122-143">检查项目。</span><span class="sxs-lookup"><span data-stu-id="69122-143">Inspect the project.</span></span> <span data-ttu-id="69122-144">你应该会看到一个名为 `Program.qs` 的源文件，该文件是一个 Q# 程序，用于定义将消息输出到控制台的简单操作。</span><span class="sxs-lookup"><span data-stu-id="69122-144">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="69122-145">运行应用程序：</span><span class="sxs-lookup"><span data-stu-id="69122-145">To run the application:</span></span>
1. <span data-ttu-id="69122-146">选择“调试” -> “在不调试的情况下启动”。</span><span class="sxs-lookup"><span data-stu-id="69122-146">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="69122-147">应该会看到打印到控制台窗口的文本 `Hello quantum world!`。</span><span class="sxs-lookup"><span data-stu-id="69122-147">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="69122-148">如果一个 Visual Studio 解决方案中具有多个项目，解决方案中包含的所有项目都需要位于解决方案所在的同一文件夹中，或位于其中一个子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="69122-148">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-line"></a>[<span data-ttu-id="69122-149">其他使用命令行的编辑器</span><span class="sxs-lookup"><span data-stu-id="69122-149">Other editors with the command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="69122-150">通过创建 Q# `Hello World` 应用程序来验证安装。</span><span class="sxs-lookup"><span data-stu-id="69122-150">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="69122-151">创建新的应用程序：</span><span class="sxs-lookup"><span data-stu-id="69122-151">Create a new application:</span></span>
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

2. <span data-ttu-id="69122-152">导航到应用程序目录：</span><span class="sxs-lookup"><span data-stu-id="69122-152">Navigate to the application directory:</span></span>
    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="69122-153">该目录现在应该会包含一个 `Program.qs` 文件，它是 Q# 程序，用于定义将消息输出到控制台的简单操作。</span><span class="sxs-lookup"><span data-stu-id="69122-153">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="69122-154">你可使用文本编辑器来修改此模板，并用你自己的量子应用程序来覆盖它。</span><span class="sxs-lookup"><span data-stu-id="69122-154">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

3. <span data-ttu-id="69122-155">运行该程序：</span><span class="sxs-lookup"><span data-stu-id="69122-155">Run the program:</span></span>
    ```dotnetcli
    dotnet run
    ```

4. <span data-ttu-id="69122-156">应会看到以下输出文本：`Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="69122-156">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="69122-157">后续步骤</span><span class="sxs-lookup"><span data-stu-id="69122-157">Next steps</span></span>

<span data-ttu-id="69122-158">在首选环境中安装量子开发工具包后，可以编写并运行[第一个量子程序](xref:microsoft.quantum.quickstarts.qrng)。</span><span class="sxs-lookup"><span data-stu-id="69122-158">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
