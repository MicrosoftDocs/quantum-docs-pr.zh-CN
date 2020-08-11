---
title: 更新 Quantum 开发工具包 (QDK)
description: 介绍如何将 Q# 项目和 Microsoft Quantum 开发工具包更新到当前版本。
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
no-loc:
- Q#
- $$v
ms.openlocfilehash: dd7360961aa728a6aa63b8d8c4e4840f5bf2afe8
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866751"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="aa350-103">更新 Microsoft Quantum 开发工具包 (QDK)</span><span class="sxs-lookup"><span data-stu-id="aa350-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="aa350-104">了解如何将 Microsoft Quantum 开发工具包 (QDK) 更新到最新版本。</span><span class="sxs-lookup"><span data-stu-id="aa350-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="aa350-105">本文假设你已安装 QDK。</span><span class="sxs-lookup"><span data-stu-id="aa350-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="aa350-106">如果是首次安装，请参阅[安装指南](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="aa350-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="aa350-107">建议始终使用最新 QDK 版本。</span><span class="sxs-lookup"><span data-stu-id="aa350-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="aa350-108">按照此更新指南升级到最新的 QDK 版本。</span><span class="sxs-lookup"><span data-stu-id="aa350-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="aa350-109">该过程包含两个阶段：</span><span class="sxs-lookup"><span data-stu-id="aa350-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="aa350-110">更新现有 Q# 文件和项目，使代码与任何更新的语法保持一致。</span><span class="sxs-lookup"><span data-stu-id="aa350-110">Updating your existing Q# files and projects to align your code with any updated syntax.</span></span>
2. <span data-ttu-id="aa350-111">为所选的开发环境更新 QDK。</span><span class="sxs-lookup"><span data-stu-id="aa350-111">Updating the QDK itself for your chosen development environment.</span></span>

## <a name="updating-no-locq-projects"></a><span data-ttu-id="aa350-112">更新 Q# 项目</span><span class="sxs-lookup"><span data-stu-id="aa350-112">Updating Q# Projects</span></span> 

<span data-ttu-id="aa350-113">无论你是使用 C# 还是 Python 来托管 Q# 操作，都请按照以下说明更新你的 Q# 项目。</span><span class="sxs-lookup"><span data-stu-id="aa350-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="aa350-114">首先，请检查是否具有最新版 [.NET Core SDK 3.1](https://dotnet.microsoft.com/download)。</span><span class="sxs-lookup"><span data-stu-id="aa350-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="aa350-115">在命令提示符下运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="aa350-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="aa350-116">验证输出为 `3.1.100` 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="aa350-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="aa350-117">如果未安装，请安装[最新版](https://dotnet.microsoft.com/download)并再次检查。</span><span class="sxs-lookup"><span data-stu-id="aa350-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="aa350-118">然后根据自己的设置（Visual Studio、Visual Studio Code 或直接使用命令行）按照以下说明操作。</span><span class="sxs-lookup"><span data-stu-id="aa350-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-no-locq-projects-in-visual-studio"></a><span data-ttu-id="aa350-119">更新 Visual Studio 中的 Q# 项目</span><span class="sxs-lookup"><span data-stu-id="aa350-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="aa350-120">更新到最新版 Visual Studio 2019，请参阅[此处](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019)了解相关说明。</span><span class="sxs-lookup"><span data-stu-id="aa350-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions.</span></span>
2. <span data-ttu-id="aa350-121">在 Visual Studio 中打开解决方案。</span><span class="sxs-lookup"><span data-stu-id="aa350-121">Open your solution in Visual Studio.</span></span>
3. <span data-ttu-id="aa350-122">从菜单中选择“生成” -> “清理解决方案” 。</span><span class="sxs-lookup"><span data-stu-id="aa350-122">From the menu, select **Build** -> **Clean Solution**.</span></span>
4. <span data-ttu-id="aa350-123">在每个 .csproj 文件中，将目标框架更新为 `netcoreapp3.1`（如果它是库项目，则更新为 `netstandard2.1`）。</span><span class="sxs-lookup"><span data-stu-id="aa350-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="aa350-124">也就是说，编辑以下格式的行：</span><span class="sxs-lookup"><span data-stu-id="aa350-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="aa350-125">可在[此处](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)找到有关如何指定目标框架的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="aa350-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

5. <span data-ttu-id="aa350-126">在每个 .csproj 文件中，将 SDK 设置为 `Microsoft.Quantum.Sdk`，如下面的行所示。</span><span class="sxs-lookup"><span data-stu-id="aa350-126">In each of the .csproj files, set the SDK to `Microsoft.Quantum.Sdk`, as indicated in the line below.</span></span> <span data-ttu-id="aa350-127">请注意，版本号应为最新的可用版本号，可以查看[发行说明](https://docs.microsoft.com/quantum/relnotes/)进行确认。</span><span class="sxs-lookup"><span data-stu-id="aa350-127">Please notice that the version number should be the latest available, and you can determine it by reviewing the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span>

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    ```

6. <span data-ttu-id="aa350-128">保存并关闭解决方案中的所有文件。</span><span class="sxs-lookup"><span data-stu-id="aa350-128">Save and close all files in your solution.</span></span>

7. <span data-ttu-id="aa350-129">选择“工具” -> “命令行” -> “开发人员命令提示”  。</span><span class="sxs-lookup"><span data-stu-id="aa350-129">Select **Tools** -> **Command Line** -> **Developer Command Prompt**.</span></span> <span data-ttu-id="aa350-130">或者，也可以在 Visual Studio 中使用程序包管理器控制台。</span><span class="sxs-lookup"><span data-stu-id="aa350-130">Alternatively, you can use the package management console in Visual Studio.</span></span>

8. <span data-ttu-id="aa350-131">为解决方案中的每个项目运行以下命令，以删除此包：</span><span class="sxs-lookup"><span data-stu-id="aa350-131">For each project in the solution, run the following command to **remove** this package:</span></span>

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="aa350-132">如果项目使用任何其他的 Microsoft.Quantum 或 Microsoft.Azure.Quantum 包（如 Microsoft.Quantum.Numerics），请为其运行“添加”命令，以更新所用的版本。</span><span class="sxs-lookup"><span data-stu-id="aa350-132">If your projects use any other Microsoft.Quantum or Microsoft.Azure.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the **add** command for these to update the version used.</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. <span data-ttu-id="aa350-133">关闭命令提示符并选择“生成” -> "生成解决方案（请勿选择“重新生成解决方案”） 。</span><span class="sxs-lookup"><span data-stu-id="aa350-133">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution).</span></span>

<span data-ttu-id="aa350-134">现可直接跳到[更新 Visual Studio QDK 扩展](#update-visual-studio-qdk-extension)。</span><span class="sxs-lookup"><span data-stu-id="aa350-134">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-no-locq-projects-in-visual-studio-code"></a><span data-ttu-id="aa350-135">更新 Visual Studio Code 中的 Q# 项目</span><span class="sxs-lookup"><span data-stu-id="aa350-135">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="aa350-136">在 Visual Studio Code 中，打开包含要更新的项目的文件夹。</span><span class="sxs-lookup"><span data-stu-id="aa350-136">In Visual Studio Code, open the folder containing the project to update.</span></span>
2. <span data-ttu-id="aa350-137">选择“终端” -> “新终端” 。</span><span class="sxs-lookup"><span data-stu-id="aa350-137">Select **Terminal** -> **New Terminal**.</span></span>
3. <span data-ttu-id="aa350-138">按照使用命令行进行更新的相关说明进行操作（如下所示）。</span><span class="sxs-lookup"><span data-stu-id="aa350-138">Follow the instructions for updating using the command line (directly below).</span></span>

### <a name="update-no-locq-projects-using-the-command-line"></a><span data-ttu-id="aa350-139">使用命令行更新 Q# 项目</span><span class="sxs-lookup"><span data-stu-id="aa350-139">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="aa350-140">导航到包含主项目文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="aa350-140">Navigate to the folder containing your main project file.</span></span>

2. <span data-ttu-id="aa350-141">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="aa350-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="aa350-142">确定 QDK 的当前版本。</span><span class="sxs-lookup"><span data-stu-id="aa350-142">Determine the current version of the QDK.</span></span> <span data-ttu-id="aa350-143">若要查找当前版本，可查看[发行说明](https://docs.microsoft.com/quantum/relnotes/)。</span><span class="sxs-lookup"><span data-stu-id="aa350-143">To find it, you can review the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span> <span data-ttu-id="aa350-144">版本的格式与 `0.12.20072031` 类似。</span><span class="sxs-lookup"><span data-stu-id="aa350-144">The version will be in a format similar to `0.12.20072031`.</span></span>

4. <span data-ttu-id="aa350-145">在每个 `.csproj` 文件中，完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="aa350-145">In each of your `.csproj` files, go through the following steps:</span></span>

    - <span data-ttu-id="aa350-146">将目标框架更新为 `netcoreapp3.1`（如果它是库项目，则更新为 `netstandard2.1`）。</span><span class="sxs-lookup"><span data-stu-id="aa350-146">Update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span> <span data-ttu-id="aa350-147">也就是说，编辑以下格式的行：</span><span class="sxs-lookup"><span data-stu-id="aa350-147">That is, edit lines of the form:</span></span>

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        <span data-ttu-id="aa350-148">可在[此处](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)找到有关如何指定目标框架的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="aa350-148">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

    - <span data-ttu-id="aa350-149">替换项目定义中的 SDK 引用。</span><span class="sxs-lookup"><span data-stu-id="aa350-149">Replace the reference to the SDK in the project definition.</span></span> <span data-ttu-id="aa350-150">请确保版本号与步骤 3 中确定的值相符。</span><span class="sxs-lookup"><span data-stu-id="aa350-150">Make sure that the version number corresponds to the value determined in **step 3**.</span></span>

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
        ```

    - <span data-ttu-id="aa350-151">删除对包 `Microsoft.Quantum.Development.Kit` 的引用（如有），该引用在以下条目中指定：</span><span class="sxs-lookup"><span data-stu-id="aa350-151">Remove the reference to package `Microsoft.Quantum.Development.Kit` if present, which will be specified in the following entry:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - <span data-ttu-id="aa350-152">将所有 Microsoft Quantum 包版本更新为最新发布的 QDK 版本（在步骤 3 中确定）。</span><span class="sxs-lookup"><span data-stu-id="aa350-152">Update the version of the all the Microsoft Quantum packages to the most recently released version of the QDK (determined in **step 3**).</span></span> <span data-ttu-id="aa350-153">这些包的命名方式如下：</span><span class="sxs-lookup"><span data-stu-id="aa350-153">Those packages are named with the following patterns:</span></span>

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        <span data-ttu-id="aa350-154">对包的引用格式如下：</span><span class="sxs-lookup"><span data-stu-id="aa350-154">References to packages have the following format:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.12.20072031" />
        ```

    - <span data-ttu-id="aa350-155">保存更新的文件。</span><span class="sxs-lookup"><span data-stu-id="aa350-155">Save the updated file.</span></span>

    - <span data-ttu-id="aa350-156">通过执行以下操作还原项目的依赖项：</span><span class="sxs-lookup"><span data-stu-id="aa350-156">Restore the dependencies of the project, by doing the following:</span></span>

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. <span data-ttu-id="aa350-157">导航回包含主项目的文件夹，然后运行：</span><span class="sxs-lookup"><span data-stu-id="aa350-157">Navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="aa350-158">Q# 项目已更新，现请按照下面的说明更新 QDK。</span><span class="sxs-lookup"><span data-stu-id="aa350-158">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="aa350-159">更新 QDK</span><span class="sxs-lookup"><span data-stu-id="aa350-159">Updating the QDK</span></span>

<span data-ttu-id="aa350-160">更新 QDK 的过程因开发语言和环境而异。</span><span class="sxs-lookup"><span data-stu-id="aa350-160">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="aa350-161">选择下面的开发环境。</span><span class="sxs-lookup"><span data-stu-id="aa350-161">Select your development environment below.</span></span>

* [<span data-ttu-id="aa350-162">Python：更新 `qsharp` 包</span><span class="sxs-lookup"><span data-stu-id="aa350-162">Python: update the `qsharp` package</span></span>](#update-the-qsharp-python-package)
* [<span data-ttu-id="aa350-163">Jupyter Notebooks: 更新 IQ# 内核</span><span class="sxs-lookup"><span data-stu-id="aa350-163">Jupyter Notebooks: update the IQ# kernel</span></span>](#update-the-iq-jupyter-kernel)
* [<span data-ttu-id="aa350-164">Visual Studio：更新 QDK 扩展</span><span class="sxs-lookup"><span data-stu-id="aa350-164">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="aa350-165">VS Code：更新 QDK 扩展</span><span class="sxs-lookup"><span data-stu-id="aa350-165">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="aa350-166">命令行和 C#：更新项目模板</span><span class="sxs-lookup"><span data-stu-id="aa350-166">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-the-qsharp-python-package"></a><span data-ttu-id="aa350-167">更新 `qsharp` Python 包</span><span class="sxs-lookup"><span data-stu-id="aa350-167">Update the `qsharp` Python package</span></span>

<span data-ttu-id="aa350-168">更新过程取决于你最初安装使用的是 conda 还是 .NET CLI 和 pip。</span><span class="sxs-lookup"><span data-stu-id="aa350-168">The update procedure depends on whether you originally installed using conda or using the .NET CLI and pip.</span></span>

#### <a name="update-using-conda-recommended"></a>[<span data-ttu-id="aa350-169">使用 conda 进行更新（推荐）</span><span class="sxs-lookup"><span data-stu-id="aa350-169">Update using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="aa350-170">激活安装 `qsharp` 包的 conda 环境，然后运行该命令来更新它：</span><span class="sxs-lookup"><span data-stu-id="aa350-170">Activate the conda environment where you installed the `qsharp` package, and then run this command to update it:</span></span>

    ```
    conda update -c quantum-engineering qsharp
    ```

1. <span data-ttu-id="aa350-171">从 `.qs` 文件的位置运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="aa350-171">Run the following command from the location of your `.qs` files:</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="aa350-172">使用 .NET CLI 和 pip 进行更新（高级）</span><span class="sxs-lookup"><span data-stu-id="aa350-172">Update using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="aa350-173">更新 `iqsharp` 内核</span><span class="sxs-lookup"><span data-stu-id="aa350-173">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="aa350-174">验证 `iqsharp` 版本</span><span class="sxs-lookup"><span data-stu-id="aa350-174">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="aa350-175">应该会看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="aa350-175">You should see the following output:</span></span>

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    <span data-ttu-id="aa350-176">如果你的 `iqsharp` 版本较高，则不必担心。</span><span class="sxs-lookup"><span data-stu-id="aa350-176">Don't worry if your `iqsharp` version is higher.</span></span> <span data-ttu-id="aa350-177">它应与[最新版本](xref:microsoft.quantum.relnotes)匹配。</span><span class="sxs-lookup"><span data-stu-id="aa350-177">It should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

1. <span data-ttu-id="aa350-178">更新 `qsharp` 包：</span><span class="sxs-lookup"><span data-stu-id="aa350-178">Update the `qsharp` package:</span></span>

    ```
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="aa350-179">验证 `qsharp` 版本：</span><span class="sxs-lookup"><span data-stu-id="aa350-179">Verify the `qsharp` version:</span></span>

    ```
    pip show qsharp
    ```

    <span data-ttu-id="aa350-180">应该会看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="aa350-180">You should see the following output:</span></span>

    ```
    Name: qsharp
    Version: 0.12.2007.2031
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. <span data-ttu-id="aa350-181">从 `.qs` 文件的位置运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="aa350-181">Run the following command from the location of your `.qs` files:</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

***

<span data-ttu-id="aa350-182">你现可使用已更新的 `qsharp` Python 包来运行现有量子程序。</span><span class="sxs-lookup"><span data-stu-id="aa350-182">You can now use the updated `qsharp` Python package to run your existing quantum programs.</span></span>

### <a name="update-the-ino-locq-jupyter-kernel"></a><span data-ttu-id="aa350-183">更新 IQ# Jupyter 内核</span><span class="sxs-lookup"><span data-stu-id="aa350-183">Update the IQ# Jupyter kernel</span></span>

<span data-ttu-id="aa350-184">更新过程取决于你最初安装使用的是 conda 还是 .NET CLI 和 pip。</span><span class="sxs-lookup"><span data-stu-id="aa350-184">The update procedure depends on whether you originally installed using conda or using the .NET CLI and pip.</span></span>

#### <a name="update-using-conda-recommended"></a>[<span data-ttu-id="aa350-185">使用 conda 进行更新（推荐）</span><span class="sxs-lookup"><span data-stu-id="aa350-185">Update using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="aa350-186">激活安装 `qsharp` 包的 conda 环境，然后运行该命令来更新它：</span><span class="sxs-lookup"><span data-stu-id="aa350-186">Activate the conda environment where you installed the `qsharp` package, and then run this command to update it:</span></span>

    ```
    conda update -c quantum-engineering qsharp
    ```

1. <span data-ttu-id="aa350-187">从每个现有 Q# Jupyter Notebooks 的单元格中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="aa350-187">Run the following command from a cell in each of your existing Q# Jupyter Notebooks:</span></span>

    ```
    %workspace reload
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="aa350-188">使用 .NET CLI 和 pip 进行更新（高级）</span><span class="sxs-lookup"><span data-stu-id="aa350-188">Update using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="aa350-189">更新 `Microsoft.Quantum.IQSharp` 包：</span><span class="sxs-lookup"><span data-stu-id="aa350-189">Update the `Microsoft.Quantum.IQSharp` package:</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="aa350-190">验证 `iqsharp` 版本：</span><span class="sxs-lookup"><span data-stu-id="aa350-190">Verify the `iqsharp` version:</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="aa350-191">输出应类似如下所示：</span><span class="sxs-lookup"><span data-stu-id="aa350-191">Your output should be similar to the following:</span></span>

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    <span data-ttu-id="aa350-192">如果你的 `iqsharp` 版本较高，则不必担心。</span><span class="sxs-lookup"><span data-stu-id="aa350-192">Don't worry if your `iqsharp` version is higher.</span></span> <span data-ttu-id="aa350-193">它应与[最新版本](xref:microsoft.quantum.relnotes)匹配。</span><span class="sxs-lookup"><span data-stu-id="aa350-193">It should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

1. <span data-ttu-id="aa350-194">从每个现有 Q# Jupyter Notebooks 的单元格中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="aa350-194">Run the following command from a cell in each of your existing Q# Jupyter Notebooks:</span></span>

    ```
    %workspace reload
    ```

***

<span data-ttu-id="aa350-195">你现可使用已更新的 IQ# 内核来运行现有 Q# Jupyter Notebooks。</span><span class="sxs-lookup"><span data-stu-id="aa350-195">You can now use the updated IQ# kernel to run your existing Q# Jupyter Notebooks.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="aa350-196">更新 Visual Studio QDK 扩展</span><span class="sxs-lookup"><span data-stu-id="aa350-196">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="aa350-197">更新 Q# Visual Studio 扩展</span><span class="sxs-lookup"><span data-stu-id="aa350-197">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="aa350-198">Visual Studio 会提示你接受 [Quantum Visual Studio 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)的更新</span><span class="sxs-lookup"><span data-stu-id="aa350-198">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="aa350-199">接受更新</span><span class="sxs-lookup"><span data-stu-id="aa350-199">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="aa350-200">项目模板将随扩展更新。</span><span class="sxs-lookup"><span data-stu-id="aa350-200">The project templates are updated with the extension.</span></span> <span data-ttu-id="aa350-201">更新后的模板仅适用于新创建的项目。</span><span class="sxs-lookup"><span data-stu-id="aa350-201">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="aa350-202">更新扩展时，不会更新现有项目的代码。</span><span class="sxs-lookup"><span data-stu-id="aa350-202">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="aa350-203">更新 VS Code QDK 扩展</span><span class="sxs-lookup"><span data-stu-id="aa350-203">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="aa350-204">更新 Quantum VS Code 扩展</span><span class="sxs-lookup"><span data-stu-id="aa350-204">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="aa350-205">重启 VS Code</span><span class="sxs-lookup"><span data-stu-id="aa350-205">Restart VS Code</span></span>
    - <span data-ttu-id="aa350-206">导航到“扩展”选项卡</span><span class="sxs-lookup"><span data-stu-id="aa350-206">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="aa350-207">选择适用于 Visual Studio Code 的 Microsoft Quantum 开发工具包扩展</span><span class="sxs-lookup"><span data-stu-id="aa350-207">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="aa350-208">重新加载扩展</span><span class="sxs-lookup"><span data-stu-id="aa350-208">Reload the extension</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="aa350-209">C#，使用 `dotnet` 命令行工具</span><span class="sxs-lookup"><span data-stu-id="aa350-209">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="aa350-210">更新适用于 .NET 的 Quantum 项目模板</span><span class="sxs-lookup"><span data-stu-id="aa350-210">Update the Quantum project templates for .NET</span></span>

    <span data-ttu-id="aa350-211">通过命令行：</span><span class="sxs-lookup"><span data-stu-id="aa350-211">From the command line:</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

   <span data-ttu-id="aa350-212">如果计划使用命令行模板，并且已经安装 VS Code QDK 扩展，可从扩展本身更新项目模板：</span><span class="sxs-lookup"><span data-stu-id="aa350-212">Alternatively, if you intend to use the command line templates, and already have the VS Code QDK extension installed, you can update the project templates from the extension itself:</span></span>

   - [<span data-ttu-id="aa350-213">更新 QDK 扩展</span><span class="sxs-lookup"><span data-stu-id="aa350-213">Update the QDK extension</span></span>](#update-vs-code-qdk-extension)
   - <span data-ttu-id="aa350-214">在 VS Code 中，转到“视图” -> “命令面板” </span><span class="sxs-lookup"><span data-stu-id="aa350-214">In VS Code, go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="aa350-215">选择“Q#:安装命令行项目模板”</span><span class="sxs-lookup"><span data-stu-id="aa350-215">Select **Q#: Install command line project templates**</span></span>
   - <span data-ttu-id="aa350-216">几秒钟后，你应该会看到一个显示“项目模板已成功安装”确认消息的弹出窗口</span><span class="sxs-lookup"><span data-stu-id="aa350-216">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>
