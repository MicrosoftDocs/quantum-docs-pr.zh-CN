---
title: 了解如何更新 Microsoft Quantum Development Kit （QDK）
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: f19285ae0e008b3460d06430a236f098d716e268
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036300"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>更新 Microsoft Quantum Development Kit （QDK）

了解如何将 Microsoft Quantum Development Kit （QDK）更新到最新版本。

本文假设已安装 QDK。 如果你是首次安装，请参阅[安装指南](xref:microsoft.quantum.install)。

建议你随时了解最新的 QDK 版本。 按照此更新指南升级到最新的 QDK 版本。 此过程由两个部分组成：
1. 更新现有的 Q # 文件和项目，以使代码与任何更新的语法对齐
2. 为所选开发环境更新 QDK 本身 

## <a name="updating-q-projects"></a>更新 Q # 项目 

无论你是使用C#还是 Python 来承载 q # 操作，请按照以下说明更新你的 q # 项目。

1. 首先，请检查是否安装了最新版本的[.NET Core SDK 3.1](https://dotnet.microsoft.com/download)。 在命令提示符下运行以下命令：

    ```dotnetcli
    dotnet --version
    ```

    验证输出 `3.1.100` 或更高版本。 如果未安装，请安装[最新版本](https://dotnet.microsoft.com/download)，然后重新检查。 然后根据您的设置（Visual Studio、Visual Studio Code 或直接命令行），按照以下说明进行操作。

### <a name="update-q-projects-in-visual-studio"></a>在 Visual Studio 中更新 Q # 项目
 
1. 更新到最新版本的 Visual Studio 2019，请参阅[此处](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019)了解相关说明
2. 在 Visual Studio 中打开解决方案
3. 从菜单中选择 "**生成** -> **清理解决方案**"
4. 在每个 .csproj 文件中，将目标框架更新为 `netcoreapp3.0` （如果它是库项目，则将 `netstandard2.1`）。
    也就是说，编辑以下格式的行：

    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```

    可在[此处](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)找到有关指定目标框架的详细信息。
5. 保存并关闭解决方案中的所有文件
6.  ->  **命令行** -> 选择工具**开发人员命令提示**
7. 对于解决方案中的每个项目，请运行以下命令：

    ```dotnetcli
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   如果你的项目使用任何其他的 Microsoft 量子包（如 Microsoft 量子），则也要为这些包运行命令。
8. 关闭命令提示符并选择 "**生成** -> **生成解决方案**" （*不选择 "* 重新生成解决方案"）

你现在可以直接跳到[更新你的 Visual STUDIO QDK 扩展](#update-visual-studio-qdk-extension)。


### <a name="update-q-projects-in-visual-studio-code"></a>更新 Visual Studio Code 中的 Q # 项目

1. 在 Visual Studio Code 中，打开包含要更新项目的文件夹
2. 选择**终端** -> **新终端**
3. 按照使用命令行进行更新的说明进行操作（如下所示）

### <a name="update-q-projects-using-the-command-line"></a>使用命令行更新 Q # 项目

1. 导航到包含项目文件的文件夹
2. 运行以下命令：

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. 在每个 .csproj 文件中，将目标框架更新为 `netcoreapp3.0` （如果它是库项目，则将 `netstandard2.1`）。
    也就是说，编辑以下格式的行：

    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```

    可在[此处](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)找到有关指定目标框架的详细信息。
4. 运行以下命令：

    ```dotnetcli
    dotnet add package Microsoft.Quantum.Development.Kit
    ```

    如果你的项目使用任何其他的 Microsoft 量子包（如 Microsoft 量子），则也要为这些包运行命令。
5. 保存并关闭所有文件。
6. 为每个项目依赖项重复1-4，然后导航回到包含主项目的文件夹，然后运行：

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
* [命令行和C#：更新项目模板](#c-using-the-dotnet-command-line-tool)


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

    您应看到下列输出：

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

    您应看到下列输出：

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. 从 `.qs` 文件的位置运行以下命令

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

   - 转到“视图” **“命令面板”**  -> 
   - 选择**Q #：安装项目模板**
   - 几秒钟后，你应该会看到一个弹出窗口，确认 "项目模板已成功安装"

### <a name="c-using-the-dotnet-command-line-tool"></a>C#，使用 `dotnet` 命令行工具

1. 更新 .NET 的量程项目模板

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a>后续步骤

现在，你已在首选环境中更新了量程开发工具包，接下来可以继续开发并运行量程程序。 如果还没有编写程序，可以开始使用[第一个量程计划](xref:microsoft.quantum.write-program)。
