---
title: 'Microsoft Q # 化学库安装'
description: 了解如何安装 Microsoft 量程化学库，并将其与 NWChem 计算化学平台配合使用。
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: 0e870bb3421dddb632375a2fc8633249954f8c8b
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871523"
---
# <a name="chemistry-library-installation"></a>化学库安装

[ **MolecularHydrogen**示例](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen)使用手动配置的分子输入数据。
虽然这对小型示例而言很不错，但大规模的量程化学要求 Hamiltonians 或数十亿。
此类 Hamiltonians 是由可扩展的计算化学包生成的，太大，无法手动导入。

适用于量子开发工具包的量程化学库旨在与计算化学包一起正常工作，最值得注意的是，在太平洋西北部国家实验室，环境分子科学实验室（EMSL）开发的[**NWChem**](http://www.nwchem-sw.org/)计算化学平台。
具体而言，Broombridge [ **Microsoft.Quantum.Chemistry**包](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry)提供的工具可用于加载在[架构](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)中表示的量程化学模拟问题的实例，还支持在最新版本的 NWChem 中导出。

量程开发工具包化学库还提供了一个命令行工具， `qdk-chem` 用于在旧式格式与[Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)之间进行转换。

本部分详细介绍如何将量程开发工具包与 NWChem 和 Broombridge 一起使用，或者使用旧格式和 `qdk-chem` 。

## <a name="using-the-quantum-development-kit-with-nwchem"></a>将量程开发工具包与 NWChem 配合使用

若要使用 NWChem 和量程开发工具包启动并运行，请使用以下方法之一：

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
> 安装[Ubuntu 18.04 LTS For Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab)后， `ubuntu18.04` 从你喜欢的终端运行并按照上面的说明从源安装 NWChem。

从源中编译 NWChem 后，可以运行 `yaml_driver` 与 NWChem 一起提供的脚本，通过 NWChem 输入卡座快速生成 Broombridge 实例：

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

此命令将 `input.yaml` 在当前目录中创建 Broombridge 格式的新文件。

### <a name="using-nwchem-with-docker"></a>结合使用 NWChem 和 Docker

使用 NWChem 的预构建映像可通过[Docker 中心](https://hub.docker.com)跨平台使用。
若要开始，请遵循适用于你的平台的 Docker 安装说明：

- [安装 Docker for Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [安装适用于 macOS 的 Docker](https://docs.docker.com/docker-for-mac/install/)
- [安装用于 Windows 的 Docker 10](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> 如果使用用于 Windows 的 Docker，则需要与 Docker 守护程序共享包含临时目录的驱动器（通常是 `C:\` 驱动器）。 有关更多详细信息，请参阅[Docker 文档](https://docs.docker.com/docker-for-windows/#shared-drives)。

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

这将通过在上运行 NWChem 来创建 Broombridge 文件 `input.nw` 。
默认情况下，Broombridge 输出将与输入纸盒具有相同的名称和路径，并将 `.nw` 扩展名替换为 `.yaml` 。
可以使用参数将其重写 `-DestinationPath` `Convert-NWChemToBroombridge` 。
可以使用 PowerShell 的内置帮助功能获取详细信息：

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```

## <a name="using-the-quantum-development-kit-with-qdk-chem"></a>使用量子开发工具包`qdk-chem`

若要安装 `qdk-chem` ，你可以在命令行中使用 .NET Core SDK：

```dotnetcli
dotnet tool install --global Microsoft.Quantum.Chemistry.Tools
```

安装后 `qdk-chem` ，可以使用 `--help` 选项获取有关该工具提供的功能的更多详细信息 `qdk-chem` 。

若要转换为 Broombridge，可以使用 `qdk-chem convert` 命令：

```
qdk-chem convert --from fcidump --to broombridge data.fcidump --out data.yml
```

该 `qdk-chem convert` 命令还可以接受其来自标准输入的数据，并可以写入标准输出; 这在脚本中尤其有用，并且与导出为旧格式的工具集成。
例如，在 Bash 中执行以下代码：

```bash
cat data.fcidump | qdk-convert --from fcidump --to broombridge - > data.yml
```
