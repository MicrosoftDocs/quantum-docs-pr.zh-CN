---
title: Quantum 开发工具包发行说明
description: 了解 Microsoft Quantum 开发工具包预览版的最新更新。
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
uid: microsoft.quantum.relnotes
ms.openlocfilehash: d10f81a1e49235be8e02661dcd6d3c839485af6e
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885051"
---
# <a name="microsoft-quantum-development-kit-release-notes"></a>Microsoft 量子开发工具包发行说明

本文包含有关每个量子开发工具包版本的信息。

有关安装说明，请参阅[安装指南](xref:microsoft.quantum.install)。

有关更新说明，请参阅[更新指南](xref:microsoft.quantum.update)。

## <a name="version-01220070124"></a>版本0.12.20070124

*发布日期：2020年7月2日*

此版本包含以下各项：

- `qdk-chem`用于将旧电子结构问题序列化格式（例如： FCIDUMP）转换为[Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)的新工具
- 一致[ `Microsoft.Quantum.Synthesis` 命名空间](xref:microsoft.quantum.synthesis)中的新函数和操作使用基于转换和分解的合成算法来应用传统 oracles。
- IQ # 现在允许参数用于 `%simulate` 、 `%estimate` 和其他幻命令。 有关更多详细信息，请参阅[ `%simulate` 幻命令参考](xref:microsoft.quantum.iqsharp.magic-ref.simulate)。
- IQ # 中的新阶段显示选项。 有关更多详细信息，请参阅[ `%config` 幻命令参考](xref:microsoft.quantum.iqsharp.magic-ref.config)。
- IQ # 和 `qsharp` Python 包现在是通过 conda 包（[qsharp](https://anaconda.org/quantum-engineering/qsharp)和[iqsharp](https://anaconda.org/quantum-engineering/iqsharp)）提供的，用于简化在 conda 环境中安装 Q # Jupyter 和 python 功能的过程。 有关更多详细信息，请参阅[q # Jupyter 笔记本](xref:microsoft.quantum.install.jupyter)和包含 Python 安装指南的[q #](xref:microsoft.quantum.install.python) 。
- 使用模拟器时，qubits 不再需要处于版本 | 0 ⟩状态，如果在释放前立即测量，则可以自动重置。
- 用于使 IQ # 用户更轻松地使用具有不同 QDK 版本的库包的更新，只要求主要 & 次版本号匹配，而不是完全相同的版本
- 删除不推荐使用的 `Microsoft.Quantum.Primitive.*` 命名空间
- 移动操作：
  - `Microsoft.Quantum.Intrinsic.Assert` 现为 `Microsoft.Quantum.Diagnostics.AssertMeasurement`
  - `Microsoft.Quantum.Intrinsic.AssertProb` 现为 `Microsoft.Quantum.Diagnostics.AssertMeasurementProbability`
- Bug 修复 

有关[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[编译器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[运行时](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)、[IQ#](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) 和 [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 的信息，请参阅已结束的 PR 的完整列表。  

## <a name="version-0112006403"></a>版本 0.11.2006.403

发行日期：*2020 年 6 月 4 日*

此版本修复了一个影响编译 Q# 项目的 bug。

## <a name="version-0112006207"></a>版本 0.11.2006.207

发行日期：*2020 年 6 月 3 日*

此版本包含以下各项：

- 当存在 Q# 入口点时，Q# 笔记本和 Python 主机程序将不再失败
- 更新了[标准库](xref:microsoft.quantum.libraries.standard.intro)以使用访问修饰符
- 编译器现在允许在内置重写步骤之间插入重写步骤
- 按照 [API 原则](xref:microsoft.quantum.contributing.api-design)中所述的计划删除了几个弃用的函数和操作。 在版本 0.11.2004.2825 中未出现警告的情况下生成的 Q# 程序和库将继续工作，不会进行修改。

有关[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[编译器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[运行时](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)、[IQ#](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) 和 [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 的信息，请参阅已结束的 PR 的完整列表。  

> [!NOTE]
> 此版本包含一个影响编译 Q# 项目的 bug。 建议升级到较新版本。

## <a name="version-01120042825"></a>版本 0.11.2004.2825

发行日期：*2020 年 4 月 30 日*

此版本包含以下各项：

- 对 Q# 命令行应用程序的新支持，这些应用程序不再需要 C# 或 Python 主机文件。 有关 Q# 命令行应用程序入门的详细信息，请参阅[此处](xref:microsoft.quantum.install.standalone)。
- 更新了量子随机数生成器快速入门，从而不再需要 C# 或 Python 主机文件。 参阅更新的[快速入门](xref:microsoft.quantum.quickstarts.qrng)
- IQ# Docker 映像的性能改进

> [!NOTE]
> 使用新的 [`@EntryPoint()`](xref:microsoft.quantum.core.entrypoint) 特性的 Q# 命令行应用程序当前无法从 Python 或 .NET 主机程序调用。
> 有关详细信息，请参阅 [Python](xref:microsoft.quantum.install.python) 和 [.NET 互操作性](xref:microsoft.quantum.install.cs)指南。

## <a name="version-01120033107"></a>版本 0.11.2003.3107

发行日期：*2020 年 3 月 31 日*

此版本包含针对版本 0.11.2003.2506 的小 Bug 修复。

## <a name="version-01120032506"></a>版本 0.11.2003.2506

发行日期：*2020 年 3 月 26 日*

此版本包含以下各项：

- 对 Q# 中的访问修饰符的新支持，有关详细信息，请参阅[文件结构](xref:microsoft.quantum.guide.filestructure)
- 已更新为 .NET Core SDK 3.1

有关[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[编译器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[运行时](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 的信息，请参阅已结束的 PR 的完整列表。  

## <a name="version-01020022610"></a>版本 0.10.2002.2610

发行日期：2020 年 2 月 27 日

此版本包含以下各项：

- 新的量子机器学习库。有关详细信息，请参阅我们的 [QML 文档页](https://docs.microsoft.com/quantum/libraries/machine-learning/?view=qsharp-preview)
- IQ# Bug 修复。在加载 NuGet 包时，性能最多可提高 10-20 倍

有关[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[编译器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[运行时](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 的信息，请参阅已结束的 PR 的完整列表。  

## <a name="version-01020012831"></a>版本 0.10.2001.2831

发行日期：2020 年 1 月 29 日

此版本包含以下各项：

- 新的 Microsoft.Quantum.SDK NuGet 包。在创建新项目时，它将替换 Microsoft.Quantum.Development.Kit 包。 现有项目会继续支持 Microsoft.Quantum.Development.Kit NuGet 包。 
- 支持 Q# 编译器扩展，这些扩展由新的 Microsoft.Quantum.SDK NuGet 包提供支持。有关详细信息，请参阅 [GitHub 上的文档](https://github.com/microsoft/qsharp-compiler/tree/master/src/QuantumSdk#extending-the-q-compiler)、[编译器扩展示例](https://github.com/microsoft/qsharp-compiler/tree/master/examples/CompilerExtensions)和 [Q# 开发博客](https://devblogs.microsoft.com/qsharp/extending-the-q-compiler/)
- 添加了对 .NET Core 3.1 的支持。强烈建议安装版本 3.1.100，因为使用旧 .NET Core SDK 版本进行生成可能会导致问题
- Microsoft.Quantum.QsCompiler.Experimental 下提供新的编译器转换
- 在 IQ# 中将输出状态矢量作为 HTML 公开的新功能
- 针对 Hadamard 和 SWAP 测试向 Microsoft.Quantum.Characterization 添加了对 EstimateFrequencyA 的支持
- AmplitudeAmplification 命名空间现在使用 Q# 样式指南

有关[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[编译器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[运行时](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 的信息，请参阅已结束的 PR 的完整列表。  

## <a name="version-01019120501"></a>版本 0.10.1912.0501

发行日期：*2019 年 12 月 5 日*

此版本包含以下各项：

- 用于 Q# 单元测试的新测试属性，请在[此处](https://docs.microsoft.com/qsharp/api/qsharp/microsoft.quantum.diagnostics.test)参阅已更新 API 文档，并在[此处](xref:microsoft.quantum.guide.testingdebugging)参阅已更新的测试与调试指南
- 添加了在出现 Q # 程序执行错误时使用的堆栈跟踪
- 对 Visual Studio Code 中的断点的支持（由于 [OmniSharp C# Visual Studio Code 扩展](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)中的更新）

有关[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[编译器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[运行时](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 的信息，请参阅已结束的 PR 的完整列表。  

## <a name="version-01019111607"></a>版本 0.10.1911.1607

发行日期：*2019 年 11 月 17 日*

此版本包含以下各项：

- [Quantum Katas](https://github.com/Microsoft/QuantumKatas) 和 Jupyter 笔记本的性能修复

有关[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[编译器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[运行时](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 的信息，请参阅已结束的 PR 的完整列表。  


## <a name="version-0101911307"></a>版本 0.10.1911.307

发行日期：*2019 年 11 月 1 日*

此版本包含以下各项：

- 更新了 Visual Studio Code 和 Visual Studio 扩展，以便将语言服务器部署为独立可执行文件，从而消除了 .NET Core SDK 版本依赖项  
- 迁移到 .NET Core 3.0
- 对 Microsoft.Quantum.Simulation.Core.IOperationFactory 进行了中断性变更，引入了新的 `Fail` 方法。 它仅影响不扩展 SimulatorBase 的自定义模拟器。 有关更多详细信息，请[查看 GitHub 上的拉取请求](https://github.com/microsoft/qsharp-runtime/pull/59)。
- 对已弃用属性的新支持

有关[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[编译器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[运行时](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 的信息，请参阅已结束的 PR 的完整列表。  

## <a name="version-0919093002"></a>版本 0.9.1909.3002

发行日期：2019 年 9 月 30 日

此版本包含以下各项：

- 对 Visual Studio 2019（16.3 版本和更高版本）和 Visual Studio Code 中的 Q# 代码补全的新支持
- 量子添加器的新[量子 Kata](https://github.com/Microsoft/QuantumKatas)

有关[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[编译器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[运行时](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 的信息，请参阅已结束的 PR 的完整列表。  

## <a name="version-09-packagereference-0919082902"></a>版本 0.9 (PackageReference 0.9.1908.2902)

发行日期：2019 年 8 月 29 日

此版本包含以下各项：

- 对 Q# 中 [conjugation 语句](xref:microsoft.quantum.guide.operationsfunctions#conjugations)的新支持
- 编译器中新的代码操作，例如：“replace with”、“add documentation”和简单数组项更新
- 已将安装模板和新项目命令添加到 Visual Studio Code 扩展
- 添加了 ApplyIf 连结符的新变体，例如 [Microsoft.Quantum.Canon.ApplyIfOne](xref:microsoft.quantum.canon.applyifone)
- 已转换为 Jupyter Notebook 的其他[量子 Katas](https://github.com/Microsoft/QuantumKatas)
- Visual Studio 扩展现在需要 Visual Studio 2019

有关[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[编译器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[运行时](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 的信息，请参阅已结束的 PR 的完整列表。  

此处汇总了这些更改，以及有关升级现有程序的说明。  有关这些更改的详细信息，请参阅 [Q# 开发博客](https://devblogs.microsoft.com/qsharp)。

## <a name="version-08-packagereference-0819071701"></a>版本 0.8 (*PackageReference 0.8.1907.1701*)

发行日期：2019 年 7 月 12 日

此版本包含以下各项：

- 用于对数组进行切片的新索引位置，请参阅[语言参考](xref:microsoft.quantum.guide.expressions#array-slices)了解详情。
- [Microsoft 容器注册表](https://github.com/microsoft/ContainerRegistry)上托管的附加 Dockerfile，请参阅 [IQ# 存储库](https://github.com/microsoft/iqsharp/blob/master/README.md)了解详情
- [跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的中断性变更、配置设置更新、名称更改；请参阅 [.NET API 浏览器](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulatorconfiguration)了解更新后的名称。

有关[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)和[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)的信息，请参阅已结束的 PR 的完整列表。  

## <a name="version-07-packagereference-0719053109"></a>版本 0.7 (*PackageReference 0.7.1905.3109*)

发行日期：2019 年 5 月 31 日

此版本包含以下各项：
- Q# 语言的附加内容、 
- 化学库的更新、 
- 新的数字库。

有关[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)和[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)的信息，请参阅已结束的 PR 的完整列表。  

此处汇总了这些更改，以及有关升级现有程序的说明。  有关这些更改的详细信息，请参阅 [Q# 开发博客](https://devblogs.microsoft.com/qsharp)。

### <a name="q-language-syntax"></a>Q# 语言语法
此版本添加了新的 Q# 语言语法：
* 添加了[用户定义类型](xref:microsoft.quantum.guide.types#user-defined-types)的命名项。  
* 现可将用户定义类型构造函数用作函数。
* 在用户定义类型中添加了对 [copy-and-update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) 和 [apply-and-reassign](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols) 的支持。
* [repeat-until-success](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop) 循环的修复块现在是可选项。
* 我们现支持在函数中（而不是在操作中）使用 while 循环。

### <a name="library"></a>库 

此版本添加了数字库：详细了解如何[使用新的数字库](xref:microsoft.quantum.numerics.usage)并尝试[新的示例](https://github.com/microsoft/quantum/tree/master/Numerics)。  [PR #102](https://github.com/Microsoft/QuantumLibraries/pull/102)。  

此版本重新组织、扩展并更新了化学库：
* 改进组件模块化、可扩展性和常规代码清理。  [PR #58](https://github.com/microsoft/QuantumLibraries/pull/58)。
* 添加了对[多参考波函数](xref:microsoft.quantum.chemistry.concepts.multireference)（稀疏多参考波函数和单一耦合群集）的支持。  [PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110)。
* （谢谢！）[1QBit](https://1qbit.com) 参与者 ([@valentinS4t1qbit](https://github.com/ValentinS4t1qbit))：使用变分拟设的能量评估。 [PR #120](https://github.com/Microsoft/QuantumLibraries/pull/120)。
* 将 [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) 架构更新为新[版本 0.2](xref:microsoft.quantum.libraries.chemistry.schema.spec_v_0_2)，并添加单一耦合群集规范。 [问题 #65](https://github.com/microsoft/QuantumLibraries/issues/65)。
* 将 Python 互操作性添加到化学库函数。 尝试此[示例](https://github.com/microsoft/Quantum/tree/master/Chemistry/PythonIntegration)。 [问题 53](https://github.com/microsoft/QuantumLibraries/issues/53) [PR 110](https://github.com/Microsoft/QuantumLibraries/pull/110)。

## <a name="version-061905"></a>版本 0.6.1905

发行日期：2019 年 5 月 3 日

此版本包含以下各项：
- 更改 Q# 语言、 
- 重构量子开发工具包库、 
- 添加了新示例，以及 
- 修复 bug。  适用于[库](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)和[示例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)的多个已结束的 PR。  

此处汇总了这些更改，以及有关升级现有程序的说明。  有关这些更改的详细信息，请参阅 devblogs.microsoft.com/qsharp。

### <a name="q-language-syntax"></a>Q# 语言语法
此版本添加了新的 Q# 语言语法：
* 使用 `+` 运算符添加了[用于表示量子操作专用化的简单方式](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations)（控制和伴随）。  旧语法已弃用。  使用旧语法（例如 `: adjoint`）的程序将继续运行，但会生成编译时警告。  
* 添加了用于 [copy-and-update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) 的新运算符 `w/`，它可用于将数组创建表示为现有数组的修改。
* 添加了常用的 [apply-and-update 语句](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols)，例如 `+=` 和 `w/=`。
* 添加了一种用于在[开放式指令](xref:microsoft.quantum.guide.filestructure#open-directives)中指定命名空间短名称的方法。

在此版本中，我们不再允许在 set 语句的左侧指定数组元素。  这是因为该语法意味着数组在实际上是可变的，操作的结果始终是创建新数组并加以修改。  系统将生成编译器错误，建议使用新新的 copy-and-update 运算符 `w/` 来达到相同的结果。  

### <a name="library-restructuring"></a>库重构
此版本重新组织库，使它们的增长保持一致：
* 将 Microsoft.Quantum.Primitive 命名空间重命名为 Microsoft.Quantum.Intrinsic。  这些操作由目标计算机实现。  Microsoft.Quantum.Primitive 命名空间已弃用。  运行时警告将建议程序何时使用弃用的名称来调用操作和函数。

* 将 Microsoft.Quantum.Canon 包重命名为 Microsoft.Quantum.Standard。  此包中包含大多数 Q# 程序共用的命名空间。  这包括：  
    - Microsoft.Quantum.Canon，适合常见操作
    - Microsoft.Quantum.Arithmetic，适合常规算术操作
    - Microsoft.Quantum.Preparation，适合用于准备量子位状态的操作
    - Microsoft.Quantum.Simulation，适合模拟函数

进行此更改后，如果程序包含适用于 Microsoft.Quatum.Canon 命名空间的单个“open”语句，且引用了已移至其他三个新命名空间的操作，则可能会遇到生成错误。  为三个新的命名空间添加其他 open 语句是解决此问题的直接方法。  

* 已弃用几个命名空间，因为其中的操作已重新组织到其他命名空间。 使用这些命名空间的程序将继续运行，并且编译时警告将指示在其中定义操作的命名空间。  

* Microsoft.Quantum.Arithmetic 命名空间已标准化为使用 <xref:microsoft.quantum.arithmetic.littleendian> 用户定义类型。 需要转换为小端时，请使用函数 [BigEndianAsLittleEndian](xref:microsoft.quantum.arithmetic.bigendianaslittleendian)。  

* 几个可调用对象（函数和操作）的名称已更改，符合 [Q# 风格指南](xref:microsoft.quantum.contributing.style)。  旧的可调用对象的名称已弃用。  使用旧的可调用对象的程序将继续处理编译时警告。 

### <a name="new-samples"></a>新示例

我们已添加 [Q# 与 F# 驱动程序结合使用的示例](https://github.com/Microsoft/Quantum/pull/164)。  

谢谢你们： 在 http://github.com/Microsoft/Quantum 向我们的开放代码库发布内容的以下参与者。 这些内容极大地丰富了 Q# 代码的示例：

* Mathias Soeken ([@msoeken](https://github.com/msoeken))：Oracle 函数合成。 [PR #135](https://github.com/Microsoft/Quantum/pull/135)。

### <a name="migrating-existing-projects-to-061905"></a>将现有项目迁移到 0.6.1905。

请参阅[安装指南](xref:microsoft.quantum.install)，以更新 QDK。
  
如果现有 Q# 项目源自量子开发工具包 0.5 版，则下方介绍了将这些项目迁移到最新版本的步骤。

    1. 项目需要按顺序升级。  如果解决方案包含多个项目，请按引用顺序更新每个项目。
    2. 在命令行中，运行 `dotnet clean`，删除所有现有的二进制文件和中间文件。
    3. 在文本编辑器中，编辑 .csproj 文件，将所有“Microsoft.Quantum”`PackageReference` 的版本更改为版本 0.6.1904，并将“Microsoft.Quantum.Canon”包名称更改为“Microsoft.Quantum.Standard”，例如：

         ```xml
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.6.1905.301" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.6.1905.301" />
        ```
    4. 从命令行运行以下命令：`dotnet msbuild`  
    5. 运行此命令后，可能仍需要手动解决因上述更改所导致的错误。  在许多情况下，Visual Studio 或 Visual Studio Code 中的 IntelliSense 会报告这些错误。
        - 在 Visual Studio 2019 或 Visual Studio Code 中，打开项目的根文件夹或包含的解决方案。
        - 在编辑器中打开 .qs 文件后，输出窗口应显示 Q# 语言扩展的输出。
        - 成功加载项目后（输出窗口中会出现相应指示），打开每个文件并手动解决所有剩余问题。

> [!NOTE]
> * 对于0.6 版本，量子开发工具包附带的语言服务器不支持多个工作区。
> * 若要在 Visual Studio Code 中处理项目，请打开包含项目本身和所有引用项目的根文件夹。   
> * 若要在 Visual Studio 中处理解决方案，解决方案中包含的所有项目都需要位于解决方案所在的同一文件夹中，或位于其中一个子文件夹中。  
> * 不支持在迁移到 0.6 和更高版本的项目与使用较低版本的包的项目之间进行引用。

## <a name="version-051904"></a>版本 0.5.1904

发行日期：2019 年 4 月 15 日

此版本包含 bug 修复。


## <a name="version-051903"></a>版本 0.5.1903

发行日期：2019 年 3 月 27 日

此版本包含以下各项：

- 添加了对 Jupyter Notebook 的支持，可以更好地了解 Q#。  [查看新的 Jupyter Notebook 示例，并了解如何编写自己的 Notebooks](xref:microsoft.quantum.install)。 

- 将整数加法器算法添加到了量子 Canon 库中。  另请参阅[描述如何使用新的整数加法器](https://github.com/microsoft/Quantum/blob/master/samples/arithmetic/AdderExample.ipynb)的 Jupyter Notebook。

- 针对社区报告的 DumpRegister 问题的 bug 修复 ([#148](https://github.com/Microsoft/Quantum/issues/148))。

- 添加了从 [using 语句](xref:microsoft.quantum.guide.qubits#allocating-qubits)中返回的功能。

- 改版了[入门指南](xref:microsoft.quantum.install)。


## <a name="version-051902"></a>版本 0.5.1902

发行日期：2019 年 2 月 27 日

此版本包含以下各项：

- 添加了对跨平台 Python 主机的支持。  使用 Python 的 `qsharp` 包可以轻松地从 Python 内模拟 Q# 操作和函数。 了解有关 [Python 互操作性](xref:microsoft.quantum.install)的详细信息。 

- Visual Studio 和 Visual Studio Code 扩展现支持符号重命名（例如，函数和操作）。

- Visual Studio 扩展现可安装在 Visual Studio 2019 上。

## <a name="version-041901"></a>版本 0.4.1901

发行日期：2019 年 1 月 30 日

此版本包含以下各项：

- 添加了对新的基元类型 BigInt 的支持，该类型表示任意大小的有符号整数。  了解有关 [BigInt 类型](xref:microsoft.quantum.guide.types)的详细信息。
- 添加了新的 Toffoli 模拟器，这是一种特殊用途的快速模拟器，可模拟 X、CNOT 和多方控制 X 量子操作（具有大量的量子位）。  了解有关 [Toffoli 模拟器](xref:microsoft.quantum.machines.toffoli-simulator)的详细信息。
- 添加了一种简单的资源估计器，用于估计在量子计算机上运行给定的 Q# 操作实例所需的资源。  了解有关[资源估计器](xref:microsoft.quantum.machines.resources-estimator)的详细信息。


## <a name="version-0318112802"></a>版本 0.3.1811.2802

发行日期：2018 年 11 月 28 日

尽管 VS Code 扩展未使用它，但在与 `event-stream` NPM 包相关的 [扩展清除](https://code.visualstudio.com/blogs/2018/11/26/event-stream)过程中，它已被标记并从商城中删除。 此版本删除了所有可使扩展触发任何红色标记的运行时依赖项。

如果以前安装了该扩展，则需要访问 Visual Studio Marketplace 上[适用于 Visual Studio Code 的 Microsoft 量子开发工具包](vscode:extension/quantum.quantum-devkit-vscode)扩展并按“安装”，再次安装该扩展。 对此产生的不便，我们深表歉意。


## <a name="version-0318111511"></a>版本 0.3.1811.1511

发行日期：2018 年 11 月 20 日

此版本修复了阻止某些用户成功加载 Visual Studio 扩展的 bug。

## <a name="version-031811203"></a>版本 0.3.1811.203

发行日期：2018 年 11 月 2 日

此版本包含几个 bug 修复，其中包括：

* 调用 `DumpMachine` 可能会在某些情况下更改模拟器的状态。
* 删除了使用比 2.1.403 更低的 .NET Core 版本生成项目时的编译警告。
* 清理文档，特别是将鼠标悬停在 VS Code 或 Visual Studio 时所显示的工具提示。

## <a name="version-0318102508"></a>版本 0.3.1810.2508

发行日期：2018 年 10 月 29 日

此版本包含新的语言功能和改善的开发者体验：

* 此版本包括用于 Q# 的语言服务器，以及用于 Visual Studio 和 Visual Studio Code 的客户端集成。 这会启用一组新的 IntelliSense 功能，以及在键入时以波浪下划线的形式发出错误和警告的实时反馈。 
* 总体上看，此更新极大地改善了诊断消息，可以轻松地导航到诊断消息的准确范围，并在显示的悬停信息中提供更多详细信息。
* Q# 语言经扩展后，统一了开发者可以执行常见操作的方式和增强语言功能的方式，从而有效地表达量子计算。  此版本中的 Q# 语言进行了一些的重大更改。   

此版本还包括新的量子化学库：

* 该化学库包含新的 Hamiltonian 模拟功能，其中包括：
    - 任意偶数顺序的 Trotter–Suzuki 积分器，可提高模拟准确性。
    - 量子位化模拟技术，其中进行了特定于化学的优化，可降低 $T$-gate 复杂性。
* 引入了一种新的开源架构，称为 Broombridge 架构（该名称参考了被誉为 Hamiltonians 发源地的[地标](https://en.wikipedia.org/wiki/Broom_Bridge)），用于导入分子表示形式并对其进行模拟。
* 提供使用 Broombridge 架构定义的多个化学表示形式。  这些模型由一种开源的高性能计算化学工具 [NWChem](http://www.nwchem-sw.org/) 生成。
* 教程和示例介绍如何使用化学库和 Broombridge 数据模型执行以下操作：
    - 使用化学库构造简单的 Hamiltonians
    - 使用阶段估计直观显示氢化锂的基态能量和激发态能量。
    - 执行量子化学模拟的资源评估。
    - 估计 Broombridge 架构表示的分子的能级。
* 文档介绍如何使用 NWChem 生成其他化学模型，以使用 Q# 进行量子模拟。

了解有关[量子开发工具包化学库](xref:microsoft.quantum.chemistry.concepts.intro)的详细信息。

使用新的化学库，我们将库划分成新的 GitHub 存储库 [Microsoft/QuantumLibraries](https://github.com/Microsoft/QuantumLibraries)。  示例保留在 [Microsoft/Quantum](https://github.com/Microsoft/Quantum) 存储库中。  我们欢迎大家参与到这两个库的构建中！

此版本包括社区报告的问题对应的 bug 修复和功能：

* Intellisense for Q#？ ([UserVoice](https://quantum.uservoice.com/forums/906943/suggestions/32656918))。
* .qs 文件 ([UserVoice](https://quantum.uservoice.com/forums/906097/suggestions/32593049))。
* 当 if 语句中大括号缩写时，请改进错误消息 ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/34718518))。
* 支持在可变（重新）绑定上进行元组析构 ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/35020444))。
* 运行提供的 BitFlipCode 时出错 ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546))。
* H2SimulationGUI 有时会显示较大峰值 ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34668370))。

### <a name="community-contributions"></a>社区贡献

谢谢你们： 在 http://github.com/Microsoft/Quantum 向我们的开放代码库发布内容的以下参与者。 这些内容极大地丰富了 Q# 代码的示例：

* Rolf Huisman ([@RolfHuisman](https://github.com/RolfHuisman))：通过创建 QASM 到 Q# 的转换器，改善了 QASM/Q# 开发者的体验。 [PR #58](https://github.com/Microsoft/Quantum/pull/58)。

* Andrew Helwer ([@ahelwer](https://github.com/ahelwer))：提供了实现 CHSH 游戏的示例，该游戏是一个与非区域相关的量子游戏。  [PR #84](https://github.com/Microsoft/Quantum/pull/84)。

同样感谢 Rohit Gupta（[@guptarohit](https://github.com/guptarohit)，[PR #90](https://github.com/Microsoft/quantum/pull/90)）、Tanaka Takayoshi（[@tanaka-takayoshi](https://github.com/tanaka-takayoshi)，[PR #289](https://github.com/MicrosoftDocs/quantum-docs-pr/pull/289)），以及 Lee James O'Riordan（[@mlxd](https://github.com/mlxd)，[PR #96](https://github.com/Microsoft/Quantum/pull/96)），他们通过分类文档以及更正拼写和错误改善了我们所有人的内容！ 

## <a name="version-021809701"></a>版本 0.2.1809.701

发行日期：2018 年 9 月 10 日

此版本包括社区报告的问题对应的 bug 修复。 其中包括：

* 无法使用移位运算符 ([GitHub](https://github.com/Microsoft/Quantum/issues/75))。
* 打印到控制台时，`DumpMachine` / `DumpRegister` 在 `QCTraceSimulator` 上失败 ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34709680))。
* 允许分配 0 个量子位 ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34768069-allow-allocating-0-qubits))。
* `AssertQubitState` 需要显式 Complex() 调用 ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34713733-assertqubitstate-requires-explicit-complex-call))。
* `Measure` 操作始终在 macOS 上返回 `One` ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546))。

谢谢！ 

## <a name="version-0218063001"></a>版本 0.2.1806.3001

发行日期：2018 年 6 月 30 日

此版本只是对 [GitHub 上报告的 #48 问题](https://github.com/Microsoft/Quantum/issues/48)的快速修复（如果用户名包含空格，则 Q# 编译失败）。 在相应的新版本 (`0.2.1806.3001-preview`) 中遵循与 `0.2.1806.1503` 相同的更新说明。

## <a name="version-0218061503"></a>版本 0.2.1806.1503

发行日期：2018 年 6 月 22 日

此版本包含多项社区贡献，并改进了调试体验，提高了性能。  具体而言：

* 对 QuantumSimulator 目标计算机的小型和大型模拟进行性能改进。
* 改进了调试功能。
* 在 bug 修复、新的帮助程序函数、操作和新示例方面的社区贡献。

### <a name="performance-improvements"></a>性能改进

此更新包括对所有目标计算机的大量和少量量子位模拟的显著性能改进。  这种改进在量子开发工具包中的标准示例 H<sub>2</sub> 模拟中非常明显。

### <a name="improved-debugging-functionality"></a>改进了调试功能

此更新添加了新的调试功能：
* 添加了 @"microsoft.quantum.extensions.diagnostics.dumpmachine" 和 @"microsoft.quantum.extensions.diagnostics.dumpregister" 两个新操作，可在某个时间点输出有关目标量子计算机的波形函数信息。  
* 在 Visual Studio 中，在单个量子位测量到 $\ket{1}$ 的概率现在会自动显示在 QuantumSimulator 目标计算机的调试窗口中。
* 在 Visual Studio 中，改进了“自动”和“局部变量”调试窗口中变量属性的显示 。 

了解有关[测试和调试](xref:microsoft.quantum.guide.testingdebugging)的详细信息。

### <a name="community-contributions"></a>社区贡献

Q# 编码员社区正在不断发展，我们非常兴奋地看到第一个用户提供的库和示例已提交到 http://github.com/Microsoft/quantum 的开放代码库中。  非常感谢！ 感谢以下参与者：
* Mathias Soeken ([@msoeken](https://github.com/msoeken))：提供了一个定义基于转换的逻辑合成方法的示例，该方法可构造用于实现给定排列的 Toffoli 网络。 代码完全使用 Q# 函数和操作编写。  [PR #41](https://github.com/Microsoft/Quantum/pull/41)。
* RolfHuisman ([@RolfHuisman](https://github.com/RolfHuisman))：Microsoft MVP Rolf Huisman 提供了一个从 Q# 代码生成平面 QASM 代码的示例，用于不具有典型控制流的有限程序类和有限量子操作。 [PR #59](https://github.com/Microsoft/Quantum/pull/59)
* Sarah Kasier ([@crazy4pi314](https://github.com/crazy4pi314))：通过提交用于受控操作的库函数，帮助改进我们的代码库。 [PR #53](https://github.com/Microsoft/Quantum/pull/53)
* Jessica Lemieux ([@Lemj3111](https://github.com/Lemj3111))：修复 @"microsoft.quantum.canon.quantumphaseestimation" 并新建单元测试。  [PR #54](https://github.com/Microsoft/Quantum/pull/54)
* Tama McGlinn ([@TamaHobbit](https://github.com/TamaHobbit))：通过确保释放 QuantumSimulator 实例来清除 Teleportation 示例。 [PR #20](https://github.com/Microsoft/Quantum/pull/20)

此外，非常感谢你们： 来自商业工程服务团队的 Microsoft 软件工程师参与者，他们在黑客马拉松期间对文档进行了重要的更改。  他们作出的更改大大改善了我们所有人的清晰度和载入体验：
* Sascha Corti
* Mihaela Curmei
* John Donnelly
* Kirill Logachev
* Jan Pospisil
* Anita Ramanan
* Frances Tibble
* Alessandro Vozza

### <a name="update-existing-projects"></a>更新现有项目

此版本可完全向后兼容。 只需将项目中的 nuget 包更新为 `0.2.1806.1503-preview` 版本，并执行全部重新生成，即可确保重新生成所有中间文件。

在 Visual Studio 中，按照有关如何[更新包](https://docs.microsoft.com/nuget/tools/package-manager-ui#updating-a-package)的常规说明进行操作。

若要更新命令行的项目模板，请运行以下命令：
```
dotnet new -i "Microsoft.Quantum.ProjectTemplates::0.2.1806.1503-preview"
```

运行此命令后，使用 `dotnet new <project-type> -lang Q#` 创建的任何新项目将自动使用此版本的量子开发工具包。

若要更新现有项目以使用最新版本，请从每个项目的目录中运行以下命令：

```
dotnet add package Microsoft.Quantum.Development.Kit -v "0.2.1806.1503-preview"
dotnet add package Microsoft.Quantum.Canon -v "0.2.1806.1503-preview"
```

如果现有项目还使用 XUnit 集成进行单元测试，则也可使用类似的命令来更新该包：
```
dotnet add package Microsoft.Quantum.Xunit -v "0.2.1806.1503-preview"
```

根据测试项目所使用的 XUnit 版本，可能还需要将 XUnit 更新到 2.3.1：
```
dotnet add package xunit -v "2.3.1" 
```

更新后，请确保通过以下方式删除先前版本生成的所有临时文件：
```
dotnet clean 
```

### <a name="known-issues"></a>已知问题

未报告任何其他已知问题。


## <a name="version-0218022202"></a>版本 0.2.1802.2202

发行日期：2018 年 2 月 26 日

此版本支持在多个平台上开发、语言互操作和性能增强。 具体来说：

- 支持基于 macOS 和 Linux 的开发。 
- 兼容 .NET Core，包括支持跨平台的 Visual Studio Code。
- 量子开发工具包库的完整开放源代码许可证。
- 提高了需要 20 个或以上量子位的项目的模拟器性能。
- 可与 Python 语言（适用于 Windows 的预览版本）互操作。

### <a name="net-editions"></a>.NET 版本

.NET 平台具有两种不同的版本：随 Windows 提供的 .NET Framework，以及在 Windows、macOS 和 Linux 上提供的开源 .NET Core。
在此版本中，量子开发工具包的大部分内容作为 .NET Standard 的库提供，该库是 Framework 和 Core 共用的一组类。
这些库因此与 .NET Framework 或 .NET Core 的最新版本兼容。

因此，为了帮助确保使用量子开发工具包编写的项目尽可能成为可移植项目，我们建议使用量子开发工具包编写的库项目面向 .NET Standard，而控制台应用程序面向 .NET Core。
由于以前版本的量子开发工具包仅支持 .NET Framework，因此可能需要迁移现有项目；有关如何执行此操作的详细信息，请参阅以下内容。

### <a name="project-migration"></a>项目迁移

只要未更新使用较低版本的量子开发工具包创建的项目中所用的 NuGet 包，则该项目仍可正常工作。 若要将现有代码迁移到新版本，请执行以下步骤：
1. 使用合适类型的 Q# 项目模板（应用程序、库或测试项目）创建新的 .NET Core 项目。
2. 将旧项目中的现有 .qs 和 .cs/.fs 文件复制到新项目（使用“添加”>“现有项”）。 请勿复制 AssemblyInfo.cs 文件。
3. 生成并运行新项目。

请注意，Microsoft.Quantum.Canon 命名空间的 RandomWalkPhaseEstimation 操作已移动到 [Microsoft/Quantum-NC](https://github.com/microsoft/quantum-nc) 存储库中的 Microsoft.Research.Quantum.RandomWalkPhaseEstimation 命名空间。

### <a name="known-issues"></a>已知问题

- `dotnet test` 的 `--filter` 选项无法正常用于使用 Q# 编写的测试。
  因此，无法在 Visual Studio Code 中运行单个单元测试；建议在命令行中使用 `dotnet test` 重新运行所有测试。

## <a name="version-0118011707"></a>版本 0.1.1801.1707

发行日期：2018 年 1 月 18 日

此版本修复了社区报告的一些问题。 也就是说，

- 模拟器现适用于不支持 AVX 的早期 CPU。
- 区域十进制设置不会导致 Q# 分析器发生故障。
- `SignD` 基元操作现返回 `Int`，而不是 `Double`。


## <a name="version-011712901"></a>版本 0.1.1712.901

发行日期：2017 年 12 月 11 日

### <a name="known-issues"></a>已知问题

#### <a name="hardware-and-software-requirements"></a>硬件和软件要求

- 量子开发工具包随附的模拟器需要安装 64 位的 Microsoft Windows 才能运行。
- Microsoft 的量子模拟器与量子开发工具包一起安装，利用高级矢量扩展 (AVX)，并且需要支持 AVX 的 CPU。 2011 年 1 季度 (Sandy Bridge) 或之后推出的 Intel 处理器支持 AVX。 我们正在评估对早期 CPU 的支持，稍后会公布详细信息。

#### <a name="project-creation"></a>项目创建

- 创建将使用 Q# 的解决方案 (.sln) 时，解决方案所在的目录必须高于解决方案中每个项目 (.csproj)。 若要新建解决方案，请确保选中“新建项目”对话框中的“创建解决方案的目录”复选框。 如果未能创建，则需要手动安装量子开发工具包 NuGet 包。

#### <a name="q"></a>Q#

- Intellisense 不显示 Q# 代码的正确错误。 请确保在 Visual Studio 错误列表中显示生成错误，以查看正确的 Q# 错误。 另请注意，在完成生成之前不会显示 Q# 错误。
- 在部分应用程序中使用可变数组可能导致意外的行为。
- 将不可变数组绑定到可变数组（令 a = b，其中 b 是可变数组）可能会导致意外的行为。
- 分析、代码覆盖率和其他 VS 插件可能不会始终准确地统计 Q# 行和块。
- Q# 编译器不会验证内插字符串。 可以通过拼写错误的变量名或在 Q# 内插字符串中使用表达式，来创建 C# 编译错误。

#### <a name="simulation"></a>模拟

- 量子模拟器使用 OpenMP 并行化所需的线性代数。 OpenMP 默认使用所有可用的硬件线程，这意味着具有少量的量子位的程序通常运行缓慢，因为所需的协调远多于实际工作。 通过将环境变量 OMP_NUM_THREADS 设置为较小数值，可修复此故障。 作为非常粗略的经验法则，1 个线程最多可以容纳约 4 个量子位，然后每个量子位最好增加一个线程，但这在很大程度上取决于你的算法。

#### <a name="debugging"></a>调试

- F11（单步执行）在 Q# 代码中不起作用。
- 在断点处暂停或单步暂停时，Q# 代码中的代码突出显示有时并不准确。 虽然系统会突出显示正确的行，但有时突出显示将从行中不正确的列开始和结束。

#### <a name="testing"></a>测试

- 必须在 64 位模式下执行测试。 如果测试失败，并出现 BadImageFormatException，请转到“测试”菜单，依次选择“测试设置”>“默认处理器体系结构”>“X64”。
- 有些测试需要很长的运行时间，可能需要 5 分钟，具体取决于你的计算机。 这是正常的，因为有些测试使用超过 20 个量子位；我们目前最大的测试可运行 23 个量子位。

#### <a name="samples"></a>示例

- 在某些计算机上，除非将环境变量 OMP_NUM_THREADS 设置为“1”，否则一些小样本可能会运行缓慢。 另请参见“模拟”下的发行说明。

#### <a name="libraries"></a>库

- 有一个隐含的假设，即以不同的参数传递给操作的量子位都是不同的。 例如，所有库操作（和所有模拟器）都假定传递给受控 NOT 的两个量子位是不同的量子位。 违反此假设可能会导致发生无法预料的意外情况。 可以使用量子计算机跟踪器模拟器对此进行测试。
- Microsoft.Quantum.Bind 函数可能无法在所有情况下都按预期方式运行。
- 在 Microsoft.Quantum.Extensions.Math 命名空间中，尽管基础 System.Math.Sign 函数始终返回整数，但 SignD 函数返回 Double 类型而非 Int 类型。 可以安全地将结果与 1.0、-1.0 和 0.0 进行比较，因为这些双精度值均具有精确的二进制表示形式。
