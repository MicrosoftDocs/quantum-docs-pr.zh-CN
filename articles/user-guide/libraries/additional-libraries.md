---
title: 使用其他 Q# 库
description: 了解如何将其他 Q# 库添加到量程应用程序。
author: cgranade
ms.author: chgranad
ms.date: 06/30/2020
ms.topic: article
uid: microsoft.quantum.libraries.using
no-loc:
- Q#
- $$v
ms.openlocfilehash: 39bf7dc52f4670a6e4536efc437d001c96f9584a
ms.sourcegitcommit: 11bd357baeb6ab53a402882979e75964d0869b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2020
ms.locfileid: "88992133"
---
# <a name="using-additional-no-locq-libraries"></a>使用其他 Q# 库

量程开发工具包通过可添加到项目中的 _NuGet 包_ 提供附加的特定于域的功能 Q# 。

| Q# 类库  | NuGet 包 | 说明 |
|---------|---------|--------|
| [Q# 标准库](xref:microsoft.quantum.libraries.standard.intro) | [**Microsoft 量子. 标准版**](https://www.nuget.org/packages/Microsoft.Quantum.Standard) | 默认包括 |
| [量子化学库](xref:microsoft.quantum.chemistry.concepts.intro) | [**Microsoft.Quantum.Chemistry**](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) | |
| [量子数字库](xref:microsoft.quantum.numerics.intro) | [**Microsoft. 量子**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) | |
| [量子机器学习库](xref:microsoft.quantum.libraries.machine-learning.intro) | [**Microsoft.Quantum.MachineLearning**](https://www.nuget.org/packages/Microsoft.Quantum.MachineLearning) | |

一旦您安装了用于您喜欢的环境和主机语言的量程开发工具包，就可以轻松地将库添加到各个 Q# 项目，而无需进行任何进一步的安装。

> [!NOTE]
> 某些 Q# 库可以很好地与你的 Q# 程序或与主机应用程序集成的其他工具一起工作。
> 例如，[化学库安装说明](xref:microsoft.quantum.chemistry.concepts.installation)介绍了如何将 NWChem [ **Microsoft.Quantum.Chemistry**包](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry)与计算化学平台一起使用，以及如何安装 `qdk-chem` 用于处理量程化学数据的命令行工具。

## <a name="no-locq-applications-or-net-interopability"></a>[Q# 应用程序或 .NET interopability](#tab/tabid-csproj)

**命令提示符或 Visual Studio Code：** 使用命令提示符自行或从 Visual Studio Code 中，你可以使用 `dotnet` 命令将 NuGet 包引用添加到你的项目。
例如，若要添加 [**Microsoft 量子**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) 包，请运行以下命令：

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```

**Visual Studio：** 如果你使用的是 Visual Studio 2019 或更高版本，则可以 Q# 使用 NuGet 包管理器添加其他包。
若要加载包： 
1. 在 Visual Studio 中打开项目后，从 "**项目**" 菜单中选择 "**管理 NuGet 包 ...** "。

2. 单击 " **浏览**"，选择 " **包括预发行** 版"，然后搜索包名称 ""。 这将列出可供下载的包。

3. 将鼠标悬停在 **"..." 上，** 并单击版本号右侧的向下箭头，以安装数字包。

有关更多详细信息，请参阅 [包管理器 UI 指南](https://docs.microsoft.com/nuget/tools/package-manager-ui)。

或者，你可以使用包管理器控制台通过命令行接口将数字库添加到你的项目。

![在命令提示符下使用包管理器控制台](~/media/vs2017-nuget-console-menu.png)

从包管理器控制台中，运行以下内容：

```
Install-Package Microsoft.Quantum.Numerics
```

有关更多详细信息，请参阅 [包管理器控制台指南](https://docs.microsoft.com/nuget/tools/package-manager-console)。

## <a name="ino-locq-notebooks"></a>[我的 Q# 笔记本](#tab/tabid-notebook)

你可以 Q# 使用[ `%package` 魔棒命令](xref:microsoft.quantum.iqsharp.magic-ref.package)使其他包可用于我的笔记本。
例如，若要添加 [**Microsoft 量子**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) 包以便在 I 笔记本中使用 Q# ，请在笔记本单元中运行以下命令：

```
%package Microsoft.Quantum.Numerics
```

在此命令之后，包可用于笔记本中的任何单元。
若要使包可从 Q# 当前工作区中的代码使用，请在添加包后重新加载工作区：

```
%workspace reload
```

## <a name="python-interoperability"></a>[Python 互操作性](#tab/tabid-python)


可以通过使用方法，使其他包在 Python 主机程序中可供使用 [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages) 。
例如，若要添加要在 I 笔记本中使用的 [**Microsoft 量子**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) 包 Q# ，请运行以下 Python 代码：

```python
import qsharp
qsharp.packages.add("Microsoft.Quantum.Numerics")
```

执行此命令后，包将可供 Q# 使用编译的任何代码使用 `qsharp.compile` 。
若要使包可从 Q# 当前工作区中的代码使用，请在添加包后重新加载工作区：

```python
qsharp.reload()
```

***
