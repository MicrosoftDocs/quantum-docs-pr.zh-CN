---
title: 向 Microsoft QDK 发布示例
description: 了解如何向 Microsoft Quantum Development Kit (QDK) 提供示例代码。
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.samples
no-loc:
- Q#
- $$v
ms.openlocfilehash: ae29614cc9c8bf965ea3cb373dc17470aec21252
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759180"
---
# <a name="contributing-samples-to-the-quantum-development-kit"></a><span data-ttu-id="13102-103">向量程开发工具包贡献示例</span><span class="sxs-lookup"><span data-stu-id="13102-103">Contributing Samples to the Quantum Development Kit</span></span>

<span data-ttu-id="13102-104">如果您对将代码提供给 [示例存储库](https://github.com/Microsoft/Quantum)感兴趣，感谢您使量子开发社区成为一个更好的场所！</span><span class="sxs-lookup"><span data-stu-id="13102-104">If you're interested in contributing code to the [samples repository](https://github.com/Microsoft/Quantum), thank you for making the quantum development community a better place!</span></span>

## <a name="the-quantum-development-kit-samples-repository"></a><span data-ttu-id="13102-105">量程开发工具包示例存储库</span><span class="sxs-lookup"><span data-stu-id="13102-105">The Quantum Development Kit Samples Repository</span></span>

<span data-ttu-id="13102-106">为了帮助您做好准备，帮助您充分了解如何帮助您更好地了解这些内容，可以快速查看示例存储库的布局：</span><span class="sxs-lookup"><span data-stu-id="13102-106">To help you prepare your contribution to help out as much as possible, it's helpful to take a quick look at how the samples repository is laid out:</span></span>

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

<span data-ttu-id="13102-107">也就是说， [microsoft/量子存储库](https://github.com/microsoft/Quantum) 中的示例按主题区域细分为不同的文件夹 `algorithms/` ，例如、 `arithmetic/` 或 `characterization/` 。</span><span class="sxs-lookup"><span data-stu-id="13102-107">That is, the samples in the [microsoft/Quantum repository](https://github.com/microsoft/Quantum) are broken down by subject area into different folders such as `algorithms/`, `arithmetic/`, or `characterization/`.</span></span>
<span data-ttu-id="13102-108">在每个主题区域的文件夹内，每个示例都包含一个文件夹，该文件夹收集用户需要浏览和使用该示例的所有内容。</span><span class="sxs-lookup"><span data-stu-id="13102-108">Within the folder for each subject area, each sample consists of a single folder that collects everything a user will need to explore and make use of that sample.</span></span>

## <a name="how-samples-are-structured"></a><span data-ttu-id="13102-109">如何构造示例</span><span class="sxs-lookup"><span data-stu-id="13102-109">How Samples are Structured</span></span>

<span data-ttu-id="13102-110">查看构成每个文件夹的文件，让我们深入了解 [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/chsh-game) 示例。</span><span class="sxs-lookup"><span data-stu-id="13102-110">Looking at the files that make up each folder, let's dive into the [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/chsh-game) sample.</span></span>

| <span data-ttu-id="13102-111">文件</span><span class="sxs-lookup"><span data-stu-id="13102-111">File</span></span>              | <span data-ttu-id="13102-112">描述</span><span class="sxs-lookup"><span data-stu-id="13102-112">Description</span></span>                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | <span data-ttu-id="13102-113">Q# 用于使用 .NET Core SDK 生成示例的项目</span><span class="sxs-lookup"><span data-stu-id="13102-113">Q# project used to build the sample with the .NET Core SDK</span></span> |
| `Game.qs`         | <span data-ttu-id="13102-114">Q# 示例的操作和函数</span><span class="sxs-lookup"><span data-stu-id="13102-114">Q# operations and functions for the sample</span></span>                 |
| `Host.cs`         | <span data-ttu-id="13102-115">用于运行示例的 c # 宿主程序</span><span class="sxs-lookup"><span data-stu-id="13102-115">C# host program used to run the sample</span></span>                     |
| `host.py`         | <span data-ttu-id="13102-116">用于运行示例的 Python 主机程序</span><span class="sxs-lookup"><span data-stu-id="13102-116">Python host program used to run the sample</span></span>                 |
| `README.md`       | <span data-ttu-id="13102-117">有关示例内容以及如何使用它的文档</span><span class="sxs-lookup"><span data-stu-id="13102-117">Documentation on what the sample does and how to use it</span></span>    |

<span data-ttu-id="13102-118">并非所有示例都具有完全相同的一组文件 (例如：某些示例可能仅限 c #，其他一些可能没有 Python 主机，或者某些示例可能需要辅助数据文件) 。</span><span class="sxs-lookup"><span data-stu-id="13102-118">Not all samples will have the exact same set of files (e.g.: some samples may be C#-only, others may not have a Python host, or some samples may require auxillary data files to work).</span></span>

## <a name="anatomy-of-a-helpful-readme-file"></a><span data-ttu-id="13102-119">有用的自述文件的剖析</span><span class="sxs-lookup"><span data-stu-id="13102-119">Anatomy of a Helpful README File</span></span>

<span data-ttu-id="13102-120">不过，一个特别重要的文件就是 `README.md` 文件，因为这就是用户需要的示例入门！</span><span class="sxs-lookup"><span data-stu-id="13102-120">One especially important file, though, is the `README.md` file, as that's what users need to get started with your sample!</span></span>

<span data-ttu-id="13102-121">每个都 `README.md` 应以一些可帮助 docs.microsoft.com/samples 查找你的内容的元数据开头。</span><span class="sxs-lookup"><span data-stu-id="13102-121">Each `README.md` should start with some metadata that helps docs.microsoft.com/samples find your contribution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="13102-122">了解如何呈现 chsh 示例</span><span class="sxs-lookup"><span data-stu-id="13102-122">See how the chsh-game sample is rendered</span></span>](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

<span data-ttu-id="13102-123">此元数据以 [YAML 标头](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) 的形式提供，此标头指示你的示例所涵盖的语言 (通常情况下，这将是 `qsharp` 、 `csharp` 和 `python`) ，而你的示例所涉及的产品 (通常只是 `qdk`) 。</span><span class="sxs-lookup"><span data-stu-id="13102-123">This metadata is provided as a [YAML header](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) that indicates what languages your sample covers (typically, this will be `qsharp`, `csharp`, and `python`), and what products your sample covers (typically, just `qdk`).</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> <span data-ttu-id="13102-124">`page_type: sample`要使示例显示在 docs.microsoft.com/samples 中，必须在标头中输入密钥。</span><span class="sxs-lookup"><span data-stu-id="13102-124">The `page_type: sample` key in the header is required for your sample to appear at docs.microsoft.com/samples.</span></span>
> <span data-ttu-id="13102-125">同样， `product` 和 `language` 键对于帮助用户查找和运行示例至关重要。</span><span class="sxs-lookup"><span data-stu-id="13102-125">Similarly, the `product` and `language` keys are critical for helping users to find and run your sample.</span></span>

<span data-ttu-id="13102-126">完成此操作后，请简要介绍一下新示例的作用：</span><span class="sxs-lookup"><span data-stu-id="13102-126">After that, it's helpful to give a short intro that says what your new sample does:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

<span data-ttu-id="13102-127">您的示例的用户还将感激知道他们需要运行它 (例如：用户只需量子开发工具包本身，还是需要其他软件（如 node.js） ) ：</span><span class="sxs-lookup"><span data-stu-id="13102-127">Users of your sample will also appreciate knowing what they need to run it (e.g.: do users just need the Quantum Development Kit itself, or do they need additional software such as node.js?):</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

<span data-ttu-id="13102-128">一切就绪后，就可以告诉用户如何运行示例：</span><span class="sxs-lookup"><span data-stu-id="13102-128">With all that in place, you can tell users how to run your sample:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

<span data-ttu-id="13102-129">最后，告诉用户您的示例中的每个文件都有帮助，在哪里可以获得更多信息：</span><span class="sxs-lookup"><span data-stu-id="13102-129">Finally, it's helpful to tell users what each file in your sample does, and where they can go for more information:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> <span data-ttu-id="13102-130">请确保在此处使用绝对 Url，因为在 docs.microsoft.com/samples 呈现时，示例将显示在不同的 URL 处！</span><span class="sxs-lookup"><span data-stu-id="13102-130">Make sure to use absolute URLs here, since your sample will appear at a different URL when rendered at docs.microsoft.com/samples!</span></span>
