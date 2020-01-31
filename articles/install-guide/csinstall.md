---
title: '用 Q # + 开发C#'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 1fd829c684502092bb7491b0f46b5f690320c941
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831012"
---
# <a name="develop-with-q--c"></a>用 Q # + 开发C#

安装 QDK 以开发C#主机程序以调用 Q # 操作。

Q # 构建为适用于 .NET 语言（特别是C#）。 可以在不同的开发环境中使用此配对：

- [使用 Visual Studio C#的 Q # + （Windows）](#VS)
- [使用 Visual Studio Code 的C# Q # + （Windows、Linux 和 Mac）](#VSC)
- [使用 `dotnet` 命令C#行工具的 Q # +](#command)

## 使用 Visual Studio 通过 Q C# # + 进行开发<a name="VS"></a>

Visual Studio 提供了一个用于开发 Q # 程序的丰富环境。 Q # Visual Studio 扩展包含用于 Q # 文件和项目的模板，以及语法突出显示、代码完成和 IntelliSense 支持。


1. 必备组件

    - [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3，启用了 .NET Core 跨平台开发工作负载。

1. 安装 Q# Visual Studio 扩展

    - 下载并安装[Visual Studio 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)

1. 通过创建 `Hello World` 应用程序来验证安装

    - 创建新的 Q# 应用程序

        - 转到“文件” -> “新建” -> “项目”
        - 在搜索框中键入 `Q#`
        - 选择“Q# 应用程序”
        - 选择“下一步”
        - 为应用程序选择名称和位置
        - 选择“创建”

    - 检查项目

        应该会看到已创建两个文件：`Driver.cs`，它是 C# 主机应用程序；以及 `Operation.qs`，它是定义将消息打印到控制台的简单操作的 Q# 程序。

    - 运行应用程序

        - 选择“调试” -> “在不调试的情况下启动”
        - 应该会看到打印到控制台窗口的文本 `Hello quantum world!`。

> [!NOTE]
> * 如果一个 Visual Studio 解决方案中具有多个项目，解决方案中包含的所有项目都需要位于解决方案所在的同一文件夹中，或位于其中一个子文件夹中。  

## 使用 Q # + C#进行开发 Visual Studio Code<a name="VSC"></a>

Visual Studio Code （VS Code）提供了一个丰富的环境，用于在 Windows、Linux 和 Mac 上开发 Q # 程序。  Q # VS Code 扩展包括对 Q # 语法突出显示、代码完成和 Q # 代码片段的支持。

1. 必备组件

   - [VS Code](https://code.visualstudio.com/download)
   - [.NET Core SDK 3.1 或更高版本](https://www.microsoft.com/net/download)

1. 安装量子 VS Code 扩展

    - 安装 [VS Code 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)

1. 安装量子项目模板：

   - 转到“视图” -> “命令面板”
   - 选择**Q #：安装项目模板**

    现已安装量子开发工具包，并且可以在自己的应用程序和库中使用。

1. 通过创建 `Hello World` 应用程序来验证安装

    - 创建新项目：

        - 转到“视图” -> “命令面板”
        - 选择**Q #：创建新项目**
        - 选择**独立控制台应用程序**
        - 导航到要在其中创建应用程序的文件系统上的位置
        - 创建项目后，单击“打开新项目...”按钮

    - 如果尚未安装 VS Code 的C#扩展，将显示一个弹出窗口。 安装扩展。 

    - 运行应用程序：

        - 中转到**终端** -> **新终端**
        - 输入 `dotnet run`
        - 应在输出窗口 `Hello quantum world!` 中看到以下文本


> [!NOTE]
> * Visual Studio Code 扩展当前不支持具有多个根文件夹的工作区。 如果一个 VS Code 工作区中具有多个项目，则所有项目都必须包含在同一个根文件夹中。

## 使用 `dotnet` 命令行工具C#通过 Q # + 进行开发<a name="command"></a>

当然，只需安装 .NET Core SDK 和 QDK 项目模板，就可以从命令行生成和运行 Q# 程序。 

1. 必备组件

    - [.NET Core SDK 3.1 或更高版本](https://www.microsoft.com/net/download)

1. 安装适用于 .NET 的量子项目模板

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    现已安装量子开发工具包，并且可以在自己的应用程序和库中使用。

1. 通过创建 `Hello World` 应用程序来验证安装

    - 创建新应用程序

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - 导航到新的应用程序目录

       ```bash
       cd runSayHello
       ```

    应该会看到已创建两个文件，以及应用程序的项目文件：Q# 文件 (`Operation.qs`) 和 C# 主机文件 (`Driver.cs`)。

    - 运行应用程序

        ```bash
        dotnet run
        ```

        应该会看到以下输出：`Hello quantum world!`

    
## <a name="whats-next"></a>还有什么？

在首选环境中安装量子开发工具包后，可以编写并运行[第一个量子程序](xref:microsoft.quantum.write-program)。
