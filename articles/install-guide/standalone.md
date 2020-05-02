---
title: '执行无驱动程序和主机语言的 Q # 程序'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e83acaf10af952da06abf4737ad2ec91f1cf1b8e
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "82706795"
---
# <a name="q-command-line-applications"></a><span data-ttu-id="fbfe2-102">Q # 命令行应用程序</span><span class="sxs-lookup"><span data-stu-id="fbfe2-102">Q# Command Line Applications</span></span>

<span data-ttu-id="fbfe2-103">Q # 程序可以自行执行，而不能在 c #、F # 或 Python 等主机语言中使用驱动程序。</span><span class="sxs-lookup"><span data-stu-id="fbfe2-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="fbfe2-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="fbfe2-104">Pre-requisites</span></span>

- [<span data-ttu-id="fbfe2-105">.NET Core SDK 3.1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="fbfe2-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="fbfe2-106">安装</span><span class="sxs-lookup"><span data-stu-id="fbfe2-106">Installation</span></span>

<span data-ttu-id="fbfe2-107">尽管可以在任何 IDE 中生成 Q # 命令行应用程序，但我们强烈建议对 Q # 应用程序使用 Visual Studio Code （VS Code）或 Visual Studio IDE。</span><span class="sxs-lookup"><span data-stu-id="fbfe2-107">While you can build Q# command line applications in any IDE, we highly recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="fbfe2-108">通过使用 VS Code 或 Visual Studio 和 QDK Visual Studio Code 扩展，你可以访问更丰富的功能。</span><span class="sxs-lookup"><span data-stu-id="fbfe2-108">By using VS Code or Visual Studio and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

- <span data-ttu-id="fbfe2-109">安装[VS Code](https://code.visualstudio.com/download) （Windows、Linux 和 Mac）</span><span class="sxs-lookup"><span data-stu-id="fbfe2-109">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
- <span data-ttu-id="fbfe2-110">[为 VS Code 或安装 QDK 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span><span class="sxs-lookup"><span data-stu-id="fbfe2-110">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) OR</span></span>
- <span data-ttu-id="fbfe2-111">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3，启用了 .NET Core 跨平台开发工作负载。</span><span class="sxs-lookup"><span data-stu-id="fbfe2-111">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>
- <span data-ttu-id="fbfe2-112">下载并安装[Visual Studio 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="fbfe2-112">Download and install the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="fbfe2-113">使用 VS Code 与 Q # 进行开发</span><span class="sxs-lookup"><span data-stu-id="fbfe2-113">Develop with Q# using VS Code</span></span>

<span data-ttu-id="fbfe2-114">安装量子项目模板：</span><span class="sxs-lookup"><span data-stu-id="fbfe2-114">Install the Quantum project templates:</span></span>

- <span data-ttu-id="fbfe2-115">中转到 "**视图** -> "**命令面板**</span><span class="sxs-lookup"><span data-stu-id="fbfe2-115">Go to **View** -> **Command Palette**</span></span>
- <span data-ttu-id="fbfe2-116">选择**Q #：安装项目模板**</span><span class="sxs-lookup"><span data-stu-id="fbfe2-116">Select **Q#: Install project templates**</span></span>

<span data-ttu-id="fbfe2-117">现已安装量子开发工具包，并且可以在自己的应用程序和库中使用。</span><span class="sxs-lookup"><span data-stu-id="fbfe2-117">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>
- <span data-ttu-id="fbfe2-118">创建新项目：</span><span class="sxs-lookup"><span data-stu-id="fbfe2-118">Create a new project:</span></span>
  - <span data-ttu-id="fbfe2-119">中转到 "**视图** -> "**命令面板**</span><span class="sxs-lookup"><span data-stu-id="fbfe2-119">Go to **View** -> **Command Palette**</span></span>
  - <span data-ttu-id="fbfe2-120">选择**Q #：创建新项目**</span><span class="sxs-lookup"><span data-stu-id="fbfe2-120">Select **Q#: Create New Project**</span></span>
  - <span data-ttu-id="fbfe2-121">选择**独立控制台应用程序**</span><span class="sxs-lookup"><span data-stu-id="fbfe2-121">Select **Standalone console application**</span></span>
  - <span data-ttu-id="fbfe2-122">导航到要在其中创建应用程序的文件系统上的位置</span><span class="sxs-lookup"><span data-stu-id="fbfe2-122">Navigate to the location on the file system where you would like to create the application</span></span>
  - <span data-ttu-id="fbfe2-123">创建项目后，单击“打开新项目...”\*\*\*\* 按钮</span><span class="sxs-lookup"><span data-stu-id="fbfe2-123">Click on the **Open new project...** button, once the project has been created</span></span>
        
- <span data-ttu-id="fbfe2-124">检查项目</span><span class="sxs-lookup"><span data-stu-id="fbfe2-124">Inspect the project</span></span>
  - <span data-ttu-id="fbfe2-125">应会看到名`Program.qs`为 "创建" 的文件，该文件是一个 Q # 程序，用于定义将消息打印到控制台的简单操作。</span><span class="sxs-lookup"><span data-stu-id="fbfe2-125">You should see that a file called `Program.qs` created, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

- <span data-ttu-id="fbfe2-126">运行应用程序：</span><span class="sxs-lookup"><span data-stu-id="fbfe2-126">Run the application:</span></span>
  - <span data-ttu-id="fbfe2-127">中转到**终端** -> **新终端**</span><span class="sxs-lookup"><span data-stu-id="fbfe2-127">Go to **Terminal** -> **New Terminal**</span></span>
  - <span data-ttu-id="fbfe2-128">输入 `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="fbfe2-128">Enter `dotnet run`</span></span>
  - <span data-ttu-id="fbfe2-129">应在输出窗口 `Hello quantum world!` 中看到以下文本</span><span class="sxs-lookup"><span data-stu-id="fbfe2-129">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> * <span data-ttu-id="fbfe2-130">Visual Studio Code 扩展当前不支持具有多个根文件夹的工作区。</span><span class="sxs-lookup"><span data-stu-id="fbfe2-130">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="fbfe2-131">如果一个 VS Code 工作区中具有多个项目，则所有项目都必须包含在同一个根文件夹中。</span><span class="sxs-lookup"><span data-stu-id="fbfe2-131">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="fbfe2-132">使用 Visual Studio 通过 Q # 进行开发</span><span class="sxs-lookup"><span data-stu-id="fbfe2-132">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="fbfe2-133">通过创建 `Hello World` 应用程序来验证安装</span><span class="sxs-lookup"><span data-stu-id="fbfe2-133">Verify the installation by creating a `Hello World` application</span></span>

- <span data-ttu-id="fbfe2-134">创建新的 Q# 应用程序</span><span class="sxs-lookup"><span data-stu-id="fbfe2-134">Create a new Q# application</span></span>
  - <span data-ttu-id="fbfe2-135">中转到 "**文件** -> " "**新建** -> **项目**"</span><span class="sxs-lookup"><span data-stu-id="fbfe2-135">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="fbfe2-136">在搜索框中键入 `Q#`</span><span class="sxs-lookup"><span data-stu-id="fbfe2-136">Type `Q#` in the search box</span></span>
  - <span data-ttu-id="fbfe2-137">选择“Q# 应用程序”\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="fbfe2-137">Select **Q# Application**</span></span>
  - <span data-ttu-id="fbfe2-138">选择 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="fbfe2-138">Select **Next**</span></span>
  - <span data-ttu-id="fbfe2-139">为应用程序选择名称和位置</span><span class="sxs-lookup"><span data-stu-id="fbfe2-139">Choose a name and location for your application</span></span>
  - <span data-ttu-id="fbfe2-140">选择**创建**</span><span class="sxs-lookup"><span data-stu-id="fbfe2-140">Select **Create**</span></span>

- <span data-ttu-id="fbfe2-141">检查项目</span><span class="sxs-lookup"><span data-stu-id="fbfe2-141">Inspect the project</span></span>
  - <span data-ttu-id="fbfe2-142">应会看到已创建一个名`Program.qs`为的文件，这是一个 Q # 程序，用于定义将消息打印到控制台的简单操作。</span><span class="sxs-lookup"><span data-stu-id="fbfe2-142">You should see that a file called `Program.qs` has been created, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

- <span data-ttu-id="fbfe2-143">运行应用程序</span><span class="sxs-lookup"><span data-stu-id="fbfe2-143">Run the application</span></span>
  - <span data-ttu-id="fbfe2-144">选择 "**调试** -> **开始" （不调试**）</span><span class="sxs-lookup"><span data-stu-id="fbfe2-144">Select **Debug** -> **Start Without Debugging**</span></span>
  - <span data-ttu-id="fbfe2-145">应该会看到打印到控制台窗口的文本 `Hello quantum world!`。</span><span class="sxs-lookup"><span data-stu-id="fbfe2-145">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="fbfe2-146">如果一个 Visual Studio 解决方案中具有多个项目，解决方案中包含的所有项目都需要位于解决方案所在的同一文件夹中，或位于其中一个子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="fbfe2-146">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  


## <a name="whats-next"></a><span data-ttu-id="fbfe2-147">后续步骤</span><span class="sxs-lookup"><span data-stu-id="fbfe2-147">What's next?</span></span>

<span data-ttu-id="fbfe2-148">在首选环境中安装量子开发工具包后，可以编写并运行[第一个量子程序](xref:microsoft.quantum.write-program)。</span><span class="sxs-lookup"><span data-stu-id="fbfe2-148">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
