---
title: 了解如何更新 Microsoft Quantum Development Kit （QDK）
description: '介绍如何将您的 Q # 项目和 Microsoft Quantum Development Kit 更新到最新版本。'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: bf6d6d3d80af485b555429f25b125bfea685bebf
ms.sourcegitcommit: c57c271ab73f75f165401651fad2b5bc143e9c8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "82862201"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="e30b9-103">更新 Microsoft Quantum Development Kit （QDK）</span><span class="sxs-lookup"><span data-stu-id="e30b9-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="e30b9-104">了解如何将 Microsoft Quantum Development Kit （QDK）更新到最新版本。</span><span class="sxs-lookup"><span data-stu-id="e30b9-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="e30b9-105">本文假设已安装 QDK。</span><span class="sxs-lookup"><span data-stu-id="e30b9-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="e30b9-106">如果你是首次安装，请参阅[安装指南](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="e30b9-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="e30b9-107">建议你随时了解最新的 QDK 版本。</span><span class="sxs-lookup"><span data-stu-id="e30b9-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="e30b9-108">按照此更新指南升级到最新的 QDK 版本。</span><span class="sxs-lookup"><span data-stu-id="e30b9-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="e30b9-109">此过程由两个部分组成：</span><span class="sxs-lookup"><span data-stu-id="e30b9-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="e30b9-110">更新现有的 Q # 文件和项目，以使代码与任何更新的语法对齐</span><span class="sxs-lookup"><span data-stu-id="e30b9-110">updating your existing Q# files and projects to align your code with any updated syntax</span></span>
2. <span data-ttu-id="e30b9-111">为所选开发环境更新 QDK 本身</span><span class="sxs-lookup"><span data-stu-id="e30b9-111">updating the QDK itself for your chosen development environment</span></span> 

## <a name="updating-q-projects"></a><span data-ttu-id="e30b9-112">更新 Q # 项目</span><span class="sxs-lookup"><span data-stu-id="e30b9-112">Updating Q# Projects</span></span> 

<span data-ttu-id="e30b9-113">无论使用 c # 还是 Python 来承载 Q # 操作，请按照以下说明更新 Q # 项目。</span><span class="sxs-lookup"><span data-stu-id="e30b9-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="e30b9-114">首先，请检查是否安装了最新版本的[.NET Core SDK 3.1](https://dotnet.microsoft.com/download)。</span><span class="sxs-lookup"><span data-stu-id="e30b9-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="e30b9-115">在命令提示符下运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e30b9-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="e30b9-116">验证输出是否为`3.1.100`或更高版本。</span><span class="sxs-lookup"><span data-stu-id="e30b9-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="e30b9-117">如果未安装，请安装[最新版本](https://dotnet.microsoft.com/download)，然后重新检查。</span><span class="sxs-lookup"><span data-stu-id="e30b9-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="e30b9-118">然后根据您的设置（Visual Studio、Visual Studio Code 或直接命令行），按照以下说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="e30b9-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="e30b9-119">在 Visual Studio 中更新 Q # 项目</span><span class="sxs-lookup"><span data-stu-id="e30b9-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="e30b9-120">更新到最新版本的 Visual Studio 2019，请参阅[此处](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019)了解相关说明</span><span class="sxs-lookup"><span data-stu-id="e30b9-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
2. <span data-ttu-id="e30b9-121">在 Visual Studio 中打开解决方案</span><span class="sxs-lookup"><span data-stu-id="e30b9-121">Open your solution in Visual Studio</span></span>
3. <span data-ttu-id="e30b9-122">从菜单中选择 "**生成** -> **干净解决方案**"</span><span class="sxs-lookup"><span data-stu-id="e30b9-122">From the menu, select **Build** -> **Clean Solution**</span></span>
4. <span data-ttu-id="e30b9-123">在每个 .csproj 文件中，将目标框架更新为`netcoreapp3.1` （或者`netstandard2.1` ，如果它是库项目）。</span><span class="sxs-lookup"><span data-stu-id="e30b9-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="e30b9-124">也就是说，编辑以下格式的行：</span><span class="sxs-lookup"><span data-stu-id="e30b9-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="e30b9-125">可在[此处](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)找到有关指定目标框架的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e30b9-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
5. <span data-ttu-id="e30b9-126">保存并关闭解决方案中的所有文件</span><span class="sxs-lookup"><span data-stu-id="e30b9-126">Save and close all files in your solution</span></span>
6. <span data-ttu-id="e30b9-127">选择**工具** -> **命令行** -> **开发人员命令提示**</span><span class="sxs-lookup"><span data-stu-id="e30b9-127">Select **Tools** -> **Command Line** -> **Developer Command Prompt**</span></span>
7. <span data-ttu-id="e30b9-128">对于解决方案中的每个项目，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e30b9-128">For each project in the solution, run the following command:</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="e30b9-129">如果你的项目使用任何其他的 Microsoft 量子包（如 Microsoft 量子），则也要为这些包运行命令。</span><span class="sxs-lookup"><span data-stu-id="e30b9-129">If your projects use any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
8. <span data-ttu-id="e30b9-130">关闭命令提示符并选择 "**生成** -> **生成解决方案**" （*不选择 "* 重新生成解决方案"）</span><span class="sxs-lookup"><span data-stu-id="e30b9-130">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution)</span></span>

<span data-ttu-id="e30b9-131">你现在可以直接跳到[更新你的 Visual STUDIO QDK 扩展](#update-visual-studio-qdk-extension)。</span><span class="sxs-lookup"><span data-stu-id="e30b9-131">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="e30b9-132">更新 Visual Studio Code 中的 Q # 项目</span><span class="sxs-lookup"><span data-stu-id="e30b9-132">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="e30b9-133">在 Visual Studio Code 中，打开包含要更新项目的文件夹</span><span class="sxs-lookup"><span data-stu-id="e30b9-133">In Visual Studio Code, open the folder containing the project to update</span></span>
2. <span data-ttu-id="e30b9-134">选择**终端** -> **新终端**</span><span class="sxs-lookup"><span data-stu-id="e30b9-134">Select **Terminal** -> **New Terminal**</span></span>
3. <span data-ttu-id="e30b9-135">按照使用命令行进行更新的说明进行操作（如下所示）</span><span class="sxs-lookup"><span data-stu-id="e30b9-135">Follow the instructions for updating using the command line (directly below)</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="e30b9-136">使用命令行更新 Q # 项目</span><span class="sxs-lookup"><span data-stu-id="e30b9-136">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="e30b9-137">导航到包含项目文件的文件夹</span><span class="sxs-lookup"><span data-stu-id="e30b9-137">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="e30b9-138">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e30b9-138">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="e30b9-139">在每个 .csproj 文件中，将目标框架更新为`netcoreapp3.1` （或者`netstandard2.1` ，如果它是库项目）。</span><span class="sxs-lookup"><span data-stu-id="e30b9-139">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="e30b9-140">也就是说，编辑以下格式的行：</span><span class="sxs-lookup"><span data-stu-id="e30b9-140">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="e30b9-141">可在[此处](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)找到有关指定目标框架的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e30b9-141">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
4. <span data-ttu-id="e30b9-142">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e30b9-142">Run the following command:</span></span>

    ```dotnetcli
    dotnet add package Microsoft.Quantum.Development.Kit
    ```

    <span data-ttu-id="e30b9-143">如果你的项目使用任何其他的 Microsoft 量子包（如 Microsoft 量子），则也要为这些包运行命令。</span><span class="sxs-lookup"><span data-stu-id="e30b9-143">If your project uses any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
5. <span data-ttu-id="e30b9-144">保存并关闭所有文件。</span><span class="sxs-lookup"><span data-stu-id="e30b9-144">Save and close all files.</span></span>
6. <span data-ttu-id="e30b9-145">为每个项目依赖项重复1-4，然后导航回到包含主项目的文件夹，然后运行：</span><span class="sxs-lookup"><span data-stu-id="e30b9-145">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="e30b9-146">现在，你的 Q # 项目已更新，请按照下面的说明更新 QDK 本身。</span><span class="sxs-lookup"><span data-stu-id="e30b9-146">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="e30b9-147">更新 QDK</span><span class="sxs-lookup"><span data-stu-id="e30b9-147">Updating the QDK</span></span>

<span data-ttu-id="e30b9-148">更新 QDK 的过程因开发语言和环境而异。</span><span class="sxs-lookup"><span data-stu-id="e30b9-148">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="e30b9-149">选择下面的开发环境。</span><span class="sxs-lookup"><span data-stu-id="e30b9-149">Select your development environment below.</span></span>

* [<span data-ttu-id="e30b9-150">Python：更新 IQ # 扩展</span><span class="sxs-lookup"><span data-stu-id="e30b9-150">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="e30b9-151">Jupyter 笔记本：更新 IQ # 扩展</span><span class="sxs-lookup"><span data-stu-id="e30b9-151">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="e30b9-152">Visual Studio：更新 QDK 扩展</span><span class="sxs-lookup"><span data-stu-id="e30b9-152">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="e30b9-153">VS Code：更新 QDK 扩展</span><span class="sxs-lookup"><span data-stu-id="e30b9-153">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="e30b9-154">命令行和 c #：更新项目模板</span><span class="sxs-lookup"><span data-stu-id="e30b9-154">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="e30b9-155">更新适用于 Python 的 IQ #</span><span class="sxs-lookup"><span data-stu-id="e30b9-155">Update IQ# for Python</span></span>

1. <span data-ttu-id="e30b9-156">更新`iqsharp`内核</span><span class="sxs-lookup"><span data-stu-id="e30b9-156">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="e30b9-157">验证`iqsharp`版本</span><span class="sxs-lookup"><span data-stu-id="e30b9-157">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="e30b9-158">应会看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="e30b9-158">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="e30b9-159">请不要担心`iqsharp`版本是否较高，它应与[最新版本](xref:microsoft.quantum.relnotes)相匹配。</span><span class="sxs-lookup"><span data-stu-id="e30b9-159">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="e30b9-160">更新`qsharp`包</span><span class="sxs-lookup"><span data-stu-id="e30b9-160">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="e30b9-161">验证`qsharp`版本</span><span class="sxs-lookup"><span data-stu-id="e30b9-161">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="e30b9-162">应会看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="e30b9-162">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="e30b9-163">从`.qs`文件的位置运行以下命令</span><span class="sxs-lookup"><span data-stu-id="e30b9-163">Run the following command from the location of your `.qs` files</span></span>

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="e30b9-164">你现在可以使用更新的 QDK 版本来运行现有的量程程序。</span><span class="sxs-lookup"><span data-stu-id="e30b9-164">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="e30b9-165">更新适用于 Jupyter 笔记本的 IQ #</span><span class="sxs-lookup"><span data-stu-id="e30b9-165">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="e30b9-166">更新`iqsharp`内核</span><span class="sxs-lookup"><span data-stu-id="e30b9-166">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="e30b9-167">验证`iqsharp`版本</span><span class="sxs-lookup"><span data-stu-id="e30b9-167">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="e30b9-168">输出应类似如下所示：</span><span class="sxs-lookup"><span data-stu-id="e30b9-168">Your output should be similar to the following:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="e30b9-169">请不要担心`iqsharp`版本是否较高，它应与[最新版本](xref:microsoft.quantum.relnotes)相匹配。</span><span class="sxs-lookup"><span data-stu-id="e30b9-169">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="e30b9-170">在 Jupyter Notebook 中的单元格上运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e30b9-170">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="e30b9-171">你现在可以打开现有的 Jupyter 笔记本，并使用更新的 QDK 运行它。</span><span class="sxs-lookup"><span data-stu-id="e30b9-171">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="e30b9-172">更新 Visual Studio QDK 扩展</span><span class="sxs-lookup"><span data-stu-id="e30b9-172">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="e30b9-173">更新 Q # Visual Studio 扩展</span><span class="sxs-lookup"><span data-stu-id="e30b9-173">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="e30b9-174">Visual Studio 会提示你接受对[量程 Visual Studio 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)的更新</span><span class="sxs-lookup"><span data-stu-id="e30b9-174">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="e30b9-175">接受更新</span><span class="sxs-lookup"><span data-stu-id="e30b9-175">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="e30b9-176">项目模板将更新为扩展。</span><span class="sxs-lookup"><span data-stu-id="e30b9-176">The project templates are updated with the extension.</span></span> <span data-ttu-id="e30b9-177">更新的模板仅适用于新创建的项目。</span><span class="sxs-lookup"><span data-stu-id="e30b9-177">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="e30b9-178">更新扩展时，不会更新现有项目的代码。</span><span class="sxs-lookup"><span data-stu-id="e30b9-178">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="e30b9-179">更新 VS Code QDK 扩展</span><span class="sxs-lookup"><span data-stu-id="e30b9-179">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="e30b9-180">更新量程 VS Code 扩展</span><span class="sxs-lookup"><span data-stu-id="e30b9-180">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="e30b9-181">重新启动 VS Code</span><span class="sxs-lookup"><span data-stu-id="e30b9-181">Restart VS Code</span></span>
    - <span data-ttu-id="e30b9-182">导航到 "**扩展**" 选项卡</span><span class="sxs-lookup"><span data-stu-id="e30b9-182">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="e30b9-183">选择 Visual Studio Code 扩展的**Microsoft Quantum Development Kit**</span><span class="sxs-lookup"><span data-stu-id="e30b9-183">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="e30b9-184">重新加载扩展</span><span class="sxs-lookup"><span data-stu-id="e30b9-184">Reload the extension</span></span>

2. <span data-ttu-id="e30b9-185">更新量程项目模板：</span><span class="sxs-lookup"><span data-stu-id="e30b9-185">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="e30b9-186">中转到 "**视图** -> "**命令面板**</span><span class="sxs-lookup"><span data-stu-id="e30b9-186">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="e30b9-187">选择**Q #：安装项目模板**</span><span class="sxs-lookup"><span data-stu-id="e30b9-187">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="e30b9-188">几秒钟后，你应该会看到一个弹出窗口，确认 "项目模板已成功安装"</span><span class="sxs-lookup"><span data-stu-id="e30b9-188">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="e30b9-189">C #，使用`dotnet`命令行工具</span><span class="sxs-lookup"><span data-stu-id="e30b9-189">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="e30b9-190">更新 .NET 的量程项目模板</span><span class="sxs-lookup"><span data-stu-id="e30b9-190">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a><span data-ttu-id="e30b9-191">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e30b9-191">What's next?</span></span>

<span data-ttu-id="e30b9-192">现在，你已在首选环境中更新了量程开发工具包，接下来可以继续开发并运行量程程序。</span><span class="sxs-lookup"><span data-stu-id="e30b9-192">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="e30b9-193">如果还没有编写程序，可以开始使用[第一个量程计划](xref:microsoft.quantum.write-program)。</span><span class="sxs-lookup"><span data-stu-id="e30b9-193">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
