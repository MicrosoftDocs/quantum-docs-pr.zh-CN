---
title: 更新 Quantum 开发工具包 (QDK)
description: 介绍如何将 Q# 项目和 Microsoft Quantum 开发工具包更新到当前版本。
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 8d39716c4d4c96ad87862b4b185895aab66cd210
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274020"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>更新 Microsoft Quantum 开发工具包 (QDK)

了解如何将 Microsoft Quantum 开发工具包 (QDK) 更新到最新版本。

本文假设你已安装 QDK。 如果是首次安装，请参阅[安装指南](xref:microsoft.quantum.install)。

建议始终使用最新 QDK 版本。 按照此更新指南升级到最新的 QDK 版本。 该过程包含两个阶段：
1. 更新现有 Q# 文件和项目，使代码与任何更新的语法保持一致。
2. 为所选的开发环境更新 QDK。

## <a name="updating-q-projects"></a>更新 Q# 项目 

无论你是使用 C# 还是 Python 来托管 Q# 操作，都请按照以下说明更新你的 Q# 项目。

1. 首先，请检查是否具有最新版 [.NET Core SDK 3.1](https://dotnet.microsoft.com/download)。 在命令提示符下运行以下命令：

    ```dotnetcli
    dotnet --version
    ```

    验证输出为 `3.1.100` 或更高版本。 如果未安装，请安装[最新版](https://dotnet.microsoft.com/download)并再次检查。 然后根据自己的设置（Visual Studio、Visual Studio Code 或直接使用命令行）按照以下说明操作。

### <a name="update-q-projects-in-visual-studio"></a>更新 Visual Studio 中的 Q# 项目
 
1. 更新到最新版 Visual Studio 2019，请参阅[此处](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019)了解相关说明。
2. 在 Visual Studio 中打开解决方案。
3. 从菜单中选择“生成” -> “清理解决方案” 。
4. 在每个 .csproj 文件中，将目标框架更新为 `netcoreapp3.1`（如果它是库项目，则更新为 `netstandard2.1`）。
    也就是说，编辑以下格式的行：

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    可在[此处](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)找到有关如何指定目标框架的更多详细信息。

5. 在每个 .csproj 文件中，将 SDK 设置为 `Microsoft.Quantum.Sdk`，如下面的行所示。 请注意，版本号应为最新的可用版本号，可以查看[发行说明](https://docs.microsoft.com/quantum/relnotes/)进行确认。

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. 保存并关闭解决方案中的所有文件。

7. 选择“工具” -> “命令行” -> “开发人员命令提示”  。 或者，也可以在 Visual Studio 中使用程序包管理器控制台。

8. 为解决方案中的每个项目运行以下命令，以删除此包：

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   如果项目使用任何其他的 Microsoft.Quantum 或 Microsoft.Azure.Quantum 包（如 Microsoft.Quantum.Numerics），请为其运行“添加”命令，以更新所用的版本。

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. 关闭命令提示符并选择“生成” -> "生成解决方案（请勿选择“重新生成解决方案”） 。

现可直接跳到[更新 Visual Studio QDK 扩展](#update-visual-studio-qdk-extension)。


### <a name="update-q-projects-in-visual-studio-code"></a>更新 Visual Studio Code 中的 Q# 项目

1. 在 Visual Studio Code 中，打开包含要更新的项目的文件夹。
2. 选择“终端” -> “新终端” 。
3. 按照使用命令行进行更新的相关说明进行操作（如下所示）。

### <a name="update-q-projects-using-the-command-line"></a>使用命令行更新 Q# 项目

1. 导航到包含主项目文件的文件夹。

2. 运行以下命令：

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. 确定 QDK 的当前版本。 若要查找当前版本，可查看[发行说明](https://docs.microsoft.com/quantum/relnotes/)。 版本的格式与 `0.11.2006.207` 类似。

4. 在每个 `.csproj` 文件中，完成以下步骤：

    - 将目标框架更新为 `netcoreapp3.1`（如果它是库项目，则更新为 `netstandard2.1`）。 也就是说，编辑以下格式的行：

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        可在[此处](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)找到有关如何指定目标框架的更多详细信息。

    - 替换项目定义中的 SDK 引用。 请确保版本号与步骤 3 中确定的值相符。

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - 删除对包 `Microsoft.Quantum.Development.Kit` 的引用（如有），该引用在以下条目中指定：

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - 将所有 Microsoft Quantum 包版本更新为最新发布的 QDK 版本（在步骤 3 中确定）。 这些包的命名方式如下：

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        对包的引用格式如下：

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - 保存更新的文件。

    - 通过执行以下操作还原项目的依赖项：

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. 导航回包含主项目的文件夹，然后运行：

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

Q# 项目已更新，现请按照下面的说明更新 QDK。

## <a name="updating-the-qdk"></a>更新 QDK

更新 QDK 的过程因开发语言和环境而异。
选择下面的开发环境。

* [Python：更新 IQ# 扩展](#update-iq-for-python)
* [Jupyter Notebook：更新 IQ# 扩展](#update-iq-for-jupyter-notebooks)
* [Visual Studio：更新 QDK 扩展](#update-visual-studio-qdk-extension)
* [VS Code：更新 QDK 扩展](#update-vs-code-qdk-extension)
* [命令行和 C#：更新项目模板](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a>更新适用于 Python 的 IQ#

1. 更新 `iqsharp` 内核 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. 验证 `iqsharp` 版本

    ```dotnetcli
    dotnet iqsharp --version
    ```

    应该会看到以下输出：

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    如果你的 `iqsharp` 版本较高，请不要担心，它应该是与[最新版本](xref:microsoft.quantum.relnotes)匹配的。

3. 更新 `qsharp` 包

    ```
    pip install qsharp --upgrade
    ```

4. 验证 `qsharp` 版本

    ```
    pip show qsharp
    ```

    应该会看到以下输出：

    ```
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. 从 `.qs` 文件的位置运行以下命令

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

6. 你现可使用更新的 QDK 版本来运行现有的量子程序。

### <a name="update-iq-for-jupyter-notebooks"></a>更新适用于 Jupyter Notebook 的 IQ#

1. 更新 `iqsharp` 内核

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. 验证 `iqsharp` 版本

    ```dotnetcli
    dotnet iqsharp --version
    ```

    输出应类似如下所示：

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    如果你的 `iqsharp` 版本较高，请不要担心，它应该是与[最新版本](xref:microsoft.quantum.relnotes)匹配的。

3. 从 Jupyter Notebook 中的单元格运行以下命令：

    ```
    %workspace reload
    ```

4. 现在便可以打开现有 Jupyter 笔记本，并使用更新后的 QDK 运行它。

### <a name="update-visual-studio-qdk-extension"></a>更新 Visual Studio QDK 扩展

1. 更新 Q# Visual Studio 扩展

    - Visual Studio 会提示你接受 [Quantum Visual Studio 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)的更新
    - 接受更新

    > [!NOTE]
    > 项目模板将随扩展更新。 更新后的模板仅适用于新创建的项目。 更新扩展时，不会更新现有项目的代码。

### <a name="update-vs-code-qdk-extension"></a>更新 VS Code QDK 扩展

1. 更新 Quantum VS Code 扩展

    - 重启 VS Code
    - 导航到“扩展”选项卡
    - 选择适用于 Visual Studio Code 的 Microsoft Quantum 开发工具包扩展
    - 重新加载扩展

2. 更新 Quantum 项目模板：

   - 转到“视图” -> “命令面板” 
   - 选择“Q#: 安装项目模板”
   - 几秒钟后，你应该会看到一个显示“项目模板已成功安装”确认消息的弹出窗口

### <a name="c-using-the-dotnet-command-line-tool"></a>C#，使用 `dotnet` 命令行工具

1. 更新适用于 .NET 的 Quantum 项目模板

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
