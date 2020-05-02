---
title: 使用 Q# + C# 进行开发
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 5bcb036b0b32e64d43f90e9a068d9dcc237890ba
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680168"
---
# <a name="using-q-with-c-and-f"></a>对 C\#和 F 使用 Q #\#

Q # 旨在与 .NET 语言（如 c # 和 F #）一起正常运行。
在本指南中，我们将演示如何将 Q # 与用 .NET 语言编写的主机程序结合使用。

## <a name="prerequisites"></a>先决条件

- 安装用于[Q # 命令行项目](xref:microsoft.quantum.install.standalone)的量程开发工具包。

## <a name="creating-a-q-library-and-a-net-host"></a>创建 Q # 库和 .NET 主机

第一步是为你的 Q # 库创建项目，并为将调用到你的 Q # 库中定义的操作和函数的 .NET 主机创建项目。

### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

- 创建新的 Q # 库
  - 中转到 "**文件** -> " "**新建** -> **项目**"
  - 在搜索框中键入 "Q #"
  - 选择**Q # 库**
  - 选择 **“下一步”**。
  - 选择库的名称和位置
  - 请确保未**选中**"将项目和解决方案放在同一目录中"
  - 选择**创建**
- 创建新的 c # 或 F # 宿主程序
  - 中转到**文件**→**新建**→**项目**
  - 为 c # 或 F 选择 "控制台应用（.NET Core"） "#
  - 选择 **“下一步”**。
  - 在 "*解决方案*" 下，选择 "添加到解决方案"
  - 选择主机程序的名称
  - 选择**创建**

### <a name="visual-studio-code-or-command-line"></a>[Visual Studio Code 或命令行](#tab/tabid-cmdline)

- 创建新的 Q # 库

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- 创建新的 c # 或 F # 控制台项目

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- 添加你的 Q # 库作为主机程序的引用

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- 可有可无为这两个项目创建解决方案

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a>从 .NET 调入 Q #

按照上述说明设置项目后，可以从 .NET 控制台应用程序调入 Q #。
Q # 编译器将为每个 Q # 操作和函数创建 .NET 类，使你能够在模拟器上运行量程程序。

例如， [.net 互操作性示例](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)包含以下 Q # 操作的示例：

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

若要在量程模拟器上从 .NET 调用此操作，可以使用由`Run` Q # 编译器`RunAlgorithm`生成的 .net 类的方法：

### <a name="c"></a>[C#](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[果#](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="whats-next"></a>后续步骤

现在，你已为 Q # 命令行程序设置了量子开发工具包，并且为了与 .NET 互操作，你可以编写并运行[第一个量程程序](xref:microsoft.quantum.write-program)。
