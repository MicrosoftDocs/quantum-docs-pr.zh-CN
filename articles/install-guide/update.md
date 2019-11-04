---
title: 了解如何更新 Microsoft Quantum Development Kit （QDK）
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: ebf1f15d65a12c921cd3f04e4111d463d1060f8e
ms.sourcegitcommit: c93fea5980d1d46fbda1e7c7153831b9337134bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2019
ms.locfileid: "73463280"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>更新 Microsoft Quantum Development Kit （QDK）

了解如何将 Microsoft Quantum Development Kit （QDK）更新到最新版本。

本文假设已安装 QDK。 如果你是首次安装，请参阅[安装指南](xref:microsoft.quantum.install)。


## <a name="updating-q-projects"></a>更新 Q # 项目 

1. 首先，安装最新版本的[.NET Core SDK 3.0](https://dotnet.microsoft.com/download) ，并在命令提示符下运行以下命令：
```bash
dotnet --version
```
 验证输出是否为3.0.100 或更高版本，按照以下说明操作，具体取决于您的设置。

### <a name="in-visual-studio"></a>在 Visual Studio 中
 
 1. 更新到最新版本的 Visual Studio 2019，请参阅[此处](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019)了解相关说明
 2. 在 Visual Studio 中打开解决方案
 3. 从菜单中选择 "生成 > 清理解决方案" 
 4. 将每个 .csproj 文件中[的目标框架更新](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework)为 netcoreapp 3.0 （如果它是库项目，则更新 netstandard 2.1）
 5. 保存并关闭解决方案中的所有文件
 6. > 命令行 > 选择工具开发人员命令提示
 7. 对于解决方案中的每个项目，请运行以下命令：
 ```bash
 dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
 ```
如果你的项目使用任何其他的 Microsoft 量子包，也请对其运行该命令。 
 8. 关闭命令提示符并选择 "生成 > 生成解决方案" （*请勿选择*"重新生成解决方案"，因为重新生成操作最初会失败）

### <a name="in-visual-studio-code"></a>在 Visual Studio Code

1. 在 Visual Studio Code 中，打开包含要更新项目的文件夹
1. 选择终端 > 新终端
1. 按照使用命令行进行更新的说明进行操作

### <a name="using-the-command-line"></a>使用命令行

1. 导航到包含项目文件的文件夹
2. 运行以下命令：
```bash
dotnet clean [project_name].csproj
```

3. 将每个 .csproj 文件中[的目标框架更新](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)为 netcoreapp 3.0 （如果它是库项目，则更新 netstandard 2.1）
4. 运行以下命令：
```bash
dotnet add package Microsoft.Quantum.Development.Kit
```
如果你的项目使用任何其他的 Microsoft 量子包，也请对其运行该命令。

5. 保存并关闭所有文件
6. 为每个项目依赖项重复1-4，然后导航回到包含主项目的文件夹，然后运行：
```bash
dotnet build [project_name].csproj
```

## <a name="update-iq-for-python"></a>更新适用于 Python 的 IQ #

1. 更新 `iqsharp` 内核

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. 验证 `iqsharp` 版本

    ```bash
    dotnet iqsharp --version
    ```

    应该会看到以下输出：

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```

1. 更新 `qsharp` 包

    ```bash
    pip install qsharp --upgrade
    ```

1. 验证 `qsharp` 版本

    ```bash
    pip show qsharp
    ```

    应该会看到以下输出：

    ```bash
    Name: qsharp
    Version: 0.10.1911.307
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```
1. 从 `.qs` 文件的位置运行以下命令
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

1. 你现在可以使用更新的 QDK 版本来运行现有的量程程序。

## <a name="update-iq-for-jupyter-notebooks"></a>更新适用于 Jupyter 笔记本的 IQ #

1. 更新 `iqsharp` 内核

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. 验证 `iqsharp` 版本

    ```bash
    dotnet iqsharp --version
    ```

    应该会看到以下输出：

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```
1. 在 Jupyter Notebook 中的单元格上运行以下命令：
    ```
    %workspace reload
    ```

1. 你现在可以打开现有的 Jupyter 笔记本，并使用更新的 QDK 运行它。

## <a name="update-visual-studio-qdk-extension"></a>更新 Visual Studio QDK 扩展

1. 更新 Q # Visual Studio 扩展

    - Visual Studio 会提示你接受对[量程 Visual Studio 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)的更新
    - 接受更新

    > [!NOTE]
    > 项目模板将更新为扩展。 更新的模板仅适用于新创建的项目。 更新扩展时，不会更新现有项目的代码。

## <a name="update-vs-code-qdk-extension"></a>更新 VS Code QDK 扩展

1. 更新量程 VS Code 扩展

    - 重新启动 VS Code
    - 导航到 "**扩展**" 选项卡
    - 选择 Visual Studio Code 扩展的**Microsoft Quantum Development Kit**
    - 重新加载扩展

1. 更新量程项目模板：

   - 转到“视图” -> “命令面板”
   - 选择**Q #：安装项目模板**

## <a name="c-using-the-dotnet-command-line-tool"></a>C#，使用 `dotnet` 命令行工具

1. 更新 .NET 的量程项目模板

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a>还有什么？

现在，你已在首选环境中更新了量程开发工具包，接下来可以继续开发并运行量程程序。 如果还没有编写程序，可以开始使用[第一个量程计划](xref:microsoft.quantum.write-program)。
