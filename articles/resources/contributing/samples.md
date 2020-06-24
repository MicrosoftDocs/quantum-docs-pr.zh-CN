---
title: 向 Microsoft QDK 发布示例
description: 了解如何向 Microsoft Quantum Development Kit （QDK）提供示例代码。
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.samples
ms.openlocfilehash: 3bd0de04a448c74eea6c3e8e3a15dcbb19f9d705
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274372"
---
# <a name="contributing-samples-to-the-quantum-development-kit"></a>向量程开发工具包贡献示例

如果您对将代码提供给[示例存储库](https://github.com/Microsoft/Quantum)感兴趣，感谢您使量子开发社区成为一个更好的场所！

## <a name="the-quantum-development-kit-samples-repository"></a>量程开发工具包示例存储库

为了帮助您做好准备，帮助您充分了解如何帮助您更好地了解这些内容，可以快速查看示例存储库的布局：

```plaintext
microsoft/Quantum
📁 samples/
  📁 algorithms/
    📁 chsh-game/
      📝 CHSHGame.csproj
      📝 Game.qs
      📝 Host.cs
      📝 host.py
      📝 README.md
     ⋮
  📁 arithmetic/
  📁 characterization/
  📁 chemistry/
   ⋮
```

也就是说， [microsoft/量子存储库](https://github.com/microsoft/Quantum)中的示例按主题区域细分为不同的文件夹 `algorithms/` ，例如、 `arithmetic/` 或 `characterization/` 。
在每个主题区域的文件夹内，每个示例都包含一个文件夹，该文件夹收集用户需要浏览和使用该示例的所有内容。

## <a name="how-samples-are-structured"></a>如何构造示例

查看构成每个文件夹的文件，让我们深入了解 [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) 示例。

| 文件              | 描述                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | 用于使用 .NET Core SDK 生成示例的 Q # 项目 |
| `Game.qs`         | 示例的 Q # 操作和函数                 |
| `Host.cs`         | 用于运行示例的 c # 宿主程序                     |
| `host.py`         | 用于运行示例的 Python 主机程序                 |
| `README.md`       | 有关示例内容以及如何使用它的文档    |

并非所有示例都具有完全相同的文件集（例如：某些示例可能仅限 c #，其他示例可能没有 Python 主机，或者某些示例可能需要辅助数据文件才能工作）。

## <a name="anatomy-of-a-helpful-readme-file"></a>有用的自述文件的剖析

不过，一个特别重要的文件就是 `README.md` 文件，因为这就是用户需要的示例入门！

每个都 `README.md` 应以一些可帮助 docs.microsoft.com/samples 查找你的内容的元数据开头。

> [!div class="nextstepaction"]
> [了解如何呈现 chsh 示例](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

此元数据以[YAML 标头](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header)的形式提供，用于指示你的示例所涵盖的语言（通常为 `qsharp` 、 `csharp` 和 `python` ），以及你的示例所涵盖的产品（通常为 `qdk` ）。

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> `page_type: sample`要使示例显示在 docs.microsoft.com/samples 中，必须在标头中输入密钥。
> 同样， `product` 和 `language` 键对于帮助用户查找和运行示例至关重要。

完成此操作后，请简要介绍一下新示例的作用：

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

您的示例的用户还将感激知道他们需要运行什么（例如：用户只需量子开发工具包本身，还是需要其他软件（如 node.js？）：

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

一切就绪后，就可以告诉用户如何运行示例：

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

最后，告诉用户您的示例中的每个文件都有帮助，在哪里可以获得更多信息：

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> 请确保在此处使用绝对 Url，因为在 docs.microsoft.com/samples 呈现时，示例将显示在不同的 URL 处！
