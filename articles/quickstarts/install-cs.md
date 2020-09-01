---
title: 使用 Q# 和 .NET 进行开发
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 24318380e0e63957a51961762a33446fe0121b21
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863673"
---
# <a name="develop-with-no-locq-and-net"></a>使用 Q# 和 .NET 进行开发

Q# 能够很好地与 C# 和 F# 等 .NET 语言配合运行。
在本指南中，我们将演示如何将 Q# 与采用 .NET 语言编写的主机程序结合使用。

首先，我们将创建 Q# 应用程序和 .NET 主机，然后演示如何从主机调用 Q#。

## <a name="prerequisites"></a>先决条件

- 安装 Quantum 开发工具包，将它[用于 Q# 项目](xref:microsoft.quantum.install.standalone)。

## <a name="creating-a-no-locq-library-and-a-net-host"></a>创建 Q# 库和 .NET 主机

第一步是为 Q# 库以及将要调入到（Q# 库中定义的）操作和函数的 .NET 主机创建项目。

按照你的开发环境所对应的选项卡中的说明操作。
如果使用的是编辑器而不是 Visual Studio 或 VS Code，只需按照命令提示符步骤操作即可。

### <a name="visual-studio-code-or-command-prompt"></a>[Visual Studio Code 或命令提示符](#tab/tabid-cmdline)

- 创建新的 Q# 库

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- 创建新的 C# 或 F# 控制台项目

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- 从主机程序添加 Q# 库作为参考

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- [可选] 为这两个项目创建解决方案

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

- 创建新的 Q# 库
  - 转到“文件” -> “新建” -> “项目”  
  - 在搜索框中键入“Q#”
  - 选择“Q# 库”
  - 选择“下一步”
  - 为库选择名称和位置
  - 请确保未选中“将项目和解决方案置于同一目录中”
  - 选择“创建”
- 创建新的 C# 或 F# 主机程序
  - 转到“文件”→“新建”→“项目”  
  - 选择适用于 C# 或 F# 的“控制台应用(.NET Core)”
  - 选择“下一步”
  - 在“解决方案”下，选择“添加到解决方案”
  - 为主机程序选择一个名称
  - 选择“创建”

***

## <a name="calling-into-no-locq-from-net"></a>从 .NET 调用 Q#

按照上述说明设置项目后，可从 .NET 控制台应用程序调用 Q#。
Q# 编译器将为每个 Q# 操作和函数创建 .NET 类，使你能够在模拟器上运行量子程序。

例如，[.NET 互操作性示例](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)包含以下 Q# 操作的示例：

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

若要在量子模拟器上从 .NET 调用此操作，可以使用由 Q# 编译器生成的 `RunAlgorithm` .NET 类的 `Run` 方法：

### <a name="c"></a>[C#](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[F#](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a>后续步骤

现在，你已为 Q# 应用程序和与 .NET 的互操作设置了 Quantum 开发工具包，接下来可编写并运行你的[第一个量子程序](xref:microsoft.quantum.quickstarts.qrng)。
