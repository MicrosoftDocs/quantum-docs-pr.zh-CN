---
title: 使用 Q# 应用程序进行开发
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: a630b2307f5d95321fb26f480d7a441ddba846fc
ms.sourcegitcommit: d6ac6f4345be0dd68f1bcd944f44b08e7a3cf346
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "89358252"
---
# <a name="develop-with-no-locq-applications"></a>使用 Q# 应用程序进行开发

Q# 程序可自己执行，无需采用 C#、F# 或 Python 等主机语言的驱动程序。

## <a name="prerequisites"></a>先决条件

- [.NET Core SDK 3.1 或更高版本](https://www.microsoft.com/net/download)

## <a name="installation"></a>安装

在任何 IDE 中构建 Q# 应用程序时，建议使用 Visual Studio Code (VS Code) 或 Visual Studio IDE 在本地开发 Q# 应用程序。 若要通过 Web 浏览器在云中开发，建议使用 Visual Studio Codespaces。 在这些环境中开发涉及到丰富的 QDK 扩展功能，其中包括警告、语法突出显示和项目模板等。 

配置 VS Code：

1. 下载并安装 [VS Code](https://code.visualstudio.com/download)（Windows、Linux 和 Mac）。
2. 安装[适用于 VS Code 的 Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)。

配置 Visual Studio:

1. 下载并安装 [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 或更高版本，并启用 .NET Core 跨平台开发工作负载。
2. 下载并安装 [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)。

若要配置 Visual Studio Codespaces：

1. 创建 [Azure 帐户](https://azure.microsoft.com/free/)。
2. 创建一个 Codespaces 环境。 请按照[快速入门指南](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser)操作。 创建 Codespace 时，建议在“Git 存储库”中输入 `microsoft/Quantum` 来加载 QDK 特定的设置。
3. 现可启动新环境，通过 [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments) 在浏览器中开始开发。 或者，可使用 VS Code 的本地安装并将 Codespaces 用作[远程环境](https://docs.microsoft.com/visualstudio/online/how-to/vscode)。


若要为另一环境安装 QDK，请在命令提示符处输入：

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-no-locq"></a>使用 Q# 进行开发

按照你的环境所对应的选项卡上的说明操作。

### <a name="vs-code"></a>[VS Code](#tab/tabid-vscode)

创建新项目：

1. 单击“查看” -> “命令面板” ，然后选择“Q#:Create New Project”。
2. 单击“独立控制台应用程序”。
3. 导航到项目的保存位置，然后单击“创建项目”。
4. 成功创建项目后，单击右下方的“打开新项目…”。
        
检查项目。 你应该会看到一个名为 `Program.qs` 的源文件，该文件是一个 Q# 程序，用于定义将消息输出到控制台的简单操作。

运行应用程序：
1. 单击“终端” -> “新终端” 。
2. 在终端提示符下，输入 `dotnet run`。
3. 应在输出窗口 `Hello quantum world!` 中看到以下文本


> [!NOTE]
> VS Code Q# 扩展当前不支持具有多个根文件夹的工作区。 如果一个 VS Code 工作区中具有多个项目，则所有项目都必须包含在同一个根文件夹中。

### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs)

创建 Q# `Hello World` 应用程序来验证 Visual Studio 安装。

若要创建新的 Q# 应用程序：
1. 打开 Visual Studio，单击“文件” -> “新建” -> “项目”  。
2. 在“搜索”框中键入 `Q#`，选择“Q# 应用程序”，然后单击“下一步” 。
3. 输入应用程序的“名称”和“位置”，然后单击“创建”。


检查项目。 你应该会看到一个名为 `Program.qs` 的源文件，该文件是一个 Q# 程序，用于定义将消息输出到控制台的简单操作。

运行应用程序：
1. 选择“调试” -> “在不调试的情况下启动”。
2. 应该会看到打印到控制台窗口的文本 `Hello quantum world!`。

> [!NOTE]
> 如果一个 Visual Studio 解决方案中具有多个项目，解决方案中包含的所有项目都需要位于解决方案所在的同一文件夹中，或位于其中一个子文件夹中。  

### <a name="other-editors-with-the-command-prompt"></a>[其他使用命令提示符的编辑器](#tab/tabid-cmdline)

创建 Q# `Hello World` 应用程序来验证安装项。

1. 安装项目模板。

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. 创建新的应用程序：
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. 导航到应用程序目录：
    ```dotnetcli
    cd runSayHello
    ```

    该目录现在应该会包含一个 `Program.qs` 文件，它是 Q# 程序，用于定义将消息输出到控制台的简单操作。 你可使用文本编辑器来修改此模板，并用你自己的量子应用程序来覆盖它。 

1. 运行该程序：
    ```dotnetcli
    dotnet run
    ```

1. 应会看到以下输出文本：`Hello quantum world!`

***

## <a name="next-steps"></a>后续步骤

在首选环境中安装量子开发工具包后，可以编写并运行[第一个量子程序](xref:microsoft.quantum.quickstarts.qrng)。
