---
title: 更新量程开发工具包（QDK）
description: '介绍如何将您的 Q # 项目和 Microsoft Quantum Development Kit 更新到最新版本。'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 3245f587493ce12cfec15c8f932fd092d85f688e
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327556"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="4a94b-103">更新 Microsoft Quantum Development Kit （QDK）</span><span class="sxs-lookup"><span data-stu-id="4a94b-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="4a94b-104">了解如何将 Microsoft Quantum Development Kit （QDK）更新到最新版本。</span><span class="sxs-lookup"><span data-stu-id="4a94b-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="4a94b-105">本文假设已安装 QDK。</span><span class="sxs-lookup"><span data-stu-id="4a94b-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="4a94b-106">如果你是首次安装，请参阅[安装指南](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="4a94b-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="4a94b-107">建议你随时了解最新的 QDK 版本。</span><span class="sxs-lookup"><span data-stu-id="4a94b-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="4a94b-108">按照此更新指南升级到最新的 QDK 版本。</span><span class="sxs-lookup"><span data-stu-id="4a94b-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="4a94b-109">此过程由两个部分组成：</span><span class="sxs-lookup"><span data-stu-id="4a94b-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="4a94b-110">更新现有的 Q # 文件和项目，以使代码与任何更新的语法对齐。</span><span class="sxs-lookup"><span data-stu-id="4a94b-110">Updating your existing Q# files and projects to align your code with any updated syntax.</span></span>
2. <span data-ttu-id="4a94b-111">为所选的开发环境更新 QDK 本身。</span><span class="sxs-lookup"><span data-stu-id="4a94b-111">Updating the QDK itself for your chosen development environment.</span></span>

## <a name="updating-q-projects"></a><span data-ttu-id="4a94b-112">更新 Q # 项目</span><span class="sxs-lookup"><span data-stu-id="4a94b-112">Updating Q# Projects</span></span> 

<span data-ttu-id="4a94b-113">无论使用 c # 还是 Python 来承载 Q # 操作，请按照以下说明更新 Q # 项目。</span><span class="sxs-lookup"><span data-stu-id="4a94b-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="4a94b-114">首先，请检查是否安装了最新版本的[.NET Core SDK 3.1](https://dotnet.microsoft.com/download)。</span><span class="sxs-lookup"><span data-stu-id="4a94b-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="4a94b-115">在命令提示符下运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="4a94b-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="4a94b-116">验证输出是否为 `3.1.100` 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="4a94b-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="4a94b-117">如果未安装，请安装[最新版本](https://dotnet.microsoft.com/download)，然后重新检查。</span><span class="sxs-lookup"><span data-stu-id="4a94b-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="4a94b-118">然后根据您的设置（Visual Studio、Visual Studio Code 或直接命令行），按照以下说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="4a94b-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="4a94b-119">在 Visual Studio 中更新 Q # 项目</span><span class="sxs-lookup"><span data-stu-id="4a94b-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="4a94b-120">更新到最新版本的 Visual Studio 2019，请参阅[此处](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019)了解说明。</span><span class="sxs-lookup"><span data-stu-id="4a94b-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions.</span></span>
2. <span data-ttu-id="4a94b-121">在 Visual Studio 中打开解决方案。</span><span class="sxs-lookup"><span data-stu-id="4a94b-121">Open your solution in Visual Studio.</span></span>
3. <span data-ttu-id="4a94b-122">从菜单中选择 "**生成**  ->  **干净解决方案**"。</span><span class="sxs-lookup"><span data-stu-id="4a94b-122">From the menu, select **Build** -> **Clean Solution**.</span></span>
4. <span data-ttu-id="4a94b-123">在每个 .csproj 文件中，将目标框架更新为 `netcoreapp3.1` （或者， `netstandard2.1` 如果它是库项目）。</span><span class="sxs-lookup"><span data-stu-id="4a94b-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="4a94b-124">也就是说，编辑以下格式的行：</span><span class="sxs-lookup"><span data-stu-id="4a94b-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="4a94b-125">可在[此处](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)找到有关指定目标框架的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4a94b-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

5. <span data-ttu-id="4a94b-126">在每个 .csproj 文件中，将 SDK 设置为 `Microsoft.Quantum.Sdk` ，如下面的行所示。</span><span class="sxs-lookup"><span data-stu-id="4a94b-126">In each of the .csproj files, set the SDK to `Microsoft.Quantum.Sdk`, as indicated in the line below.</span></span> <span data-ttu-id="4a94b-127">请注意，版本号应该是最新的，并且可以通过查看[发行说明](https://docs.microsoft.com/quantum/relnotes/)来确定。</span><span class="sxs-lookup"><span data-stu-id="4a94b-127">Please notice that the version number should be the latest available, and you can determine it by reviewing the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span>

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. <span data-ttu-id="4a94b-128">保存并关闭解决方案中的所有文件。</span><span class="sxs-lookup"><span data-stu-id="4a94b-128">Save and close all files in your solution.</span></span>

7. <span data-ttu-id="4a94b-129">选择**工具**  ->  **命令行**  ->  **开发人员命令提示**。</span><span class="sxs-lookup"><span data-stu-id="4a94b-129">Select **Tools** -> **Command Line** -> **Developer Command Prompt**.</span></span> <span data-ttu-id="4a94b-130">或者，你可以使用 Visual Studio 中的包管理控制台。</span><span class="sxs-lookup"><span data-stu-id="4a94b-130">Alternatively, you can use the package management console in Visual Studio.</span></span>

8. <span data-ttu-id="4a94b-131">对于解决方案中的每个项目，请运行以下命令来**删除**此包：</span><span class="sxs-lookup"><span data-stu-id="4a94b-131">For each project in the solution, run the following command to **remove** this package:</span></span>

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="4a94b-132">如果你的项目使用任何其他的 Microsoft 量子或. 量子包（例如，Microsoft 量子），请运行 "**添加**" 命令，以更新使用的版本。</span><span class="sxs-lookup"><span data-stu-id="4a94b-132">If your projects use any other Microsoft.Quantum or Microsoft.Azure.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the **add** command for these to update the version used.</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. <span data-ttu-id="4a94b-133">关闭命令提示符并选择 "**生成**  ->  **生成解决方案**" （*不*选择 "重新生成解决方案"）。</span><span class="sxs-lookup"><span data-stu-id="4a94b-133">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution).</span></span>

<span data-ttu-id="4a94b-134">你现在可以直接跳到[更新你的 Visual STUDIO QDK 扩展](#update-visual-studio-qdk-extension)。</span><span class="sxs-lookup"><span data-stu-id="4a94b-134">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="4a94b-135">更新 Visual Studio Code 中的 Q # 项目</span><span class="sxs-lookup"><span data-stu-id="4a94b-135">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="4a94b-136">在 Visual Studio Code 中，打开包含要更新的项目的文件夹。</span><span class="sxs-lookup"><span data-stu-id="4a94b-136">In Visual Studio Code, open the folder containing the project to update.</span></span>
2. <span data-ttu-id="4a94b-137">选择**终端**  ->  **新终端**。</span><span class="sxs-lookup"><span data-stu-id="4a94b-137">Select **Terminal** -> **New Terminal**.</span></span>
3. <span data-ttu-id="4a94b-138">按照使用命令行进行更新的说明进行操作（如下所示）。</span><span class="sxs-lookup"><span data-stu-id="4a94b-138">Follow the instructions for updating using the command line (directly below).</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="4a94b-139">使用命令行更新 Q # 项目</span><span class="sxs-lookup"><span data-stu-id="4a94b-139">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="4a94b-140">导航到包含主项目文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="4a94b-140">Navigate to the folder containing your main project file.</span></span>

2. <span data-ttu-id="4a94b-141">运行下面的命令：</span><span class="sxs-lookup"><span data-stu-id="4a94b-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="4a94b-142">确定 QDK 的当前版本。</span><span class="sxs-lookup"><span data-stu-id="4a94b-142">Determine the current version of the QDK.</span></span> <span data-ttu-id="4a94b-143">若要找到它，可以查看[发行说明](https://docs.microsoft.com/quantum/relnotes/)。</span><span class="sxs-lookup"><span data-stu-id="4a94b-143">To find it, you can review the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span> <span data-ttu-id="4a94b-144">版本的格式类似于 `0.11.2006.207` 。</span><span class="sxs-lookup"><span data-stu-id="4a94b-144">The version will be in a format similar to `0.11.2006.207`.</span></span>

4. <span data-ttu-id="4a94b-145">在每个 `.csproj` 文件中，完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="4a94b-145">In each of your `.csproj` files, go through the following steps:</span></span>

    - <span data-ttu-id="4a94b-146">将目标框架更新为 `netcoreapp3.1` （或者， `netstandard2.1` 如果它是库项目）。</span><span class="sxs-lookup"><span data-stu-id="4a94b-146">Update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span> <span data-ttu-id="4a94b-147">也就是说，编辑以下格式的行：</span><span class="sxs-lookup"><span data-stu-id="4a94b-147">That is, edit lines of the form:</span></span>

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        <span data-ttu-id="4a94b-148">可在[此处](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)找到有关指定目标框架的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4a94b-148">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

    - <span data-ttu-id="4a94b-149">将引用替换为项目定义中的 SDK。</span><span class="sxs-lookup"><span data-stu-id="4a94b-149">Replace the reference to the SDK in the project definition.</span></span> <span data-ttu-id="4a94b-150">请确保版本号与**步骤 3**中确定的值相对应。</span><span class="sxs-lookup"><span data-stu-id="4a94b-150">Make sure that the version number corresponds to the value determined in **step 3**.</span></span>

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - <span data-ttu-id="4a94b-151">删除对包的引用 `Microsoft.Quantum.Development.Kit` （如果存在），此引用将在以下条目中指定：</span><span class="sxs-lookup"><span data-stu-id="4a94b-151">Remove the reference to package `Microsoft.Quantum.Development.Kit` if present, which will be specified in the following entry:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - <span data-ttu-id="4a94b-152">将所有 Microsoft 量程包的版本更新到最近发布的 QDK 版本（在**步骤 3**中确定）。</span><span class="sxs-lookup"><span data-stu-id="4a94b-152">Update the version of the all the Microsoft Quantum packages to the most recently released version of the QDK (determined in **step 3**).</span></span> <span data-ttu-id="4a94b-153">这些包的命名方式如下：</span><span class="sxs-lookup"><span data-stu-id="4a94b-153">Those packages are named with the following patterns:</span></span>

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        <span data-ttu-id="4a94b-154">对包的引用具有以下格式：</span><span class="sxs-lookup"><span data-stu-id="4a94b-154">References to packages have the following format:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - <span data-ttu-id="4a94b-155">保存更新的文件。</span><span class="sxs-lookup"><span data-stu-id="4a94b-155">Save the updated file.</span></span>

    - <span data-ttu-id="4a94b-156">通过执行以下操作还原项目的依赖项：</span><span class="sxs-lookup"><span data-stu-id="4a94b-156">Restore the dependencies of the project, by doing the following:</span></span>

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. <span data-ttu-id="4a94b-157">导航回包含主项目的文件夹，然后运行：</span><span class="sxs-lookup"><span data-stu-id="4a94b-157">Navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="4a94b-158">现在，你的 Q # 项目已更新，请按照下面的说明更新 QDK 本身。</span><span class="sxs-lookup"><span data-stu-id="4a94b-158">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="4a94b-159">更新 QDK</span><span class="sxs-lookup"><span data-stu-id="4a94b-159">Updating the QDK</span></span>

<span data-ttu-id="4a94b-160">更新 QDK 的过程因开发语言和环境而异。</span><span class="sxs-lookup"><span data-stu-id="4a94b-160">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="4a94b-161">选择下面的开发环境。</span><span class="sxs-lookup"><span data-stu-id="4a94b-161">Select your development environment below.</span></span>

* [<span data-ttu-id="4a94b-162">Python：更新 IQ # 扩展</span><span class="sxs-lookup"><span data-stu-id="4a94b-162">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="4a94b-163">Jupyter 笔记本：更新 IQ # 扩展</span><span class="sxs-lookup"><span data-stu-id="4a94b-163">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="4a94b-164">Visual Studio：更新 QDK 扩展</span><span class="sxs-lookup"><span data-stu-id="4a94b-164">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="4a94b-165">VS Code：更新 QDK 扩展</span><span class="sxs-lookup"><span data-stu-id="4a94b-165">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="4a94b-166">命令行和 c #：更新项目模板</span><span class="sxs-lookup"><span data-stu-id="4a94b-166">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="4a94b-167">更新适用于 Python 的 IQ #</span><span class="sxs-lookup"><span data-stu-id="4a94b-167">Update IQ# for Python</span></span>

1. <span data-ttu-id="4a94b-168">更新 `iqsharp` 内核</span><span class="sxs-lookup"><span data-stu-id="4a94b-168">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="4a94b-169">验证 `iqsharp` 版本</span><span class="sxs-lookup"><span data-stu-id="4a94b-169">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="4a94b-170">应该会看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="4a94b-170">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="4a94b-171">请不要担心 `iqsharp` 版本是否较高，它应与[最新版本](xref:microsoft.quantum.relnotes)相匹配。</span><span class="sxs-lookup"><span data-stu-id="4a94b-171">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="4a94b-172">更新 `qsharp` 包</span><span class="sxs-lookup"><span data-stu-id="4a94b-172">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="4a94b-173">验证 `qsharp` 版本</span><span class="sxs-lookup"><span data-stu-id="4a94b-173">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="4a94b-174">应该会看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="4a94b-174">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="4a94b-175">从文件的位置运行以下命令 `.qs`</span><span class="sxs-lookup"><span data-stu-id="4a94b-175">Run the following command from the location of your `.qs` files</span></span>

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="4a94b-176">你现在可以使用更新的 QDK 版本来运行现有的量程程序。</span><span class="sxs-lookup"><span data-stu-id="4a94b-176">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="4a94b-177">更新适用于 Jupyter 笔记本的 IQ #</span><span class="sxs-lookup"><span data-stu-id="4a94b-177">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="4a94b-178">更新 `iqsharp` 内核</span><span class="sxs-lookup"><span data-stu-id="4a94b-178">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="4a94b-179">验证 `iqsharp` 版本</span><span class="sxs-lookup"><span data-stu-id="4a94b-179">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="4a94b-180">输出应类似如下所示：</span><span class="sxs-lookup"><span data-stu-id="4a94b-180">Your output should be similar to the following:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="4a94b-181">请不要担心 `iqsharp` 版本是否较高，它应与[最新版本](xref:microsoft.quantum.relnotes)相匹配。</span><span class="sxs-lookup"><span data-stu-id="4a94b-181">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="4a94b-182">在 Jupyter Notebook 中的单元格上运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="4a94b-182">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="4a94b-183">你现在可以打开现有的 Jupyter 笔记本，并使用更新的 QDK 运行它。</span><span class="sxs-lookup"><span data-stu-id="4a94b-183">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="4a94b-184">更新 Visual Studio QDK 扩展</span><span class="sxs-lookup"><span data-stu-id="4a94b-184">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="4a94b-185">更新 Q # Visual Studio 扩展</span><span class="sxs-lookup"><span data-stu-id="4a94b-185">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="4a94b-186">Visual Studio 会提示你接受对[量程 Visual Studio 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)的更新</span><span class="sxs-lookup"><span data-stu-id="4a94b-186">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="4a94b-187">接受更新</span><span class="sxs-lookup"><span data-stu-id="4a94b-187">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="4a94b-188">项目模板将更新为扩展。</span><span class="sxs-lookup"><span data-stu-id="4a94b-188">The project templates are updated with the extension.</span></span> <span data-ttu-id="4a94b-189">更新的模板仅适用于新创建的项目。</span><span class="sxs-lookup"><span data-stu-id="4a94b-189">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="4a94b-190">更新扩展时，不会更新现有项目的代码。</span><span class="sxs-lookup"><span data-stu-id="4a94b-190">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="4a94b-191">更新 VS Code QDK 扩展</span><span class="sxs-lookup"><span data-stu-id="4a94b-191">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="4a94b-192">更新量程 VS Code 扩展</span><span class="sxs-lookup"><span data-stu-id="4a94b-192">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="4a94b-193">重新启动 VS Code</span><span class="sxs-lookup"><span data-stu-id="4a94b-193">Restart VS Code</span></span>
    - <span data-ttu-id="4a94b-194">导航到 "**扩展**" 选项卡</span><span class="sxs-lookup"><span data-stu-id="4a94b-194">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="4a94b-195">选择 Visual Studio Code 扩展的**Microsoft Quantum Development Kit**</span><span class="sxs-lookup"><span data-stu-id="4a94b-195">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="4a94b-196">重新加载扩展</span><span class="sxs-lookup"><span data-stu-id="4a94b-196">Reload the extension</span></span>

2. <span data-ttu-id="4a94b-197">更新量程项目模板：</span><span class="sxs-lookup"><span data-stu-id="4a94b-197">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="4a94b-198">中转到 "**视图**"  ->  **命令面板**</span><span class="sxs-lookup"><span data-stu-id="4a94b-198">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="4a94b-199">选择**Q #：安装项目模板**</span><span class="sxs-lookup"><span data-stu-id="4a94b-199">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="4a94b-200">几秒钟后，你应该会看到一个弹出窗口，确认 "项目模板已成功安装"</span><span class="sxs-lookup"><span data-stu-id="4a94b-200">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="4a94b-201">C #，使用 `dotnet` 命令行工具</span><span class="sxs-lookup"><span data-stu-id="4a94b-201">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="4a94b-202">更新 .NET 的量程项目模板</span><span class="sxs-lookup"><span data-stu-id="4a94b-202">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
