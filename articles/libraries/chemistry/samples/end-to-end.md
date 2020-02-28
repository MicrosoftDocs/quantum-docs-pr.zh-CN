---
title: 示例 NWChem 量程计划
description: 使用 NWChem 输入纸牌，演练一个示例，了解如何获取量程化学模拟的入口计数。
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/23/2018
uid: microsoft.quantum.chemistry.examples.endtoend
ms.openlocfilehash: 545ade99859f2a9939477fb18604921f70a5d9aa
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906502"
---
# <a name="end-to-end-with-nwchem"></a>NWChem 端到端 #

在本页面中，我们将逐步介绍如何从[NWChem](http://www.nwchem-sw.org/index.php/Main_Page)的输入牌中获取量程化学模拟的入口计数。
在继续此示例之前，请确保已按照[安装和验证指南](xref:microsoft.quantum.chemistry.concepts.installation)安装了 Docker。

更多相关信息：
- [NWChem 输入卡座的结构](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [用于量程开发工具包的输入纸牌命令](https://github.com/nwchemgit/nwchem/tree/master/contrib/quasar)
- [安装化学库和依赖项](xref:microsoft.quantum.chemistry.concepts.installation)
- [资源计数](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> 此示例需要运行 Windows PowerShell Core。
> https://github.com/PowerShell/PowerShell下载适用于 Windows、macOS 或 Linux 的 PowerShell Core。

## <a name="importing-required-powershell-modules"></a>导入所需的 PowerShell 模块 ##

如果尚未这样做，请克隆[Microsoft/量子存储库](https://github.com/Microsoft/Quantum)，其中包含用于处理量程开发工具包的示例和实用程序：

```powershell
git clone https://github.com/Microsoft/Quantum
```

克隆 `Microsoft/Quantum`后，请在 `utilities/` 文件夹中执行 `cd`，并导入 PowerShell 模块以便使用 Docker 和 NWChem：

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> 默认情况下，Windows 会阻止执行任何脚本或模块作为安全措施。
> 若要允许在 Windows 上运行 `Invoke-NWChem.psm1` 模块，可能需要更改执行策略。
> 为此，请运行 `Set-ExecutionPolicy` 命令：
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> 当你退出 PowerShell 时，执行策略将被还原。
> 如果要保存执行策略，请使用不同的 `-Scope`值：
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

现在，你应该可以使用 `Convert-NWChemToBroombridge` 命令：

```powershell
Get-Command -Module InvokeNWChem
```

接下来，我们将导入**GetGateCount**示例附带的 `Get-GateCount` 命令。
有关完整的详细信息，请参阅[示例中提供的说明](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount)。
接下来，运行以下操作，将 `<runtime>` 替换为 `win10-x64`、`osx-x64`或 `linux-x64`，具体取决于你的操作系统：

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

现在，你应该可以使用 `Get-GateCount` 命令：

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a>输入卡片 ##

NWChem 包采用一个名为 "_输入_" 的文本文件，该文件指定要解决的量程化学问题以及其他参数，例如内存分配设置。
在此示例中，我们将使用 NWChem 附带的一个预输入牌。
首先，克隆[nwchemgit/nwchem 存储库](https://github.com/nwchemgit/nwchem)：

> [!NOTE]
> 由于这是一个非常大的存储库，因此，我们可以使用 `--depth 1` 参数执行浅表克隆来节省带宽和磁盘空间。
> 但这是可选的。
> 如果没有 `--depth 1`，克隆功能将正常工作。

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

`nwchemgit/nwchem` 存储库随附了各种输入卡座，适用于在 " [`QA/chem_library_tests`" 文件夹](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests)下列出的 "量程开发" 工具包。
在此示例中，我们将使用 `H4` 的输入牌：

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

相关的分子是 4 hydrogen 原子的系统，它们按照一种角度的特定几何进行排列，参数 `alpha` 如的 `h4_sto6g_alpha.nw` 名称中所示。 H4 是自70年代以来计算化学的已知[分子基准](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) 参数 `sto6g` 表明，纸牌 orbital 实现了 Slater 类型的表示形式，具体而言，是指与[停止-nG basis](https://en.wikipedia.org/wiki/STO-nG_basis_sets)函数（包含6个高斯基础函数）有关的表示形式。 此输入组还包含 NWChem Tensor 缩写式引擎（TCE）的若干说明，这些说明指示 NWChem 生成与量程开发工具包互操作所需的信息：

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a>生成和使用 NWChem 的 Broombridge 输出 ##

现在我们已经有了生成和使用 Broombridge 文档所需的一切。
若要运行 NWChem 并为 `h4_sto6g_0.000.nw` 输入幻灯片生成 Broombridge 文档，请运行 `Convert-NWChemToBroombridge`：

> [!NOTE]
> 第一次运行此命令时，Docker 将下载 `nwchemorg/nwchem-qc` 映像。
> 这可能需要一些时间，具体取决于你的连接速度，可能会为你提供一个令杯咖啡的机会。

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

这将生成一个名为 `h4_sto6g_0.000.yaml` 的 Broombridge 文档，可用于 `Get-GateCount`：

```powershell
Get-GateCount -Format YAML h4_sto6g_0.000.yaml
```

现在应会看到控制台输出，其中包含各种量程模拟方法的资源估算，如 T 计数、旋转计数、CNOT-CONTAINS 计数等：

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

这里有很多需要注意的事项： 
- 尝试不同的预定义输入纸牌，例如，通过改变 `h4_sto6g_alpha.nw`中的参数 `alpha`。 
- 尝试通过直接编辑 NWChem 卡片进行修改，例如，探索用于不同选项 n 的 `STO-nG` 模型， 
- 尝试 `nwchem/qa/chem_library_tests`提供的其他预定义的 NWChem 输入卡座，
- 尝试从 NWChem 生成的一系列预定义的 Broombridge YAML 基准，并将其作为[Microsoft/量子存储库](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML)的一部分提供。 这些基准包括： 
    - small 分子，例如分子 hydrogen （H2）、Beryllium （）、锂 hydride （LiH）、
    - 更大的分子，例如臭氧（O3）、carotene、cytosine 等。 
- 尝试使用具有 Microsoft Quantum Development Kit 的接口的图形前端[EMSL 箭头](https://arrows.emsl.pnnl.gov/api/qsharp_chem)。 


## <a name="producing-broombridge-output-from-emsl-arrows"></a>从 EMSL 箭头生成 Broombridge 输出 ##

若要开始使用基于 web 的前端 EMSL 箭头，请在[此处](https://arrows.emsl.pnnl.gov/api/qsharp_chem)导航浏览器。 

> [!NOTE]
> 在 web 浏览器中运行 EMSL 箭头需要启用 JavaScript。 请参阅以下[说明](https://www.enable-javascript.com/)，了解如何在浏览器中启用 JavaScript。 

首先，在 "查询" 框中输入分子，其中显示 ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.`` 

可以按其 colloquial 名称输入许多分子，例如 "加班加点"，而不是 "1，3，7-Trimethylxanthine"。 

接下来，单击 "``theory{qsharp_chem}``" 按钮。 这将进一步用指示运行以 Broombridge YAML 格式导出输出的指令来填充查询框。 

现在，``Run Arrows``上的时钟。 这可能需要一些时间，具体取决于输入的大小。 或者，如果特定模型之前已经计算过，则可以非常快速地完成此操作，因为它只是在数据库中的查找量。 无论是哪种情况，都将转到一个新页面，其中包含有关特定运行 NWChem 的很多信息，具体取决于输入指定的牌。 

可以从以以下标头开头的部分下载并保存 Broombridge YAML 文件： 
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

单击 "``download``"，将使用唯一的文件名（如 ``qsharp_chem48443.yaml``）保存本地副本（每次运行时，特定名称将有所不同）。 然后，你可以按照上述方式进一步处理此文件，例如，用 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
获取资源计数。 

你可能会喜欢通过 EMSL 箭头起始页上的 "``Arrows Entry - 3D Builder``" 选项卡访问的3D 分子生成器。 单击所显示的分子的[JSMol](http://wiki.jmol.org/index.php/JSmol) 3d 图片，可以允许对其进行编辑。 您可以四处移动原子，将原子拖到一起，使它们之间的分子距离发生变化、添加/删除原子等。对于上述每个选项，在 "查询" 框中添加 ``theory{qsharp_chem}`` 后，便可以生成 Broombridge YAML 架构的实例，并使用量程化学库进一步浏览该实例。 
