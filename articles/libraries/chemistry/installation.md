---
title: 'Microsoft Q # 化学库安装和验证'
description: 了解如何安装 Microsoft 量程化学库，并将其与 NWChem 计算化学平台配合使用。
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: 48bf7bc980e238e622053f5c2bdd09604c572596
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907352"
---
# <a name="chemistry-library-installation-and-validation"></a>化学库安装和验证

量程开发工具包通过[`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) NuGet 包提供对量程化学应用程序的支持。
与其他 NuGet 包一样，可以直接将化学库添加到项目。

**Visual Studio 2019：** 如果使用的是 Visual Studio 2019，则可以使用 NuGet 包管理器添加量程化学包。
若要打开程序包管理器，请右键单击要向其添加化学库的项目，然后选择 "管理 NuGet 包 ..."，如下面的屏幕截图所示。

![在 Visual Studio 2019 中使用 NuGet 包管理器](~/media/vs2017-nuget-manage-packages.png)

从 "浏览" 选项卡中，搜索包名称 ""。

> [!NOTE]
> 请确保 "包括预发行版"。

!["包括预发行版" 复选框](~/media/vs2017-nuget-package-search.png)

这将列出可供下载的包。
单击左侧窗格中的 ""，然后在右侧窗格中选择最新的预发行版本，然后单击 "安装"：

![安装最新的 Microsoft 量子包](~/media/vs2017-nuget-select-chem.png)

有关更多详细信息，请参阅[包管理器 UI 指南](https://docs.microsoft.com/nuget/tools/package-manager-ui)。

或者，你可以使用包管理器控制台，使用命令行接口将量程化学库添加到你的项目中。

![在命令行中使用程序包管理器控制台](~/media/vs2017-nuget-console-menu.png)

从包管理器控制台中，运行以下内容：

```
Install-Package Microsoft.Quantum.Chemistry
```

有关更多详细信息，请参阅[包管理器控制台指南](https://docs.microsoft.com/nuget/tools/package-manager-console)。

**命令行或 Visual Studio Code：** 你可以使用命令行自己使用命令行，也可以从 Visual Studio Code 中，使用 `dotnet` 命令将 NuGet 包引用添加到你的项目：

```dotnetcli
dotnet add package Microsoft.Quantum.Chemistry
```

## <a name="verifying-your-installation"></a>验证安装 

与量程开发工具包的其余部分一样，量程化学库附带了多个完整记录的示例，可帮助你快速启动和运行。
若要使用这些示例测试安装，请克隆[主示例存储库](https://github.com/Microsoft/Quantum)，然后运行其中一个示例。  例如，若要运行[`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen)示例：

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/chemistry/MolecularHydrogen
dotnet run
```

若要在克隆存储库后使用 Microsoft Visual Studio 验证量程化学库的安装，请执行以下操作：
    1. 在化学文件夹中打开 ChemistrySamples 解决方案。  
    2. 选择 "示例/1"。 简单分子/MolecularHydrogen 作为启动项目。
    3. 按 F5 运行分子 Hydrogen 量程阶段估算演示。

有关估计能源水平值的详细信息，请参阅[获取能源水平估算](xref:microsoft.quantum.chemistry.examples.energyestimate)。   


## <a name="using-the-quantum-development-kit-with-nwchem"></a>将量程开发工具包与 NWChem 配合使用 ##

MolecularHydrogen 示例使用手动配置的分子输入数据。  虽然这对小型示例而言很不错，但大规模的量程化学要求 Hamiltonians 或数十亿。 可缩放的计算化学包生成的此类 Hamiltonians 太大，无法手动导入。 

适用于量子开发工具包的量程化学库旨在与计算化学包一起正常工作，最值得注意的是，在太平洋西北部国家实验室，环境分子科学实验室（EMSL）开发的[**NWChem**](http://www.nwchem-sw.org/)计算化学平台。
具体而言，`Microsoft.Quantum.Chemistry` 包提供的工具可用于加载在[Broombridge 架构](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)中表示的量程化学模拟问题的实例，还支持 NWChem 最新版本的导出。

若要将 NWChem 与量程开发工具包一起使用，我们建议使用以下方法之一：
- 开始使用在[IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML)的示例中提供的现有 Broombridge 文件。
- 将[EMSL 箭头生成器用于](https://arrows.emsl.pnnl.gov/api/qsharp_chem)作为基于 web 的前端到 NWChem 的 Microsoft Quantum Development Kit，以生成新的 Broombridge 格式化分子输入文件。  
- 使用 PNNL 提供的[Docker 映像](https://hub.docker.com/r/nwchemorg/nwchem-qc/)运行 NWChem，或
- [编译](http://www.nwchem-sw.org/index.php/Compiling_NWChem)平台的 NWChem。

请参阅[使用 NWChem 的端到端](xref:microsoft.quantum.chemistry.examples.endtoend)的详细信息，了解有关如何使用 NWChem 到化学模型的详细信息，以使用量程开发套件化学库进行分析。

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a>使用示例提供的 Broombridge 文件入门

量程开发工具包示例存储库中的[IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML)文件夹包含 Broombridge 格式化的分子数据文件。  

作为一个简单的示例，请使用化学 library 示例， [GetGateCount](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/GetGateCount)从 Broombridge 文件之一加载 Hamiltonian，并执行量程模拟 algorigthms 的入口估计：

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

有关如何输入 Broombridge 架构表示的分子的详细信息，请参阅[从文件加载 Hamiltonian](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) 。  

有关资源估计的详细信息，请参阅[获取资源计数](xref:microsoft.quantum.chemistry.examples.resourcecounts)。  

### <a name="getting-started-using-the-emsl-arrows-builder"></a>开始使用 EMSL 箭头生成器

EMSL 箭头是一种使用 NWChem 和化学计算数据库生成分子数据的工具。  使用[Microsoft Quantum Development Kit 的 EMSL 箭头生成器](https://arrows.emsl.pnnl.gov/api/qsharp_chem)，可以使用多个分子模型生成器输入模型，并生成将由量子开发工具包使用的 Broombridge 数据文件。  

从 "EMSL" 页上，单击 [' China '] 选项卡，然后按照 [' 简单示例 '] 说明生成 Broombridge 文件。  然后尝试运行 [' GetGateCount ']，查看这些分子的量程资源估算值。

### <a name="installing-nwchem-from-source"></a>从源安装 NWChem

[PNNL 提供](http://www.nwchem-sw.org/index.php/Compiling_NWChem)了有关如何从源安装 NWChem 的完整说明。

> [!TIP]
> 如果要从 Windows 10 使用 NWChem，适用于 Linux 的 Windows 子系统是一个不错的选择。
> 安装[Ubuntu 18.04 LTS For Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab)后，请从喜欢的终端运行 `ubuntu18.04`，并按照上述说明从 "源" 安装 NWChem。

从源中编译 NWChem 后，可以运行与 NWChem 一起提供的 `yaml_driver` 脚本，通过 NWChem 输入卡座快速生成 Broombridge 实例：

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

此命令将在当前目录中创建 Broombridge 格式的新的 `input.yaml` 文件。

### <a name="using-nwchem-with-docker"></a>结合使用 NWChem 和 Docker

使用 NWChem 的预构建映像可通过[Docker 中心](https://hub.docker.com)跨平台使用。
若要开始，请遵循适用于你的平台的 Docker 安装说明：

- [安装 Docker for Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [安装适用于 macOS 的 Docker](https://docs.docker.com/docker-for-mac/install/)
- [安装用于 Windows 的 Docker 10](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> 如果使用用于 Windows 的 Docker，则需要使用 Docker 守护程序共享包含临时目录的驱动器（通常是 `C:\` 驱动器）。 有关更多详细信息，请参阅[Docker 文档](https://docs.docker.com/docker-for-windows/#shared-drives)。

安装 Docker 后，可以使用随量程开发工具包示例提供的 PowerShell 模块来运行映像，也可以手动运行映像。
此处是使用 PowerShell 的详细信息;如果希望手动使用 Docker 映像，请参阅[随图像提供的文档](https://hub.docker.com/r/nwchemorg/nwchem-qc/)。

#### <a name="running-nwchem-through-powershell-core"></a>通过 PowerShell Core 运行 NWChem

若要将 NWChem Docker 映像与量程开发工具包一起使用，我们提供了一个小型 PowerShell 模块，用于处理将文件移入和移出 NWChem 的情况。
如果尚未安装 PowerShell Core，则可以从[GitHub 上的 powershell 存储库](https://github.com/PowerShell/PowerShell#get-powershell)跨平台下载。

> [!NOTE]
> PowerShell Core 还适用于一些示例，用于演示与数据科学和业务分析工作流的互操作性。

安装 PowerShell Core 后，导入 `InvokeNWChem.psm1` 以使 NWChem 命令在当前会话中可用：

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

这会使 `Convert-NWChemToBroombridge` 命令在当前 PowerShell 会话中可用。
若要从 Docker 下载任何所需的映像并将其用于运行 NWChem input 卡座并将输出捕获到 Broombridge，请运行以下内容：

```powershell
Convert-NWChemToBroombridge ./input.nw
```

这将通过在 `input.nw`上运行 NWChem 来创建 Broombridge 文件。
默认情况下，Broombridge 输出将与输入纸盒具有相同的名称和路径，并且 `.nw` 扩展将替换为 `.yaml`。
这可以通过使用 `Convert-NWChemToBroombridge`的 `-DestinationPath` 参数重写。
可以使用 PowerShell 的内置帮助功能获取详细信息：

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```
