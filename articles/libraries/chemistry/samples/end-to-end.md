---
title: 具有 NWChem 的端到端 |Microsoft Docs
description: NWChem 文档的端到端
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/23/2018
uid: microsoft.quantum.chemistry.examples.endtoend
ms.openlocfilehash: 8f727ea4599e06b41ced561c624c4e773b9887d9
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185811"
---
# <a name="end-to-end-with-nwchem"></a><span data-ttu-id="256af-103">NWChem 的端到端</span><span class="sxs-lookup"><span data-stu-id="256af-103">End-to-end with NWChem</span></span> #

<span data-ttu-id="256af-104">在本页面中，我们将逐步介绍如何从[NWChem](http://www.nwchem-sw.org/index.php/Main_Page)的输入牌中获取量程化学模拟的入口计数。</span><span class="sxs-lookup"><span data-stu-id="256af-104">In this page, we will walk through an example of getting gate counts for quantum chemistry simulation, starting from an [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) input deck.</span></span>
<span data-ttu-id="256af-105">在继续此示例之前，请确保已按照[安装和验证指南](xref:microsoft.quantum.chemistry.concepts.installation)安装了 Docker。</span><span class="sxs-lookup"><span data-stu-id="256af-105">Before proceeding with this example, make sure that you've installed Docker, following the [installation and validation guide](xref:microsoft.quantum.chemistry.concepts.installation).</span></span>

<span data-ttu-id="256af-106">有关详细信息：</span><span class="sxs-lookup"><span data-stu-id="256af-106">For more information:</span></span>
- [<span data-ttu-id="256af-107">NWChem 输入卡座的结构</span><span class="sxs-lookup"><span data-stu-id="256af-107">Structure of NWChem input decks</span></span>](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [<span data-ttu-id="256af-108">用于量程开发工具包的输入纸牌命令</span><span class="sxs-lookup"><span data-stu-id="256af-108">Input deck commands for use with the Quantum Development Kit</span></span>](https://github.com/nwchemgit/nwchem/tree/master/contrib/quasar)
- [<span data-ttu-id="256af-109">安装化学库和依赖项</span><span class="sxs-lookup"><span data-stu-id="256af-109">Installing the chemistry library and dependencies</span></span>](xref:microsoft.quantum.chemistry.concepts.installation)
- [<span data-ttu-id="256af-110">资源计数</span><span class="sxs-lookup"><span data-stu-id="256af-110">Resource counting</span></span>](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> <span data-ttu-id="256af-111">此示例需要运行 Windows PowerShell Core。</span><span class="sxs-lookup"><span data-stu-id="256af-111">This example requires Windows PowerShell Core to run.</span></span>
> <span data-ttu-id="256af-112">https://github.com/PowerShell/PowerShell 下载适用于 Windows、macOS 或 Linux 的 PowerShell Core。</span><span class="sxs-lookup"><span data-stu-id="256af-112">Download PowerShell Core for Windows, macOS, or Linux at https://github.com/PowerShell/PowerShell.</span></span>

## <a name="importing-required-powershell-modules"></a><span data-ttu-id="256af-113">导入所需的 PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="256af-113">Importing Required PowerShell Modules</span></span> ##

<span data-ttu-id="256af-114">如果尚未这样做，请克隆[Microsoft/量子存储库](https://github.com/Microsoft/Quantum)，其中包含用于处理量程开发工具包的示例和实用程序：</span><span class="sxs-lookup"><span data-stu-id="256af-114">If you haven't already done so, clone the [Microsoft/Quantum repository](https://github.com/Microsoft/Quantum), which contains samples and utilities for working with the Quantum Development Kit:</span></span>

```powershell
git clone https://github.com/Microsoft/Quantum
```

<span data-ttu-id="256af-115">克隆 `Microsoft/Quantum`后，请在 `utilities/` 文件夹中执行 `cd`，并导入 PowerShell 模块以便使用 Docker 和 NWChem：</span><span class="sxs-lookup"><span data-stu-id="256af-115">Once you've cloned `Microsoft/Quantum`, perform `cd` into the `utilities/` folder and import the PowerShell module for working with Docker and NWChem:</span></span>

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> <span data-ttu-id="256af-116">默认情况下，Windows 会阻止执行任何脚本或模块作为安全措施。</span><span class="sxs-lookup"><span data-stu-id="256af-116">By default, Windows prevents the execution of any scripts or modules as a security measure.</span></span>
> <span data-ttu-id="256af-117">若要允许在 Windows 上运行 `Invoke-NWChem.psm1` 模块，可能需要更改执行策略。</span><span class="sxs-lookup"><span data-stu-id="256af-117">To allow modules such as `Invoke-NWChem.psm1` to run on Windows, you may need to change the execution policy.</span></span>
> <span data-ttu-id="256af-118">为此，请运行 `Set-ExecutionPolicy` 命令：</span><span class="sxs-lookup"><span data-stu-id="256af-118">To do so, run the `Set-ExecutionPolicy` command:</span></span>
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> <span data-ttu-id="256af-119">当你退出 PowerShell 时，执行策略将被还原。</span><span class="sxs-lookup"><span data-stu-id="256af-119">The execution policy will then be reverted when you exit PowerShell.</span></span>
> <span data-ttu-id="256af-120">如果要保存执行策略，请使用不同的 `-Scope`值：</span><span class="sxs-lookup"><span data-stu-id="256af-120">If you would like to save the execution policy, use a different value for `-Scope`:</span></span>
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

<span data-ttu-id="256af-121">现在，你应该可以使用 `Convert-NWChemToBroombridge` 命令：</span><span class="sxs-lookup"><span data-stu-id="256af-121">You should now have the `Convert-NWChemToBroombridge` command available:</span></span>

```powershell
Get-Command -Module InvokeNWChem
```

<span data-ttu-id="256af-122">接下来，我们将导入**GetGateCount**示例附带的 `Get-GateCount` 命令。</span><span class="sxs-lookup"><span data-stu-id="256af-122">Next, we'll import the `Get-GateCount` command provided with the **GetGateCount** sample.</span></span>
<span data-ttu-id="256af-123">有关完整的详细信息，请参阅[示例中提供的说明](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount)。</span><span class="sxs-lookup"><span data-stu-id="256af-123">For full details, see the [instructions provided with the sample](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount).</span></span>
<span data-ttu-id="256af-124">接下来，运行以下操作，将 `<runtime>` 替换为 `win10-x64`、`osx-x64`或 `linux-x64`，具体取决于你的操作系统：</span><span class="sxs-lookup"><span data-stu-id="256af-124">Next, run the following, substituting `<runtime>` with either `win10-x64`, `osx-x64`, or `linux-x64`, depending on your operating system:</span></span>

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

<span data-ttu-id="256af-125">现在，你应该可以使用 `Get-GateCount` 命令：</span><span class="sxs-lookup"><span data-stu-id="256af-125">You should now have the `Get-GateCount` command available:</span></span>

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a><span data-ttu-id="256af-126">输入卡片</span><span class="sxs-lookup"><span data-stu-id="256af-126">Input Decks</span></span> ##

<span data-ttu-id="256af-127">NWChem 包采用一个名为 "_输入_" 的文本文件，该文件指定要解决的量程化学问题以及其他参数，例如内存分配设置。</span><span class="sxs-lookup"><span data-stu-id="256af-127">The NWChem package takes a text file called an _input deck_ which specifies a quantum chemistry problem to be solved, along with other parameters such as memory allocation settings.</span></span>
<span data-ttu-id="256af-128">在此示例中，我们将使用 NWChem 附带的一个预输入牌。</span><span class="sxs-lookup"><span data-stu-id="256af-128">For this example, we'll use one of the pre-made input decks that comes with NWChem.</span></span>
<span data-ttu-id="256af-129">首先，克隆[nwchemgit/nwchem 存储库](https://github.com/nwchemgit/nwchem)：</span><span class="sxs-lookup"><span data-stu-id="256af-129">First, clone the [nwchemgit/nwchem repository](https://github.com/nwchemgit/nwchem):</span></span>

> [!NOTE]
> <span data-ttu-id="256af-130">由于这是一个非常大的存储库，因此，我们可以使用 `--depth 1` 参数执行浅表克隆来节省带宽和磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="256af-130">Since this is a very large repository, we can do a shallow clone to save some bandwidth and disk space, using the `--depth 1` argument.</span></span>
> <span data-ttu-id="256af-131">但这是可选的。</span><span class="sxs-lookup"><span data-stu-id="256af-131">This is optional, however.</span></span>
> <span data-ttu-id="256af-132">如果没有 `--depth 1`，克隆功能将正常工作。</span><span class="sxs-lookup"><span data-stu-id="256af-132">Cloning will work just fine without `--depth 1`.</span></span>

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

<span data-ttu-id="256af-133">`nwchemgit/nwchem` 存储库随附了各种输入卡座，适用于在 " [`QA/chem_library_tests`" 文件夹](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests)下列出的 "量程开发" 工具包。</span><span class="sxs-lookup"><span data-stu-id="256af-133">The `nwchemgit/nwchem` repository comes with a variety of input decks intended for use with the Quantum Development Kit, listed under the [`QA/chem_library_tests` folder](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests).</span></span>
<span data-ttu-id="256af-134">在此示例中，我们将使用 `H4` 的输入牌：</span><span class="sxs-lookup"><span data-stu-id="256af-134">For this example, we'll use the `H4` input deck:</span></span>

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

<span data-ttu-id="256af-135">相关的分子是 4 hydrogen 原子的系统，它们按照一种角度的特定几何进行排列，参数 `alpha` 如的 `h4_sto6g_alpha.nw` 名称中所示。</span><span class="sxs-lookup"><span data-stu-id="256af-135">The molecule in question is a system of 4 hydrogen atoms that are arranged in a certain geometry that depends on one angle, the parameter `alpha` as indicated in the name `h4_sto6g_alpha.nw` of the deck.</span></span> <span data-ttu-id="256af-136">H4 是自70年代以来计算化学的已知[分子基准](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511)</span><span class="sxs-lookup"><span data-stu-id="256af-136">H4 is a known [molecular benchmark](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) for computational chemistry since the 1970s.</span></span> <span data-ttu-id="256af-137">参数 `sto6g` 表明，纸牌 orbital 实现了 Slater 类型的表示形式，具体而言，是指与[停止-nG basis](https://en.wikipedia.org/wiki/STO-nG_basis_sets)函数（包含6个高斯基础函数）有关的表示形式。</span><span class="sxs-lookup"><span data-stu-id="256af-137">The parameter `sto6g` is indicative that the deck implements a representation with respect to a Slater-type orbital, specifically, a representation with respect to an [STO-nG basis set](https://en.wikipedia.org/wiki/STO-nG_basis_sets) with 6 Gaussian basis functions.</span></span> <span data-ttu-id="256af-138">此输入组还包含 NWChem Tensor 缩写式引擎（TCE）的若干说明，这些说明指示 NWChem 生成与量程开发工具包互操作所需的信息：</span><span class="sxs-lookup"><span data-stu-id="256af-138">This input deck furthermore contains several instructions to the NWChem Tensor Contraction Engine (TCE) that direct NWChem to produce the information needed for interoperating with the Quantum Development Kit:</span></span>

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a><span data-ttu-id="256af-139">生成和使用 NWChem 的 Broombridge 输出</span><span class="sxs-lookup"><span data-stu-id="256af-139">Producing and Consuming Broombridge Output from NWChem</span></span> ##

<span data-ttu-id="256af-140">现在我们已经有了生成和使用 Broombridge 文档所需的一切。</span><span class="sxs-lookup"><span data-stu-id="256af-140">We now have everything we need to produce and consume Broombridge documents.</span></span>
<span data-ttu-id="256af-141">若要运行 NWChem 并为 `h4_sto6g_0.000.nw` 输入幻灯片生成 Broombridge 文档，请运行 `Convert-NWChemToBroombridge`：</span><span class="sxs-lookup"><span data-stu-id="256af-141">To run NWChem and produce a Broombridge document for the `h4_sto6g_0.000.nw` input deck, run `Convert-NWChemToBroombridge`:</span></span>

> [!NOTE]
> <span data-ttu-id="256af-142">第一次运行此命令时，Docker 将下载 `nwchemorg/nwchem-qc` 映像。</span><span class="sxs-lookup"><span data-stu-id="256af-142">The first time you run this command, Docker will download the `nwchemorg/nwchem-qc` image for you.</span></span>
> <span data-ttu-id="256af-143">这可能需要一些时间，具体取决于你的连接速度，可能会为你提供一个令杯咖啡的机会。</span><span class="sxs-lookup"><span data-stu-id="256af-143">This may take a little while, depending on your connection speed, possibly providing an opportunity to get a cup of coffee.</span></span>

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

<span data-ttu-id="256af-144">这将生成一个名为 `h4_sto6g_0.000.yaml` 的 Broombridge 文档，可用于 `Get-GateCount`：</span><span class="sxs-lookup"><span data-stu-id="256af-144">This will produce a Broombridge document called `h4_sto6g_0.000.yaml` that we can use with `Get-GateCount`:</span></span>

```powershell
Get-GateCount -Format YAML h4_sto6g_0.000.yaml
```

<span data-ttu-id="256af-145">现在应会看到控制台输出，其中包含各种量程模拟方法的资源估算，如 T 计数、旋转计数、CNOT-CONTAINS 计数等：</span><span class="sxs-lookup"><span data-stu-id="256af-145">You should now see console output which contains resource estimation such as T-count, rotations count, CNOT count, etc. for various quantum simulation methods:</span></span>

```powershell 
IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Trotter
TCount              : 0
RotationsCount      : 92
CNOTCount           : 520
ElapsedMilliseconds : 327

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Qubitization
TCount              : 438
RotationsCount      : 516
CNOTCount           : 2150
ElapsedMilliseconds : 528

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Optimized Qubitization
TCount              : 3540
RotationsCount      : 18
CNOTCount           : 7932
ElapsedMilliseconds : 721
```

<span data-ttu-id="256af-146">这里有很多需要注意的事项：</span><span class="sxs-lookup"><span data-stu-id="256af-146">There are many things to go do from here:</span></span> 
- <span data-ttu-id="256af-147">尝试不同的预定义输入纸牌，例如，通过改变 `h4_sto6g_alpha.nw`中的参数 `alpha`。</span><span class="sxs-lookup"><span data-stu-id="256af-147">Try out different predefined input decks, e.g., by varying the parameter `alpha` in `h4_sto6g_alpha.nw`,</span></span> 
- <span data-ttu-id="256af-148">尝试通过直接编辑 NWChem 卡片进行修改，例如，探索用于不同选项 n 的 `STO-nG` 模型，</span><span class="sxs-lookup"><span data-stu-id="256af-148">Try modifying the decks by editing the NWChem decks directly, e.g., exploring `STO-nG` models for various choices of n,</span></span> 
- <span data-ttu-id="256af-149">尝试 `nwchem/qa/chem_library_tests`提供的其他预定义的 NWChem 输入卡座，</span><span class="sxs-lookup"><span data-stu-id="256af-149">Try other predefined NWChem input decks that are available at `nwchem/qa/chem_library_tests`,</span></span>
- <span data-ttu-id="256af-150">尝试从 NWChem 生成的一系列预定义的 Broombridge YAML 基准，并将其作为[Microsoft/量子存储库](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML)的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="256af-150">Try out a suite of predefined Broombridge YAML benchmarks that were generated from NWChem and are available as part of the [Microsoft/Quantum repository](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML).</span></span> <span data-ttu-id="256af-151">这些基准包括：</span><span class="sxs-lookup"><span data-stu-id="256af-151">These benchmarks include:</span></span> 
    - <span data-ttu-id="256af-152">small 分子，例如分子 hydrogen （H2）、Beryllium （）、锂 hydride （LiH）、</span><span class="sxs-lookup"><span data-stu-id="256af-152">small molecules such as molecular hydrogen (H2), Beryllium (Be), Lithium hydride (LiH),</span></span>
    - <span data-ttu-id="256af-153">更大的分子，例如臭氧（O3）、carotene、cytosine 等。</span><span class="sxs-lookup"><span data-stu-id="256af-153">larger molecules such as ozone (O3), beta-carotene, cytosine, and many more.</span></span> 
- <span data-ttu-id="256af-154">尝试使用具有 Microsoft Quantum Development Kit 的接口的图形前端[EMSL 箭头](https://arrows.emsl.pnnl.gov/api/qsharp_chem)。</span><span class="sxs-lookup"><span data-stu-id="256af-154">Try out the graphical front-end [EMSL Arrows](https://arrows.emsl.pnnl.gov/api/qsharp_chem) that features an interface to the Microsoft Quantum Development Kit.</span></span> 


## <a name="producing-broombridge-output-from-emsl-arrows"></a><span data-ttu-id="256af-155">从 EMSL 箭头生成 Broombridge 输出</span><span class="sxs-lookup"><span data-stu-id="256af-155">Producing Broombridge Output from EMSL Arrows</span></span> ##

<span data-ttu-id="256af-156">若要开始使用基于 web 的前端 EMSL 箭头，请在[此处](https://arrows.emsl.pnnl.gov/api/qsharp_chem)导航浏览器。</span><span class="sxs-lookup"><span data-stu-id="256af-156">To get started with web-based front end EMSL Arrows, navigate a browser [here](https://arrows.emsl.pnnl.gov/api/qsharp_chem).</span></span> 

> [!NOTE]
> <span data-ttu-id="256af-157">在 web 浏览器中运行 EMSL 箭头需要启用 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="256af-157">Running EMSL Arrows in a web browser requires JavaScript to be enabled.</span></span> <span data-ttu-id="256af-158">请参阅以下[说明](https://www.enable-javascript.com/)，了解如何在浏览器中启用 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="256af-158">Please refer to these [instructions](https://www.enable-javascript.com/) on how to enable JavaScript in your browser.</span></span> 

<span data-ttu-id="256af-159">首先，在 "查询" 框中输入分子，其中显示 ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.``</span><span class="sxs-lookup"><span data-stu-id="256af-159">First, enter a molecule in the query box that says ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.``</span></span> 

<span data-ttu-id="256af-160">可以按其 colloquial 名称输入许多分子，例如 "加班加点"，而不是 "1，3，7-Trimethylxanthine"。</span><span class="sxs-lookup"><span data-stu-id="256af-160">You can enter many molecules by their colloquial name, such as "caffeine" instead of "1,3,7-Trimethylxanthine".</span></span> 

<span data-ttu-id="256af-161">接下来，单击 "``theory{qsharp_chem}``" 按钮。</span><span class="sxs-lookup"><span data-stu-id="256af-161">Next, click the button that says ``theory{qsharp_chem}``.</span></span> <span data-ttu-id="256af-162">这将进一步用指示运行以 Broombridge YAML 格式导出输出的指令来填充查询框。</span><span class="sxs-lookup"><span data-stu-id="256af-162">This will populate the query box further with an instruction that will tell the run to export output in the Broombridge YAML format.</span></span> 

<span data-ttu-id="256af-163">现在，``Run Arrows``上的时钟。</span><span class="sxs-lookup"><span data-stu-id="256af-163">Now, clock on ``Run Arrows``.</span></span> <span data-ttu-id="256af-164">这可能需要一些时间，具体取决于输入的大小。</span><span class="sxs-lookup"><span data-stu-id="256af-164">Depending on the size of the input, this might take a while.</span></span> <span data-ttu-id="256af-165">或者，如果特定模型之前已经计算过，则可以非常快速地完成此操作，因为它只是在数据库中的查找量。</span><span class="sxs-lookup"><span data-stu-id="256af-165">Or, in case the particular model has already been computed before, it can be done extremely fast as it will only amount to a lookup in a database.</span></span> <span data-ttu-id="256af-166">无论是哪种情况，都将转到一个新页面，其中包含有关特定运行 NWChem 的很多信息，具体取决于输入指定的牌。</span><span class="sxs-lookup"><span data-stu-id="256af-166">In either case, you will be taken to a new page that contains a plethora of information about the particular run of NWChem against the deck specified by your input.</span></span> 

<span data-ttu-id="256af-167">可以从以以下标头开头的部分下载并保存 Broombridge YAML 文件：</span><span class="sxs-lookup"><span data-stu-id="256af-167">You can download and save the Broombridge YAML file from the section that starts with the following header:</span></span> 
```powershell
+==================================================+
||              Molecular Calculation             ||
+==================================================+

Id     = 48443

NWOutput = Link to NWChem Output (download)

Datafiles:
qsharp_chem.yaml-2018-10-23-14:37:42 (download)
...
```

<span data-ttu-id="256af-168">单击 "``download``"，将使用唯一的文件名（如 ``qsharp_chem48443.yaml``）保存本地副本（每次运行时，特定名称将有所不同）。</span><span class="sxs-lookup"><span data-stu-id="256af-168">Click on ``download``, which saves a local copy with a unique file name such as ``qsharp_chem48443.yaml`` (the particular name will be different for each run).</span></span> <span data-ttu-id="256af-169">然后，你可以按照上述方式进一步处理此文件，例如，用</span><span class="sxs-lookup"><span data-stu-id="256af-169">You can then further process this file as above, e.g., with</span></span> 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
<span data-ttu-id="256af-170">获取资源计数。</span><span class="sxs-lookup"><span data-stu-id="256af-170">to get resource counts.</span></span> 

<span data-ttu-id="256af-171">你可能会喜欢通过 EMSL 箭头起始页上的 "``Arrows Entry - 3D Builder``" 选项卡访问的3D 分子生成器。</span><span class="sxs-lookup"><span data-stu-id="256af-171">You might enjoy the 3D molecule builder that can be accessed from the ``Arrows Entry - 3D Builder`` tab on the EMSL Arrows start page.</span></span> <span data-ttu-id="256af-172">单击所显示的分子的[JSMol](http://wiki.jmol.org/index.php/JSmol) 3d 图片，可以允许对其进行编辑。</span><span class="sxs-lookup"><span data-stu-id="256af-172">Clicking the [JSMol](http://wiki.jmol.org/index.php/JSmol) 3D picture of the shown molecule will let you allow to edit it.</span></span> <span data-ttu-id="256af-173">您可以四处移动原子，将原子拖到一起，使它们之间的分子距离发生变化、添加/删除原子等。对于上述每个选项，在 "查询" 框中添加 ``theory{qsharp_chem}`` 后，便可以生成 Broombridge YAML 架构的实例，并使用量程化学库进一步浏览该实例。</span><span class="sxs-lookup"><span data-stu-id="256af-173">You can move atoms around, drag atoms apart so that their inter-molecular distances change, add/remove atoms, etc. For each of these choices, once you added ``theory{qsharp_chem}`` in the query box, you can then generate an instance of the Broombridge YAML schema and further explore it using the Quantum Chemistry Library.</span></span> 