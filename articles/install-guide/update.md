---
title: 了解如何更新 Microsoft Quantum Development Kit （QDK）
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: fc430a77f88878437e662c5b54507f70f3c6e020
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185845"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>更新 Microsoft Quantum Development Kit （QDK）

了解如何将 Microsoft Quantum Development Kit （QDK）更新到最新版本。

本文假设已安装 QDK。 如果你是首次安装，请参阅[安装指南](xref:microsoft.quantum.install)。

更新步骤取决于你的开发环境。 从以下部分中选择环境。

## <a name="python"></a>Python

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
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
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
    Version: 0.9.1909.3002
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. 你现在可以使用更新的 QDK 版本来运行现有的量程程序。

## <a name="jupyter-notebooks"></a>Jupyter 笔记本

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
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. 你现在可以打开现有的 Jupyter 笔记本，并使用更新的 QDK 运行它。

## <a name="c-on-windows-using-visual-studio"></a>C#在 Windows 上，使用 Visual Studio

1. 更新 Q # Visual Studio 扩展

    - Visual Studio 会提示你接受对[量程 Visual Studio 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)的更新
    - 接受更新

    > [!NOTE]
    > 项目模板将更新为扩展。 更新的模板仅适用于新创建的项目。 更新扩展时，不会更新现有项目的代码。

1. 更新 QDK 包

    - 打开现有应用程序
    - 在解决方案资源管理器中选择**依赖关系**
    - 选择 "**管理 NuGet 包**"
    - 将**Microsoft 量子**包更新到最新版本

1. 你现在可以用最新的 QDK 运行你的应用程序。

## <a name="c-using-vs-code"></a>C#，使用 VS Code

1. 更新量程 VS Code 扩展

    - 重新启动 VS Code
    - 导航到 "**扩展**" 选项卡
    - 选择 Visual Studio Code 扩展的**Microsoft Quantum Development Kit**
    - 重新加载扩展

1. 更新量程项目模板：

   - 中转到**查看** -> **命令面板**
   - 选择**Q #：安装项目模板**

1. 在 VS Code 中打开现有应用程序

   - 编辑 .csproj 文件以添加新的包版本

    ```xml
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.9.1909.3002" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.9.1909.3002" />
    </ItemGroup>
    ```

    如果使用其他 `Microsoft.Quantum` 包，也可以更新这些包。

1. 你现在可以运行包含更新的 QDK 的应用程序

## <a name="c-using-the-dotnet-command-line-tool"></a>C#，使用 `dotnet` 命令行工具

1. 更新 .NET 的量程项目模板

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. 更新并运行现有应用程序

    - 更新应用程序中的 QDK 包版本

        ```bash
        dotnet add package Microsoft.Quantum.Development.Kit
        dotnet add package Microsoft.Quantum.Standard
        ```

        如果你的应用程序使用任何其他 `Microsoft.Quantum` 包，也更新这些包。

    - 运行应用程序

        ```bash
        dotnet run
        ```

    - 应用程序将在新的包版本中运行

## <a name="whats-next"></a>还有什么？

现在，你已在首选环境中更新了量程开发工具包，接下来可以继续开发并运行量程程序。 如果还没有编写程序，可以开始使用[第一个量程计划](xref:microsoft.quantum.write-program)。
