---
title: '用 Q # 命令行应用程序进行开发'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 4311ebf9f72254485a20ba721ea2ce19163f4371
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630262"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="7ecb3-102">用 Q # 命令行应用程序进行开发</span><span class="sxs-lookup"><span data-stu-id="7ecb3-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="7ecb3-103">Q # 程序可以自行执行，而不能在 c #、F # 或 Python 等主机语言中使用驱动程序。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7ecb3-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="7ecb3-104">Prerequisites</span></span>

- [<span data-ttu-id="7ecb3-105">.NET Core SDK 3.1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="7ecb3-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="7ecb3-106">安装</span><span class="sxs-lookup"><span data-stu-id="7ecb3-106">Installation</span></span>

<span data-ttu-id="7ecb3-107">尽管可以在任何 IDE 中生成 Q # 命令行应用程序，但我们还是建议为 Q # 应用程序使用 Visual Studio Code （VS Code）或 Visual Studio IDE。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="7ecb3-108">使用这些工具进行开发可提供对丰富功能的访问权限。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-108">Developing in these tools provides access to rich functionality.</span></span>

<span data-ttu-id="7ecb3-109">配置 VS Code：</span><span class="sxs-lookup"><span data-stu-id="7ecb3-109">To configure VS Code:</span></span>

1. <span data-ttu-id="7ecb3-110">下载并安装[VS Code](https://code.visualstudio.com/download) （Windows、Linux 和 Mac）。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="7ecb3-111">安装[MICROSOFT QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="7ecb3-112">若要配置 Visual Studio：</span><span class="sxs-lookup"><span data-stu-id="7ecb3-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="7ecb3-113">下载并安装[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 或更高版本，并启用 .net Core 跨平台开发工作负荷。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="7ecb3-114">下载并安装[MICROSOFT QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="7ecb3-115">使用 VS Code 与 Q # 进行开发</span><span class="sxs-lookup"><span data-stu-id="7ecb3-115">Develop with Q# using VS Code</span></span>

<span data-ttu-id="7ecb3-116">安装 Q # 项目模板：</span><span class="sxs-lookup"><span data-stu-id="7ecb3-116">Install the Q# project templates:</span></span>

1. <span data-ttu-id="7ecb3-117">打开 VS Code。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-117">Open VS Code.</span></span>
2. <span data-ttu-id="7ecb3-118">单击 "**查看**" "  ->  **命令面板**"。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-118">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="7ecb3-119">选择 " **Q #：安装项目模板**"。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-119">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="7ecb3-120">如果已**成功安装项目模板**，则可以将 QDK 用于自己的应用程序和库。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-120">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="7ecb3-121">创建新项目：</span><span class="sxs-lookup"><span data-stu-id="7ecb3-121">To create a new project:</span></span>

1. <span data-ttu-id="7ecb3-122">单击 "**查看**" "  ->  **命令面板**"，然后选择 " **Q #：创建新项目**"。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-122">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="7ecb3-123">单击 "**独立控制台应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-123">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="7ecb3-124">导航到要保存项目的位置，然后单击 "**创建项目**"。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-124">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="7ecb3-125">成功创建项目后，单击右下方的 "**打开新项目 ...** "。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-125">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="7ecb3-126">检查项目。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-126">Inspect the project.</span></span> <span data-ttu-id="7ecb3-127">应该会看到一个名为的源文件，该文件 `Program.qs` 是一个 Q # 程序，用于定义将消息打印到控制台的简单操作。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-127">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="7ecb3-128">运行应用程序：</span><span class="sxs-lookup"><span data-stu-id="7ecb3-128">To run the application:</span></span>
1. <span data-ttu-id="7ecb3-129">单击 "**终端**  ->  **新终端**"。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-129">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="7ecb3-130">在终端提示符下，输入 `dotnet run` 。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-130">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="7ecb3-131">应在输出窗口 `Hello quantum world!` 中看到以下文本</span><span class="sxs-lookup"><span data-stu-id="7ecb3-131">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="7ecb3-132">VS Code Q # 扩展当前不支持具有多个根文件夹的工作区。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-132">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="7ecb3-133">如果一个 VS Code 工作区中具有多个项目，则所有项目都必须包含在同一个根文件夹中。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-133">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="7ecb3-134">使用 Visual Studio 通过 Q # 进行开发</span><span class="sxs-lookup"><span data-stu-id="7ecb3-134">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="7ecb3-135">通过创建 Q # 应用程序来验证你的 Visual Studio 安装 `Hello World` 。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-135">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="7ecb3-136">若要创建新的 Q # 应用程序：</span><span class="sxs-lookup"><span data-stu-id="7ecb3-136">To create a new Q# application:</span></span>
1. <span data-ttu-id="7ecb3-137">打开 Visual Studio，然后单击 "**文件**" "  ->  **新建**  ->  **项目**"。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-137">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="7ecb3-138">`Q#`在搜索框中键入，选择 " **Q # 应用程序**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-138">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="7ecb3-139">输入应用程序的名称和位置，然后单击 "**创建**"。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-139">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="7ecb3-140">检查项目。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-140">Inspect the project.</span></span> <span data-ttu-id="7ecb3-141">应该会看到一个名为的源文件，该文件 `Program.qs` 是一个 Q # 程序，用于定义将消息打印到控制台的简单操作。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-141">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="7ecb3-142">运行应用程序：</span><span class="sxs-lookup"><span data-stu-id="7ecb3-142">To run the application:</span></span>
1. <span data-ttu-id="7ecb3-143">选择 "**调试**开始" （  ->  **不调试**）。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-143">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="7ecb3-144">应该会看到打印到控制台窗口的文本 `Hello quantum world!`。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-144">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="7ecb3-145">如果一个 Visual Studio 解决方案中有多个项目，则解决方案中包含的所有项目都需要位于解决方案所在的同一文件夹中，或位于其某个子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-145">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  


## <a name="next-steps"></a><span data-ttu-id="7ecb3-146">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7ecb3-146">Next steps</span></span>

<span data-ttu-id="7ecb3-147">在首选环境中安装量子开发工具包后，可以编写并运行[第一个量子程序](xref:microsoft.quantum.quickstarts.qrng)。</span><span class="sxs-lookup"><span data-stu-id="7ecb3-147">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
