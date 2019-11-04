---
title: 了解如何更新 Microsoft Quantum Development Kit （QDK）
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: fc430a77f88878437e662c5b54507f70f3c6e020
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185845"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="89de5-102">更新 Microsoft Quantum Development Kit （QDK）</span><span class="sxs-lookup"><span data-stu-id="89de5-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="89de5-103">了解如何将 Microsoft Quantum Development Kit （QDK）更新到最新版本。</span><span class="sxs-lookup"><span data-stu-id="89de5-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="89de5-104">本文假设已安装 QDK。</span><span class="sxs-lookup"><span data-stu-id="89de5-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="89de5-105">如果你是首次安装，请参阅[安装指南](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="89de5-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="89de5-106">更新步骤取决于你的开发环境。</span><span class="sxs-lookup"><span data-stu-id="89de5-106">The update steps depend on your development environment.</span></span> <span data-ttu-id="89de5-107">从以下部分中选择环境。</span><span class="sxs-lookup"><span data-stu-id="89de5-107">Choose your environment from the following sections.</span></span>

## <a name="python"></a><span data-ttu-id="89de5-108">Python</span><span class="sxs-lookup"><span data-stu-id="89de5-108">Python</span></span>

1. <span data-ttu-id="89de5-109">更新 `iqsharp` 内核</span><span class="sxs-lookup"><span data-stu-id="89de5-109">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="89de5-110">验证 `iqsharp` 版本</span><span class="sxs-lookup"><span data-stu-id="89de5-110">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="89de5-111">应该会看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="89de5-111">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. <span data-ttu-id="89de5-112">更新 `qsharp` 包</span><span class="sxs-lookup"><span data-stu-id="89de5-112">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="89de5-113">验证 `qsharp` 版本</span><span class="sxs-lookup"><span data-stu-id="89de5-113">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="89de5-114">应该会看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="89de5-114">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.9.1909.3002
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. <span data-ttu-id="89de5-115">你现在可以使用更新的 QDK 版本来运行现有的量程程序。</span><span class="sxs-lookup"><span data-stu-id="89de5-115">You can now use the updated QDK version to run your existing quantum programs.</span></span>

## <a name="jupyter-notebooks"></a><span data-ttu-id="89de5-116">Jupyter 笔记本</span><span class="sxs-lookup"><span data-stu-id="89de5-116">Jupyter notebooks</span></span>

1. <span data-ttu-id="89de5-117">更新 `iqsharp` 内核</span><span class="sxs-lookup"><span data-stu-id="89de5-117">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="89de5-118">验证 `iqsharp` 版本</span><span class="sxs-lookup"><span data-stu-id="89de5-118">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="89de5-119">应该会看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="89de5-119">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. <span data-ttu-id="89de5-120">你现在可以打开现有的 Jupyter 笔记本，并使用更新的 QDK 运行它。</span><span class="sxs-lookup"><span data-stu-id="89de5-120">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

## <a name="c-on-windows-using-visual-studio"></a><span data-ttu-id="89de5-121">C#在 Windows 上，使用 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="89de5-121">C# on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="89de5-122">更新 Q # Visual Studio 扩展</span><span class="sxs-lookup"><span data-stu-id="89de5-122">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="89de5-123">Visual Studio 会提示你接受对[量程 Visual Studio 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)的更新</span><span class="sxs-lookup"><span data-stu-id="89de5-123">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="89de5-124">接受更新</span><span class="sxs-lookup"><span data-stu-id="89de5-124">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="89de5-125">项目模板将更新为扩展。</span><span class="sxs-lookup"><span data-stu-id="89de5-125">The project templates are updated with the extension.</span></span> <span data-ttu-id="89de5-126">更新的模板仅适用于新创建的项目。</span><span class="sxs-lookup"><span data-stu-id="89de5-126">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="89de5-127">更新扩展时，不会更新现有项目的代码。</span><span class="sxs-lookup"><span data-stu-id="89de5-127">The code for your existing projects is not updated when the extension is updated.</span></span>

1. <span data-ttu-id="89de5-128">更新 QDK 包</span><span class="sxs-lookup"><span data-stu-id="89de5-128">Update the QDK packages</span></span>

    - <span data-ttu-id="89de5-129">打开现有应用程序</span><span class="sxs-lookup"><span data-stu-id="89de5-129">Open an existing application</span></span>
    - <span data-ttu-id="89de5-130">在解决方案资源管理器中选择**依赖关系**</span><span class="sxs-lookup"><span data-stu-id="89de5-130">Select **Dependencies** in the Solution Explorer</span></span>
    - <span data-ttu-id="89de5-131">选择 "**管理 NuGet 包**"</span><span class="sxs-lookup"><span data-stu-id="89de5-131">Select **Manage NuGet Packages**</span></span>
    - <span data-ttu-id="89de5-132">将**Microsoft 量子**包更新到最新版本</span><span class="sxs-lookup"><span data-stu-id="89de5-132">Update the **Microsoft.Quantum** packages to the latest version</span></span>

1. <span data-ttu-id="89de5-133">你现在可以用最新的 QDK 运行你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="89de5-133">You can now run your application with the latest QDK.</span></span>

## <a name="c-using-vs-code"></a><span data-ttu-id="89de5-134">C#，使用 VS Code</span><span class="sxs-lookup"><span data-stu-id="89de5-134">C#, using VS Code</span></span>

1. <span data-ttu-id="89de5-135">更新量程 VS Code 扩展</span><span class="sxs-lookup"><span data-stu-id="89de5-135">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="89de5-136">重新启动 VS Code</span><span class="sxs-lookup"><span data-stu-id="89de5-136">Restart VS Code</span></span>
    - <span data-ttu-id="89de5-137">导航到 "**扩展**" 选项卡</span><span class="sxs-lookup"><span data-stu-id="89de5-137">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="89de5-138">选择 Visual Studio Code 扩展的**Microsoft Quantum Development Kit**</span><span class="sxs-lookup"><span data-stu-id="89de5-138">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="89de5-139">重新加载扩展</span><span class="sxs-lookup"><span data-stu-id="89de5-139">Reload the extension</span></span>

1. <span data-ttu-id="89de5-140">更新量程项目模板：</span><span class="sxs-lookup"><span data-stu-id="89de5-140">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="89de5-141">中转到**查看** -> **命令面板**</span><span class="sxs-lookup"><span data-stu-id="89de5-141">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="89de5-142">选择**Q #：安装项目模板**</span><span class="sxs-lookup"><span data-stu-id="89de5-142">Select **Q#: Install project templates**</span></span>

1. <span data-ttu-id="89de5-143">在 VS Code 中打开现有应用程序</span><span class="sxs-lookup"><span data-stu-id="89de5-143">Open an existing application in VS Code</span></span>

   - <span data-ttu-id="89de5-144">编辑 .csproj 文件以添加新的包版本</span><span class="sxs-lookup"><span data-stu-id="89de5-144">Edit the .csproj file to add the new package versions</span></span>

    ```xml
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.9.1909.3002" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.9.1909.3002" />
    </ItemGroup>
    ```

    <span data-ttu-id="89de5-145">如果使用其他 `Microsoft.Quantum` 包，也可以更新这些包。</span><span class="sxs-lookup"><span data-stu-id="89de5-145">If you use other `Microsoft.Quantum` packages, update these too.</span></span>

1. <span data-ttu-id="89de5-146">你现在可以运行包含更新的 QDK 的应用程序</span><span class="sxs-lookup"><span data-stu-id="89de5-146">You can now run your application with the updated QDK</span></span>

## <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="89de5-147">C#，使用 `dotnet` 命令行工具</span><span class="sxs-lookup"><span data-stu-id="89de5-147">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="89de5-148">更新 .NET 的量程项目模板</span><span class="sxs-lookup"><span data-stu-id="89de5-148">Update the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. <span data-ttu-id="89de5-149">更新并运行现有应用程序</span><span class="sxs-lookup"><span data-stu-id="89de5-149">Update and run an existing application</span></span>

    - <span data-ttu-id="89de5-150">更新应用程序中的 QDK 包版本</span><span class="sxs-lookup"><span data-stu-id="89de5-150">Update the QDK package versions in your application</span></span>

        ```bash
        dotnet add package Microsoft.Quantum.Development.Kit
        dotnet add package Microsoft.Quantum.Standard
        ```

        <span data-ttu-id="89de5-151">如果你的应用程序使用任何其他 `Microsoft.Quantum` 包，也更新这些包。</span><span class="sxs-lookup"><span data-stu-id="89de5-151">If your application uses any other `Microsoft.Quantum` packages, update these too.</span></span>

    - <span data-ttu-id="89de5-152">运行应用程序</span><span class="sxs-lookup"><span data-stu-id="89de5-152">Run the application</span></span>

        ```bash
        dotnet run
        ```

    - <span data-ttu-id="89de5-153">应用程序将在新的包版本中运行</span><span class="sxs-lookup"><span data-stu-id="89de5-153">Your application will run with the new package versions</span></span>

## <a name="whats-next"></a><span data-ttu-id="89de5-154">还有什么？</span><span class="sxs-lookup"><span data-stu-id="89de5-154">What's next?</span></span>

<span data-ttu-id="89de5-155">现在，你已在首选环境中更新了量程开发工具包，接下来可以继续开发并运行量程程序。</span><span class="sxs-lookup"><span data-stu-id="89de5-155">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="89de5-156">如果还没有编写程序，可以开始使用[第一个量程计划](xref:microsoft.quantum.write-program)。</span><span class="sxs-lookup"><span data-stu-id="89de5-156">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
