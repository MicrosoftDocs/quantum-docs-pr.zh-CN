---
title: Microsoft 量程数字库-安装和验证
description: 了解如何向 Visual Studio 2019 或更高版本安装添加 Microsoft 量程数字库。
author: thomashaener
ms.author: thhaner
ms.date: 05/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: cb0d00a509b3986b605dd7f15f9bccc0661bb894
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906332"
---
# <a name="numerics-library-installation-and-validation"></a>数字库安装和验证

量程开发工具包通过[`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet 包提供对数值型功能的支持。

**Visual Studio > = 2019：** 如果使用的是 Visual Studio 2019 或更高版本，则可以使用 NuGet 包管理器添加数字包。
为此，请选择 "管理 NuGet 包 ..."从 Visual Studio 中的 "项目" 菜单项。

从 "浏览" 选项卡中，搜索包名称 ""。

> [!NOTE]
> 请确保 "包括预发行版"

这将列出可供下载的包。
如果将鼠标悬停在 ""，则会显示版本号右侧的向下箭头。
单击箭头以便安装数字包。

有关更多详细信息，请参阅[包管理器 UI 指南](https://docs.microsoft.com/nuget/tools/package-manager-ui)。

或者，你可以使用包管理器控制台通过命令行接口将数字库添加到你的项目。

![在命令行中使用程序包管理器控制台](../../media/vs2017-nuget-console-menu.png)

从包管理器控制台中，运行以下内容：

```
Install-Package Microsoft.Quantum.Numerics
```

有关更多详细信息，请参阅[包管理器控制台指南](https://docs.microsoft.com/nuget/tools/package-manager-console)。

**命令行或 Visual Studio Code：** 你可以使用命令行自己使用命令行，也可以从 Visual Studio Code 中，使用 `dotnet` 命令将 NuGet 包引用添加到你的项目：

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a>验证安装

与量程开发工具包的其余部分一样，数字库附带了有助于尽快入门的示例。
若要使用这些示例测试安装，请克隆[主示例存储库](https://github.com/Microsoft/Quantum)，然后运行其中一个示例。

运行[`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd)示例：

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics/CustomModAdd
dotnet run
```
