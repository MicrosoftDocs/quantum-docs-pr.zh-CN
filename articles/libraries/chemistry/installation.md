---
title: 化学库安装和验证 |Microsoft Docs
description: 化学库安装和验证
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: fd43c783fa82c7219e143a57759919606fdd197f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184196"
---
# <a name="chemistry-library-installation-and-validation"></a><span data-ttu-id="90394-103">化学库安装和验证</span><span class="sxs-lookup"><span data-stu-id="90394-103">Chemistry Library Installation and Validation</span></span>

<span data-ttu-id="90394-104">量程开发工具包通过[`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) NuGet 包提供对量程化学应用程序的支持。</span><span class="sxs-lookup"><span data-stu-id="90394-104">The Quantum Development Kit provides support for quantum chemistry applications through the [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) NuGet package.</span></span>
<span data-ttu-id="90394-105">与其他 NuGet 包一样，可以直接将化学库添加到项目。</span><span class="sxs-lookup"><span data-stu-id="90394-105">As with other NuGet packages, it's straightforward to add the chemistry library to your project.</span></span>

<span data-ttu-id="90394-106">**Visual Studio 2019：** 如果使用的是 Visual Studio 2019，则可以使用 NuGet 包管理器添加量程化学包。</span><span class="sxs-lookup"><span data-stu-id="90394-106">**Visual Studio 2019:** If you are using Visual Studio 2019, you can add the quantum chemistry packages by using the NuGet Package Manager.</span></span>
<span data-ttu-id="90394-107">若要打开程序包管理器，请右键单击要向其添加化学库的项目，然后选择 "管理 NuGet 包 ..."，如下面的屏幕截图所示。</span><span class="sxs-lookup"><span data-stu-id="90394-107">To open the Package Manager, right-click on the project you'd like to add the chemistry library to and select "Manage NuGet Packages...," as in the screenshot below.</span></span>

![](~/media/vs2017-nuget-manage-packages.png)

<span data-ttu-id="90394-108">从 "浏览" 选项卡中，搜索包名称 ""。</span><span class="sxs-lookup"><span data-stu-id="90394-108">From the Browse tab, search for the package name "Microsoft.Quantum.Chemistry."</span></span>

> [!NOTE]
> <span data-ttu-id="90394-109">请确保 "包括预发行版"。</span><span class="sxs-lookup"><span data-stu-id="90394-109">Make sure to tick "Include prerelease."</span></span>

![](~/media/vs2017-nuget-package-search.png)

<span data-ttu-id="90394-110">这将列出可供下载的包。</span><span class="sxs-lookup"><span data-stu-id="90394-110">This will list the packages available for download.</span></span>
<span data-ttu-id="90394-111">单击左侧窗格中的 ""，然后在右侧窗格中选择最新的预发行版本，然后单击 "安装"：</span><span class="sxs-lookup"><span data-stu-id="90394-111">Click on the "Microsoft.Quantum.Chemistry on the left-hand pane, select the latest pre-release version on the right-hand pane, and click "Install":</span></span>

![](~/media/vs2017-nuget-select-chem.png)

<span data-ttu-id="90394-112">有关更多详细信息，请参阅[包管理器 UI 指南](https://docs.microsoft.com/nuget/tools/package-manager-ui)。</span><span class="sxs-lookup"><span data-stu-id="90394-112">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="90394-113">或者，你可以使用包管理器控制台，使用命令行接口将量程化学库添加到你的项目中。</span><span class="sxs-lookup"><span data-stu-id="90394-113">Alternatively, you can use the Package Manager Console to add the quantum chemistry library to your project with a command line interface.</span></span>

![](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="90394-114">从包管理器控制台中，运行以下内容：</span><span class="sxs-lookup"><span data-stu-id="90394-114">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Chemistry
```

<span data-ttu-id="90394-115">有关更多详细信息，请参阅[包管理器控制台指南](https://docs.microsoft.com/nuget/tools/package-manager-console)。</span><span class="sxs-lookup"><span data-stu-id="90394-115">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="90394-116">**命令行或 Visual Studio Code：** 你可以使用命令行自己使用命令行，也可以从 Visual Studio Code 中，使用 `dotnet` 命令将 NuGet 包引用添加到你的项目：</span><span class="sxs-lookup"><span data-stu-id="90394-116">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```bash
dotnet add package Microsoft.Quantum.Chemistry
```

## <a name="verifying-your-installation"></a><span data-ttu-id="90394-117">验证安装</span><span class="sxs-lookup"><span data-stu-id="90394-117">Verifying Your Installation</span></span> 

<span data-ttu-id="90394-118">与量程开发工具包的其余部分一样，量程化学库附带了多个完整记录的示例，可帮助你快速启动和运行。</span><span class="sxs-lookup"><span data-stu-id="90394-118">Like the rest of the Quantum Development Kit, the quantum chemistry library comes with a number of fully documented samples to help you get up and running quickly.</span></span>
<span data-ttu-id="90394-119">若要使用这些示例测试安装，请克隆[主示例存储库](https://github.com/Microsoft/Quantum)，然后运行其中一个示例。</span><span class="sxs-lookup"><span data-stu-id="90394-119">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum), then run one of the samples.</span></span>  <span data-ttu-id="90394-120">例如，若要运行[`MolecularHydrogen`](https://github.com/Microsoft/Quantum/tree/master/Chemistry/MolecularHydrogen)示例：</span><span class="sxs-lookup"><span data-stu-id="90394-120">For example, to run the [`MolecularHydrogen`](https://github.com/Microsoft/Quantum/tree/master/Chemistry/MolecularHydrogen) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Chemistry/MolecularHydrogen
dotnet run
```

<span data-ttu-id="90394-121">若要在克隆存储库后使用 Microsoft Visual Studio 验证量程化学库的安装，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="90394-121">To verify the installation of the quantum chemistry library using Microsoft Visual Studio after cloning the repository:</span></span>
    1. <span data-ttu-id="90394-122">在化学文件夹中打开 ChemistrySamples 解决方案。</span><span class="sxs-lookup"><span data-stu-id="90394-122">Open the ChemistrySamples.sln solution in the Chemistry folder.</span></span>  
    2. <span data-ttu-id="90394-123">选择 "示例/1"。</span><span class="sxs-lookup"><span data-stu-id="90394-123">Select Samples/1.</span></span> <span data-ttu-id="90394-124">简单分子/MolecularHydrogen 作为启动项目。</span><span class="sxs-lookup"><span data-stu-id="90394-124">Simple Molecules/MolecularHydrogen as the StartUp project.</span></span>
    3. <span data-ttu-id="90394-125">按 F5 运行分子 Hydrogen 量程阶段估算演示。</span><span class="sxs-lookup"><span data-stu-id="90394-125">Press F5 to run the molecular Hydrogen quantum phase estimation demo.</span></span>

<span data-ttu-id="90394-126">有关估计能源水平值的详细信息，请参阅[获取能源水平估算](xref:microsoft.quantum.chemistry.examples.energyestimate)。</span><span class="sxs-lookup"><span data-stu-id="90394-126">See [Obtaining energy level estimates](xref:microsoft.quantum.chemistry.examples.energyestimate) for more information on estimating the values of energy levels.</span></span>   


## <a name="using-the-quantum-development-kit-with-nwchem"></a><span data-ttu-id="90394-127">将量程开发工具包与 NWChem 配合使用</span><span class="sxs-lookup"><span data-stu-id="90394-127">Using the Quantum Development Kit with NWChem</span></span> ##

<span data-ttu-id="90394-128">MolecularHydrogen 示例使用手动配置的分子输入数据。</span><span class="sxs-lookup"><span data-stu-id="90394-128">The MolecularHydrogen sample uses molecular input data that is manually configured.</span></span>  <span data-ttu-id="90394-129">虽然这对小型示例而言很不错，但大规模的量程化学要求 Hamiltonians 或数十亿。</span><span class="sxs-lookup"><span data-stu-id="90394-129">While this is fine for small examples, quantum chemistry at scale require Hamiltonians with millions or billions of terms.</span></span> <span data-ttu-id="90394-130">可缩放的计算化学包生成的此类 Hamiltonians 太大，无法手动导入。</span><span class="sxs-lookup"><span data-stu-id="90394-130">Such Hamiltonians, generated by scalable computational chemistry packages are too large to import by hand.</span></span> 

<span data-ttu-id="90394-131">量程开发工具包的量程化学库旨在与计算化学包一起正常工作，最值得注意的是，环境分子科学实验室开发的[**NWChem**](http://www.nwchem-sw.org/)计算化学平台（EMSL）。</span><span class="sxs-lookup"><span data-stu-id="90394-131">The quantum chemistry library for the Quantum Development Kit is designed to work well with computational chemistry packages, most notably the [**NWChem**](http://www.nwchem-sw.org/) computational chemistry platform developed by the Environmental Molecular Sciences Laboratory (EMSL) at Pacific Northwest National Laboratory.</span></span>
<span data-ttu-id="90394-132">具体而言，`Microsoft.Quantum.Chemistry` 包提供的工具可用于加载在[Broombridge 架构](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)中表示的量程化学模拟问题的实例，还支持 NWChem 最新版本的导出。</span><span class="sxs-lookup"><span data-stu-id="90394-132">In particular, the `Microsoft.Quantum.Chemistry` package provides tools for loading instances of quantum chemistry simulation problems represented in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), also supported for export by recent versions of NWChem.</span></span>

<span data-ttu-id="90394-133">若要将 NWChem 与量程开发工具包一起使用，我们建议使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="90394-133">To get up and running using NWChem together with the Quantum Development Kit, we suggest one of the following methods:</span></span>
- <span data-ttu-id="90394-134">开始使用在[IntegralData/YAML](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML)的示例中提供的现有 Broombridge 文件。</span><span class="sxs-lookup"><span data-stu-id="90394-134">Get started using existing Broombridge files provided with the samples at [IntegralData/YAML](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML).</span></span>
- <span data-ttu-id="90394-135">将[EMSL 箭头生成器用于](https://arrows.emsl.pnnl.gov/api/qsharp_chem)作为基于 web 的前端到 NWChem 的 Microsoft Quantum Development Kit，以生成新的 Broombridge 格式化分子输入文件。</span><span class="sxs-lookup"><span data-stu-id="90394-135">Use the [EMSL Arrows Builder for the Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) which is a web-based frontend to NWChem, to generate new Broombridge-formated molecular input files.</span></span>  
- <span data-ttu-id="90394-136">使用 PNNL 提供的[Docker 映像](https://hub.docker.com/r/nwchemorg/nwchem-qc/)运行 NWChem，或</span><span class="sxs-lookup"><span data-stu-id="90394-136">Use the [Docker image](https://hub.docker.com/r/nwchemorg/nwchem-qc/) provided by PNNL to run NWChem, or</span></span>
- <span data-ttu-id="90394-137">[编译](http://www.nwchem-sw.org/index.php/Compiling_NWChem)平台的 NWChem。</span><span class="sxs-lookup"><span data-stu-id="90394-137">[Compile NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) for your platform.</span></span>

<span data-ttu-id="90394-138">请参阅[使用 NWChem 的端到端](xref:microsoft.quantum.chemistry.examples.endtoend)的详细信息，了解有关如何使用 NWChem 到化学模型的详细信息，以使用量程开发套件化学库进行分析。</span><span class="sxs-lookup"><span data-stu-id="90394-138">See [End-to-end with NWChem](xref:microsoft.quantum.chemistry.examples.endtoend) for more information on how to work with NWChem to chemical models to analyze with the Quantum Developmen Kit chemistry library.</span></span>

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a><span data-ttu-id="90394-139">使用示例提供的 Broombridge 文件入门</span><span class="sxs-lookup"><span data-stu-id="90394-139">Getting started using Broombridge files provided with the samples</span></span>
<span data-ttu-id="90394-140">量程开发工具包示例存储库中的[IntegralData/YAML](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML)文件夹包含 Broombridge 格式化的分子数据文件。</span><span class="sxs-lookup"><span data-stu-id="90394-140">The [IntegralData/YAML](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML) folder in the Quantum Development Kit Samples repository contains Broombridge-formated molecule data files.</span></span>  

<span data-ttu-id="90394-141">作为一个简单的示例，请使用化学 library 示例， [GetGateCount](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount)从 Broombridge 文件之一加载 Hamiltonian，并执行量程模拟 algorigthms 的入口估计：</span><span class="sxs-lookup"><span data-stu-id="90394-141">As a simple example, use the chemistry library sample, [GetGateCount](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount) to load the Hamiltonian from one of Broombridge files and perform gate estimates of quantum simulation algorigthms:</span></span>

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

<span data-ttu-id="90394-142">有关如何输入 Broombridge 架构表示的分子的详细信息，请参阅[从文件加载 Hamiltonian](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) 。</span><span class="sxs-lookup"><span data-stu-id="90394-142">See [Loading a Hamiltonian from file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) for more information on how to input molecules represented by the Broombridge schema.</span></span>  

<span data-ttu-id="90394-143">有关资源估计的详细信息，请参阅[获取资源计数](xref:microsoft.quantum.chemistry.examples.resourcecounts)。</span><span class="sxs-lookup"><span data-stu-id="90394-143">See [Obtaining resource counts](xref:microsoft.quantum.chemistry.examples.resourcecounts) for more information on resource estimation.</span></span>  

### <a name="getting-started-using-the-emsl-arrows-builder"></a><span data-ttu-id="90394-144">开始使用 EMSL 箭头生成器</span><span class="sxs-lookup"><span data-stu-id="90394-144">Getting started using the EMSL Arrows Builder</span></span>

<span data-ttu-id="90394-145">EMSL 箭头是一种使用 NWChem 和化学计算数据库生成分子数据的工具。</span><span class="sxs-lookup"><span data-stu-id="90394-145">EMSL Arrows is a tool that uses NWChem and chemical computational databases to generate molecule data.</span></span>  <span data-ttu-id="90394-146">使用[Microsoft Quantum Development Kit 的 EMSL 箭头生成器](https://arrows.emsl.pnnl.gov/api/qsharp_chem)，可以使用多个分子模型生成器输入模型，并生成将由量子开发工具包使用的 Broombridge 数据文件。</span><span class="sxs-lookup"><span data-stu-id="90394-146">[EMSL Arrows Builder for the Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) allows you to enter your model using multiple molecular model builders and generate the Broombridge datafile to be used by the Quantum Development Kit.</span></span>  

<span data-ttu-id="90394-147">从 "EMSL" 页上，单击 [' China '] 选项卡，然后按照 [' 简单示例 '] 说明生成 Broombridge 文件。</span><span class="sxs-lookup"><span data-stu-id="90394-147">From the EMSL page, click on the ['Instuctions'] tab, and follow the ['Simple Examples'] instructions to generate Broombridge files.</span></span>  <span data-ttu-id="90394-148">然后尝试运行 [' GetGateCount ']，查看这些分子的量程资源估算值。</span><span class="sxs-lookup"><span data-stu-id="90394-148">Then try running the ['GetGateCount'] to see the quantum resource estimates for these molecules.</span></span>

### <a name="installing-nwchem-from-source"></a><span data-ttu-id="90394-149">从源安装 NWChem</span><span class="sxs-lookup"><span data-stu-id="90394-149">Installing NWChem from Source</span></span>

<span data-ttu-id="90394-150">[PNNL 提供](http://www.nwchem-sw.org/index.php/Compiling_NWChem)了有关如何从源安装 NWChem 的完整说明。</span><span class="sxs-lookup"><span data-stu-id="90394-150">Full instructions on how to install NWChem from source [are provided by PNNL](http://www.nwchem-sw.org/index.php/Compiling_NWChem).</span></span>

> [!TIP]
> <span data-ttu-id="90394-151">如果要从 Windows 10 使用 NWChem，适用于 Linux 的 Windows 子系统是一个不错的选择。</span><span class="sxs-lookup"><span data-stu-id="90394-151">If you wish to use NWChem from Windows 10, the Windows Subsystem for Linux is a great option.</span></span>
> <span data-ttu-id="90394-152">安装[Ubuntu 18.04 LTS For Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab)后，请从喜欢的终端运行 `ubuntu18.04`，并按照上述说明从 "源" 安装 NWChem。</span><span class="sxs-lookup"><span data-stu-id="90394-152">Once you have installed [Ubuntu 18.04 LTS for Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab), run `ubuntu18.04` from your favorite terminal and follow the instructions above to install NWChem from source.</span></span>

<span data-ttu-id="90394-153">从源中编译 NWChem 后，可以运行与 NWChem 一起提供的 `yaml_driver` 脚本，通过 NWChem 输入卡座快速生成 Broombridge 实例：</span><span class="sxs-lookup"><span data-stu-id="90394-153">Once you have compiled NWChem from source, you can run the `yaml_driver` script provided with NWChem to quickly produce Broombridge instances from NWChem input decks:</span></span>

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

<span data-ttu-id="90394-154">此命令将在当前目录中创建 Broombridge 格式的新的 `input.yaml` 文件。</span><span class="sxs-lookup"><span data-stu-id="90394-154">This command will create a new `input.yaml` file in the Broombridge format within your current directory.</span></span>

### <a name="using-nwchem-with-docker"></a><span data-ttu-id="90394-155">结合使用 NWChem 和 Docker</span><span class="sxs-lookup"><span data-stu-id="90394-155">Using NWChem with Docker</span></span>

<span data-ttu-id="90394-156">使用 NWChem 的预构建映像可通过[Docker 中心](https://hub.docker.com)跨平台使用。</span><span class="sxs-lookup"><span data-stu-id="90394-156">Pre-built images for using NWChem are available cross-platform via [Docker Hub](https://hub.docker.com).</span></span>
<span data-ttu-id="90394-157">若要开始，请遵循适用于你的平台的 Docker 安装说明：</span><span class="sxs-lookup"><span data-stu-id="90394-157">To get started, follow the Docker installation instructions for your platform:</span></span>

- [<span data-ttu-id="90394-158">安装 Docker for Ubuntu</span><span class="sxs-lookup"><span data-stu-id="90394-158">Install Docker for Ubuntu</span></span>](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [<span data-ttu-id="90394-159">安装适用于 macOS 的 Docker</span><span class="sxs-lookup"><span data-stu-id="90394-159">Install Docker for macOS</span></span>](https://docs.docker.com/docker-for-mac/install/)
- [<span data-ttu-id="90394-160">安装用于 Windows 的 Docker 10</span><span class="sxs-lookup"><span data-stu-id="90394-160">Install Docker for Windows 10</span></span>](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> <span data-ttu-id="90394-161">如果使用用于 Windows 的 Docker，则需要使用 Docker 守护程序共享包含临时目录的驱动器（通常是 `C:\` 驱动器）。</span><span class="sxs-lookup"><span data-stu-id="90394-161">If you are using Docker for Windows, you will need to share the drive containing your temporary directory (usually this is the `C:\` drive) with the Docker daemon.</span></span> <span data-ttu-id="90394-162">有关更多详细信息，请参阅[Docker 文档](https://docs.docker.com/docker-for-windows/#shared-drives)。</span><span class="sxs-lookup"><span data-stu-id="90394-162">See the [Docker documentation](https://docs.docker.com/docker-for-windows/#shared-drives) for more details.</span></span>

<span data-ttu-id="90394-163">安装 Docker 后，可以使用随量程开发工具包示例提供的 PowerShell 模块来运行映像，也可以手动运行映像。</span><span class="sxs-lookup"><span data-stu-id="90394-163">Once you have Docker installed, you can either use the PowerShell module provided with the Quantum Development Kit samples to run the image, or you can run the image manually.</span></span>
<span data-ttu-id="90394-164">此处是使用 PowerShell 的详细信息;如果希望手动使用 Docker 映像，请参阅[随图像提供的文档](https://hub.docker.com/r/nwchemorg/nwchem-qc/)。</span><span class="sxs-lookup"><span data-stu-id="90394-164">We detail using PowerShell here; if you would like to use the Docker image manually, please see the [documentation provided with the image](https://hub.docker.com/r/nwchemorg/nwchem-qc/).</span></span>

#### <a name="running-nwchem-through-powershell-core"></a><span data-ttu-id="90394-165">通过 PowerShell Core 运行 NWChem</span><span class="sxs-lookup"><span data-stu-id="90394-165">Running NWChem through PowerShell Core</span></span>

<span data-ttu-id="90394-166">若要将 NWChem Docker 映像与量程开发工具包一起使用，我们提供了一个小型 PowerShell 模块，用于处理将文件移入和移出 NWChem 的情况。</span><span class="sxs-lookup"><span data-stu-id="90394-166">To use the NWChem Docker image with the Quantum Development Kit, we provide a small PowerShell module that handles moving files in and out of NWChem for you.</span></span>
<span data-ttu-id="90394-167">如果尚未安装 PowerShell Core，则可以从[GitHub 上的 powershell 存储库](https://github.com/PowerShell/PowerShell#get-powershell)跨平台下载。</span><span class="sxs-lookup"><span data-stu-id="90394-167">If you don't already have PowerShell Core installed, you can download it cross-platform from the [PowerShell repository on GitHub](https://github.com/PowerShell/PowerShell#get-powershell).</span></span>

> [!NOTE]
> <span data-ttu-id="90394-168">PowerShell Core 还适用于一些示例，用于演示与数据科学和业务分析工作流的互操作性。</span><span class="sxs-lookup"><span data-stu-id="90394-168">PowerShell Core is also used for some samples to demonstrate interoperability with data science and business analytics workflows.</span></span>

<span data-ttu-id="90394-169">安装 PowerShell Core 后，导入 `InvokeNWChem.psm1` 以使 NWChem 命令在当前会话中可用：</span><span class="sxs-lookup"><span data-stu-id="90394-169">Once you have PowerShell Core installed, import `InvokeNWChem.psm1` to make NWChem commands available in your current session:</span></span>

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

<span data-ttu-id="90394-170">这会使 `Convert-NWChemToBroombridge` 命令在当前 PowerShell 会话中可用。</span><span class="sxs-lookup"><span data-stu-id="90394-170">This will make the `Convert-NWChemToBroombridge` command available in your current PowerShell session.</span></span>
<span data-ttu-id="90394-171">若要从 Docker 下载任何所需的映像并将其用于运行 NWChem input 卡座并将输出捕获到 Broombridge，请运行以下内容：</span><span class="sxs-lookup"><span data-stu-id="90394-171">To download any needed images from Docker and use them to run NWChem input decks and capture output to Broombridge, run the following:</span></span>

```powershell
Convert-NWChemToBroombridge ./input.nw
```

<span data-ttu-id="90394-172">这将通过在 `input.nw`上运行 NWChem 来创建 Broombridge 文件。</span><span class="sxs-lookup"><span data-stu-id="90394-172">This will create a Broombridge file by running NWChem on `input.nw`.</span></span>
<span data-ttu-id="90394-173">默认情况下，Broombridge 输出将与输入纸盒具有相同的名称和路径，并且 `.nw` 扩展将替换为 `.yaml`。</span><span class="sxs-lookup"><span data-stu-id="90394-173">By default, the Broombridge output will have the same name and path as the input deck, with the `.nw` extension replaced by `.yaml`.</span></span>
<span data-ttu-id="90394-174">这可以通过使用 `Convert-NWChemToBroombridge`的 `-DestinationPath` 参数重写。</span><span class="sxs-lookup"><span data-stu-id="90394-174">This can be overridden by using the `-DestinationPath` parameter to `Convert-NWChemToBroombridge`.</span></span>
<span data-ttu-id="90394-175">可以使用 PowerShell 的内置帮助功能获取详细信息：</span><span class="sxs-lookup"><span data-stu-id="90394-175">More information can be obtained by using PowerShell's built-in help functionality:</span></span>

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```


