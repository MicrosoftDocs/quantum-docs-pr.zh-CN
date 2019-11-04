---
title: 了解如何更新 Microsoft Quantum Development Kit （QDK）
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: ebf1f15d65a12c921cd3f04e4111d463d1060f8e
ms.sourcegitcommit: c93fea5980d1d46fbda1e7c7153831b9337134bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2019
ms.locfileid: "73463280"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="33eda-102">更新 Microsoft Quantum Development Kit （QDK）</span><span class="sxs-lookup"><span data-stu-id="33eda-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="33eda-103">了解如何将 Microsoft Quantum Development Kit （QDK）更新到最新版本。</span><span class="sxs-lookup"><span data-stu-id="33eda-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="33eda-104">本文假设已安装 QDK。</span><span class="sxs-lookup"><span data-stu-id="33eda-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="33eda-105">如果你是首次安装，请参阅[安装指南](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="33eda-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>


## <a name="updating-q-projects"></a><span data-ttu-id="33eda-106">更新 Q # 项目</span><span class="sxs-lookup"><span data-stu-id="33eda-106">Updating Q# Projects</span></span> 

1. <span data-ttu-id="33eda-107">首先，安装最新版本的[.NET Core SDK 3.0](https://dotnet.microsoft.com/download) ，并在命令提示符下运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="33eda-107">First, install the latest version of the [.NET Core SDK 3.0](https://dotnet.microsoft.com/download) and run the following command in the command prompt:</span></span>
```bash
dotnet --version
```
 <span data-ttu-id="33eda-108">验证输出是否为3.0.100 或更高版本，按照以下说明操作，具体取决于您的设置。</span><span class="sxs-lookup"><span data-stu-id="33eda-108">Verify the output is 3.0.100 or higher, then follow the instructions below depending on your setup.</span></span>

### <a name="in-visual-studio"></a><span data-ttu-id="33eda-109">在 Visual Studio 中</span><span class="sxs-lookup"><span data-stu-id="33eda-109">In Visual Studio</span></span>
 
 1. <span data-ttu-id="33eda-110">更新到最新版本的 Visual Studio 2019，请参阅[此处](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019)了解相关说明</span><span class="sxs-lookup"><span data-stu-id="33eda-110">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
 2. <span data-ttu-id="33eda-111">在 Visual Studio 中打开解决方案</span><span class="sxs-lookup"><span data-stu-id="33eda-111">Open your solution in Visual Studio</span></span>
 3. <span data-ttu-id="33eda-112">从菜单中选择 "生成 > 清理解决方案"</span><span class="sxs-lookup"><span data-stu-id="33eda-112">From the menu, select Build > Clean Solution</span></span> 
 4. <span data-ttu-id="33eda-113">将每个 .csproj 文件中[的目标框架更新](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework)为 netcoreapp 3.0 （如果它是库项目，则更新 netstandard 2.1）</span><span class="sxs-lookup"><span data-stu-id="33eda-113">[Update the target framework](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework) in each of your .csproj files to netcoreapp3.0 (or netstandard2.1 if it is a library project)</span></span>
 5. <span data-ttu-id="33eda-114">保存并关闭解决方案中的所有文件</span><span class="sxs-lookup"><span data-stu-id="33eda-114">Save and close all files in your solution</span></span>
 6. <span data-ttu-id="33eda-115">> 命令行 > 选择工具开发人员命令提示</span><span class="sxs-lookup"><span data-stu-id="33eda-115">Select Tools > Command Line > Developer Command Prompt</span></span>
 7. <span data-ttu-id="33eda-116">对于解决方案中的每个项目，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="33eda-116">For each project in the solution, run the following command:</span></span>
 ```bash
 dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
 ```
<span data-ttu-id="33eda-117">如果你的项目使用任何其他的 Microsoft 量子包，也请对其运行该命令。</span><span class="sxs-lookup"><span data-stu-id="33eda-117">If your projects use any other Microsoft.Quantum packages, run the command for these too.</span></span> 
 8. <span data-ttu-id="33eda-118">关闭命令提示符并选择 "生成 > 生成解决方案" （*请勿选择*"重新生成解决方案"，因为重新生成操作最初会失败）</span><span class="sxs-lookup"><span data-stu-id="33eda-118">Close the command prompt and select Build > Build Solution (do *not* select Rebuild Solution, as rebuilding will initially fail)</span></span>

### <a name="in-visual-studio-code"></a><span data-ttu-id="33eda-119">在 Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="33eda-119">In Visual Studio Code</span></span>

1. <span data-ttu-id="33eda-120">在 Visual Studio Code 中，打开包含要更新项目的文件夹</span><span class="sxs-lookup"><span data-stu-id="33eda-120">In Visual Studio Code, open the folder containing the project to update</span></span>
1. <span data-ttu-id="33eda-121">选择终端 > 新终端</span><span class="sxs-lookup"><span data-stu-id="33eda-121">Select Terminal > New Terminal</span></span>
1. <span data-ttu-id="33eda-122">按照使用命令行进行更新的说明进行操作</span><span class="sxs-lookup"><span data-stu-id="33eda-122">Follow the instructions for updating using the command line</span></span>

### <a name="using-the-command-line"></a><span data-ttu-id="33eda-123">使用命令行</span><span class="sxs-lookup"><span data-stu-id="33eda-123">Using the command line</span></span>

1. <span data-ttu-id="33eda-124">导航到包含项目文件的文件夹</span><span class="sxs-lookup"><span data-stu-id="33eda-124">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="33eda-125">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="33eda-125">Run the following command:</span></span>
```bash
dotnet clean [project_name].csproj
```

3. <span data-ttu-id="33eda-126">将每个 .csproj 文件中[的目标框架更新](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)为 netcoreapp 3.0 （如果它是库项目，则更新 netstandard 2.1）</span><span class="sxs-lookup"><span data-stu-id="33eda-126">[Update the target framework](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) in each of your .csproj files to netcoreapp3.0 (or netstandard2.1 if it is a library project)</span></span>
4. <span data-ttu-id="33eda-127">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="33eda-127">Run the following command:</span></span>
```bash
dotnet add package Microsoft.Quantum.Development.Kit
```
<span data-ttu-id="33eda-128">如果你的项目使用任何其他的 Microsoft 量子包，也请对其运行该命令。</span><span class="sxs-lookup"><span data-stu-id="33eda-128">if your project uses any other Microsoft.Quantum packages, run the command for these too.</span></span>

5. <span data-ttu-id="33eda-129">保存并关闭所有文件</span><span class="sxs-lookup"><span data-stu-id="33eda-129">Save and close all files</span></span>
6. <span data-ttu-id="33eda-130">为每个项目依赖项重复1-4，然后导航回到包含主项目的文件夹，然后运行：</span><span class="sxs-lookup"><span data-stu-id="33eda-130">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>
```bash
dotnet build [project_name].csproj
```

## <a name="update-iq-for-python"></a><span data-ttu-id="33eda-131">更新适用于 Python 的 IQ #</span><span class="sxs-lookup"><span data-stu-id="33eda-131">Update IQ# for Python</span></span>

1. <span data-ttu-id="33eda-132">更新 `iqsharp` 内核</span><span class="sxs-lookup"><span data-stu-id="33eda-132">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="33eda-133">验证 `iqsharp` 版本</span><span class="sxs-lookup"><span data-stu-id="33eda-133">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="33eda-134">应该会看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="33eda-134">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```

1. <span data-ttu-id="33eda-135">更新 `qsharp` 包</span><span class="sxs-lookup"><span data-stu-id="33eda-135">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="33eda-136">验证 `qsharp` 版本</span><span class="sxs-lookup"><span data-stu-id="33eda-136">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="33eda-137">应该会看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="33eda-137">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1911.307
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```
1. <span data-ttu-id="33eda-138">从 `.qs` 文件的位置运行以下命令</span><span class="sxs-lookup"><span data-stu-id="33eda-138">Run the following command from the location of your `.qs` files</span></span>
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

1. <span data-ttu-id="33eda-139">你现在可以使用更新的 QDK 版本来运行现有的量程程序。</span><span class="sxs-lookup"><span data-stu-id="33eda-139">You can now use the updated QDK version to run your existing quantum programs.</span></span>

## <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="33eda-140">更新适用于 Jupyter 笔记本的 IQ #</span><span class="sxs-lookup"><span data-stu-id="33eda-140">Update IQ# for Jupyter notebooks</span></span>

1. <span data-ttu-id="33eda-141">更新 `iqsharp` 内核</span><span class="sxs-lookup"><span data-stu-id="33eda-141">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="33eda-142">验证 `iqsharp` 版本</span><span class="sxs-lookup"><span data-stu-id="33eda-142">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="33eda-143">应该会看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="33eda-143">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```
1. <span data-ttu-id="33eda-144">在 Jupyter Notebook 中的单元格上运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="33eda-144">Run the following command from a cell in your Jupyter Notebook:</span></span>
    ```
    %workspace reload
    ```

1. <span data-ttu-id="33eda-145">你现在可以打开现有的 Jupyter 笔记本，并使用更新的 QDK 运行它。</span><span class="sxs-lookup"><span data-stu-id="33eda-145">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

## <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="33eda-146">更新 Visual Studio QDK 扩展</span><span class="sxs-lookup"><span data-stu-id="33eda-146">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="33eda-147">更新 Q # Visual Studio 扩展</span><span class="sxs-lookup"><span data-stu-id="33eda-147">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="33eda-148">Visual Studio 会提示你接受对[量程 Visual Studio 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)的更新</span><span class="sxs-lookup"><span data-stu-id="33eda-148">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="33eda-149">接受更新</span><span class="sxs-lookup"><span data-stu-id="33eda-149">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="33eda-150">项目模板将更新为扩展。</span><span class="sxs-lookup"><span data-stu-id="33eda-150">The project templates are updated with the extension.</span></span> <span data-ttu-id="33eda-151">更新的模板仅适用于新创建的项目。</span><span class="sxs-lookup"><span data-stu-id="33eda-151">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="33eda-152">更新扩展时，不会更新现有项目的代码。</span><span class="sxs-lookup"><span data-stu-id="33eda-152">The code for your existing projects is not updated when the extension is updated.</span></span>

## <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="33eda-153">更新 VS Code QDK 扩展</span><span class="sxs-lookup"><span data-stu-id="33eda-153">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="33eda-154">更新量程 VS Code 扩展</span><span class="sxs-lookup"><span data-stu-id="33eda-154">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="33eda-155">重新启动 VS Code</span><span class="sxs-lookup"><span data-stu-id="33eda-155">Restart VS Code</span></span>
    - <span data-ttu-id="33eda-156">导航到 "**扩展**" 选项卡</span><span class="sxs-lookup"><span data-stu-id="33eda-156">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="33eda-157">选择 Visual Studio Code 扩展的**Microsoft Quantum Development Kit**</span><span class="sxs-lookup"><span data-stu-id="33eda-157">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="33eda-158">重新加载扩展</span><span class="sxs-lookup"><span data-stu-id="33eda-158">Reload the extension</span></span>

1. <span data-ttu-id="33eda-159">更新量程项目模板：</span><span class="sxs-lookup"><span data-stu-id="33eda-159">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="33eda-160">转到“视图” -> “命令面板”</span><span class="sxs-lookup"><span data-stu-id="33eda-160">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="33eda-161">选择**Q #：安装项目模板**</span><span class="sxs-lookup"><span data-stu-id="33eda-161">Select **Q#: Install project templates**</span></span>

## <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="33eda-162">C#，使用 `dotnet` 命令行工具</span><span class="sxs-lookup"><span data-stu-id="33eda-162">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="33eda-163">更新 .NET 的量程项目模板</span><span class="sxs-lookup"><span data-stu-id="33eda-163">Update the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a><span data-ttu-id="33eda-164">还有什么？</span><span class="sxs-lookup"><span data-stu-id="33eda-164">What's next?</span></span>

<span data-ttu-id="33eda-165">现在，你已在首选环境中更新了量程开发工具包，接下来可以继续开发并运行量程程序。</span><span class="sxs-lookup"><span data-stu-id="33eda-165">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="33eda-166">如果还没有编写程序，可以开始使用[第一个量程计划](xref:microsoft.quantum.write-program)。</span><span class="sxs-lookup"><span data-stu-id="33eda-166">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
