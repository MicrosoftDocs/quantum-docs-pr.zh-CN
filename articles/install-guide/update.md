---
title: 更新量程开发工具包（QDK）
description: '介绍如何将您的 Q # 项目和 Microsoft Quantum Development Kit 更新到最新版本。'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 3245f587493ce12cfec15c8f932fd092d85f688e
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327556"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>更新 Microsoft Quantum Development Kit （QDK）

了解如何将 Microsoft Quantum Development Kit （QDK）更新到最新版本。

本文假设已安装 QDK。 如果你是首次安装，请参阅[安装指南](xref:microsoft.quantum.install)。

建议你随时了解最新的 QDK 版本。 按照此更新指南升级到最新的 QDK 版本。 此过程由两个部分组成：
1. 更新现有的 Q # 文件和项目，以使代码与任何更新的语法对齐。
2. 为所选的开发环境更新 QDK 本身。

## <a name="updating-q-projects"></a>更新 Q # 项目 

无论使用 c # 还是 Python 来承载 Q # 操作，请按照以下说明更新 Q # 项目。

1. 首先，请检查是否安装了最新版本的[.NET Core SDK 3.1](https://dotnet.microsoft.com/download)。 在命令提示符下运行以下命令：

    ```dotnetcli
    dotnet --version
    ```

    验证输出是否为 `3.1.100` 或更高版本。 如果未安装，请安装[最新版本](https://dotnet.microsoft.com/download)，然后重新检查。 然后根据您的设置（Visual Studio、Visual Studio Code 或直接命令行），按照以下说明进行操作。

### <a name="update-q-projects-in-visual-studio"></a>在 Visual Studio 中更新 Q # 项目
 
1. 更新到最新版本的 Visual Studio 2019，请参阅[此处](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019)了解说明。
2. 在 Visual Studio 中打开解决方案。
3. 从菜单中选择 "**生成**  ->  **干净解决方案**"。
4. 在每个 .csproj 文件中，将目标框架更新为 `netcoreapp3.1` （或者， `netstandard2.1` 如果它是库项目）。
    也就是说，编辑以下格式的行：

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    可在[此处](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)找到有关指定目标框架的详细信息。

5. 在每个 .csproj 文件中，将 SDK 设置为 `Microsoft.Quantum.Sdk` ，如下面的行所示。 请注意，版本号应该是最新的，并且可以通过查看[发行说明](https://docs.microsoft.com/quantum/relnotes/)来确定。

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. 保存并关闭解决方案中的所有文件。

7. 选择**工具**  ->  **命令行**  ->  **开发人员命令提示**。 或者，你可以使用 Visual Studio 中的包管理控制台。

8. 对于解决方案中的每个项目，请运行以下命令来**删除**此包：

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   如果你的项目使用任何其他的 Microsoft 量子或. 量子包（例如，Microsoft 量子），请运行 "**添加**" 命令，以更新使用的版本。

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. 关闭命令提示符并选择 "**生成**  ->  **生成解决方案**" （*不*选择 "重新生成解决方案"）。

你现在可以直接跳到[更新你的 Visual STUDIO QDK 扩展](#update-visual-studio-qdk-extension)。


### <a name="update-q-projects-in-visual-studio-code"></a>更新 Visual Studio Code 中的 Q # 项目

1. 在 Visual Studio Code 中，打开包含要更新的项目的文件夹。
2. 选择**终端**  ->  **新终端**。
3. 按照使用命令行进行更新的说明进行操作（如下所示）。

### <a name="update-q-projects-using-the-command-line"></a>使用命令行更新 Q # 项目

1. 导航到包含主项目文件的文件夹。

2. 运行下面的命令：

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. 确定 QDK 的当前版本。 若要找到它，可以查看[发行说明](https://docs.microsoft.com/quantum/relnotes/)。 版本的格式类似于 `0.11.2006.207` 。

4. 在每个 `.csproj` 文件中，完成以下步骤：

    - 将目标框架更新为 `netcoreapp3.1` （或者， `netstandard2.1` 如果它是库项目）。 也就是说，编辑以下格式的行：

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        可在[此处](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)找到有关指定目标框架的详细信息。

    - 将引用替换为项目定义中的 SDK。 请确保版本号与**步骤 3**中确定的值相对应。

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - 删除对包的引用 `Microsoft.Quantum.Development.Kit` （如果存在），此引用将在以下条目中指定：

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - 将所有 Microsoft 量程包的版本更新到最近发布的 QDK 版本（在**步骤 3**中确定）。 这些包的命名方式如下：

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        对包的引用具有以下格式：

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

现在，你的 Q # 项目已更新，请按照下面的说明更新 QDK 本身。

## <a name="updating-the-qdk"></a>更新 QDK

更新 QDK 的过程因开发语言和环境而异。
选择下面的开发环境。

* [Python：更新 IQ # 扩展](#update-iq-for-python)
* [Jupyter 笔记本：更新 IQ # 扩展](#update-iq-for-jupyter-notebooks)
* [Visual Studio：更新 QDK 扩展](#update-visual-studio-qdk-extension)
* [VS Code：更新 QDK 扩展](#update-vs-code-qdk-extension)
* [命令行和 c #：更新项目模板](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a>更新适用于 Python 的 IQ #

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

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    请不要担心 `iqsharp` 版本是否较高，它应与[最新版本](xref:microsoft.quantum.relnotes)相匹配。

3. 更新 `qsharp` 包

    ```bash
    pip install qsharp --upgrade
    ```

4. 验证 `qsharp` 版本

    ```bash
    pip show qsharp
    ```

    应该会看到以下输出：

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. 从文件的位置运行以下命令 `.qs`

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. 你现在可以使用更新的 QDK 版本来运行现有的量程程序。

### <a name="update-iq-for-jupyter-notebooks"></a>更新适用于 Jupyter 笔记本的 IQ #

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

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    请不要担心 `iqsharp` 版本是否较高，它应与[最新版本](xref:microsoft.quantum.relnotes)相匹配。

3. 在 Jupyter Notebook 中的单元格上运行以下命令：

    ```
    %workspace reload
    ```

4. 你现在可以打开现有的 Jupyter 笔记本，并使用更新的 QDK 运行它。

### <a name="update-visual-studio-qdk-extension"></a>更新 Visual Studio QDK 扩展

1. 更新 Q # Visual Studio 扩展

    - Visual Studio 会提示你接受对[量程 Visual Studio 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)的更新
    - 接受更新

    > [!NOTE]
    > 项目模板将更新为扩展。 更新的模板仅适用于新创建的项目。 更新扩展时，不会更新现有项目的代码。

### <a name="update-vs-code-qdk-extension"></a>更新 VS Code QDK 扩展

1. 更新量程 VS Code 扩展

    - 重新启动 VS Code
    - 导航到 "**扩展**" 选项卡
    - 选择 Visual Studio Code 扩展的**Microsoft Quantum Development Kit**
    - 重新加载扩展

2. 更新量程项目模板：

   - 中转到 "**视图**"  ->  **命令面板**
   - 选择**Q #：安装项目模板**
   - 几秒钟后，你应该会看到一个弹出窗口，确认 "项目模板已成功安装"

### <a name="c-using-the-dotnet-command-line-tool"></a>C #，使用 `dotnet` 命令行工具

1. 更新 .NET 的量程项目模板

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
