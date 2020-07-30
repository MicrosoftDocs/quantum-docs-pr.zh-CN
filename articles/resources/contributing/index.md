---
title: 为 Microsoft Quantum 开发工具包贡献内容
description: 了解如何为 Microsoft Quantum 开发工具包和量子开发社区贡献内容。
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing
ms.openlocfilehash: c5acd6c2b3163488a9b4c6e52e6d34489a8f4056
ms.sourcegitcommit: 2f4c637e194dc2b5d18539469ed37444e2800199
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2020
ms.locfileid: "87436568"
---
# <a name="contributing-to-the-quantum-development-kit"></a><span data-ttu-id="dacf5-103">对量子开发工具包做出贡献</span><span class="sxs-lookup"><span data-stu-id="dacf5-103">Contributing to the Quantum Development Kit</span></span>

<span data-ttu-id="dacf5-104">量子开发工具包不仅是一组用于编写量子程序的工具。</span><span class="sxs-lookup"><span data-stu-id="dacf5-104">The Quantum Development Kit is more than a collection of tools for writing quantum programs.</span></span>
<span data-ttu-id="dacf5-105">它属于广泛的用户社区，可发现量子计算，对量子算法进行研究，为量子设备开发新应用程序，并致力于充分利用量子编程。</span><span class="sxs-lookup"><span data-stu-id="dacf5-105">It's part of a broad community of people discovering quantum computing, performing research in quantum algorithms, developing new applications for quantum devices, and otherwise working to make the most out of the quantum programming.</span></span>
<span data-ttu-id="dacf5-106">作为该社区的成员，量子开发工具包旨在为各种背景的量子开发人员提供所需的功能。</span><span class="sxs-lookup"><span data-stu-id="dacf5-106">As a member of that community, the Quantum Development Kit aims to offer quantum developers across a wide range of backgrounds with the features they need.</span></span>
<span data-ttu-id="dacf5-107">为量子开发工具包做出贡献有助于实现这一目标，方法是改进其他量子开发人员使用的工具和记录这些工具的方式，甚至创建有助于使整个量子编程社区更适合发现和创建的新特性和功能。</span><span class="sxs-lookup"><span data-stu-id="dacf5-107">Your contributions to the Quantum Development Kit help in realizing that goal by improving the tools used by other quantum developers, how those tools are documented, and even by creating new features and functionality that helps make the entire quantum programming community a better place to discover and create.</span></span>
<span data-ttu-id="dacf5-108">我们对你做出的贡献以及有机会与你合作来尽可能完善社区表示非常感谢。</span><span class="sxs-lookup"><span data-stu-id="dacf5-108">We're very thankful for your kind contributions, and for the opportunity to work with you to make our community the best that it can be.</span></span> 

<span data-ttu-id="dacf5-109">在本指南中，我们将提供有关如何使你的贡献尽可能适用于更广泛的量子编程社区的一些建议。</span><span class="sxs-lookup"><span data-stu-id="dacf5-109">In this guide, we provide some advice on how to make your contribution as useful as possible to the broader quantum programming community.</span></span>

## <a name="building-community"></a><span data-ttu-id="dacf5-110">构建社区</span><span class="sxs-lookup"><span data-stu-id="dacf5-110">Building Community</span></span>

<span data-ttu-id="dacf5-111">有关做出贡献的第一件事就是始终记住对其做出贡献的社区。</span><span class="sxs-lookup"><span data-stu-id="dacf5-111">The very first thing about making a contribution is to always keep in mind the community that you are contributing to.</span></span>
<span data-ttu-id="dacf5-112">通过在量子编程社区中对合作伙伴做出恭敬且专业的行为，可以帮助确保构建最受欢迎的社区。</span><span class="sxs-lookup"><span data-stu-id="dacf5-112">By acting respectfully and professionally towards your peers in the quantum programming community and more broadly, you can help to make sure that your efforts build the best and most welcoming community possible.</span></span>

<span data-ttu-id="dacf5-113">在这一过程中，所有量子开发工具包项目都采用了 [Microsoft 开放源代码行为准则](https://opensource.microsoft.com/codeofconduct/)。</span><span class="sxs-lookup"><span data-stu-id="dacf5-113">As a part of that effort, all Quantum Development Kit projects have adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).</span></span>
<span data-ttu-id="dacf5-114">有关详细信息，请参阅[行为准则常见问题解答](https://opensource.microsoft.com/codeofconduct/faq/)；若有其他任何问题或意见，请联系 [opencode@microsoft.com](mailto:opencode@microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="dacf5-114">For more information, please see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.</span></span>

## <a name="what-kinds-of-contributions-help-the-community"></a><span data-ttu-id="dacf5-115">哪些类型的贡献可以帮助社区？</span><span class="sxs-lookup"><span data-stu-id="dacf5-115">What Kinds of Contributions Help the Community?</span></span>

<span data-ttu-id="dacf5-116">通过你的贡献来帮助量子编程社区有多种不同的方法。</span><span class="sxs-lookup"><span data-stu-id="dacf5-116">There are lots of different ways to help the quantum programming community through your contributions.</span></span>
<span data-ttu-id="dacf5-117">在本指南中，我们将重点介绍与量子开发工具包密切相关的三种方法。</span><span class="sxs-lookup"><span data-stu-id="dacf5-117">In this guide, we'll focus on three ways that are especially relevant to the Quantum Development Kit.</span></span>
<span data-ttu-id="dacf5-118">所有这些方法对于构建可提高用户能力的量子社区非常重要。</span><span class="sxs-lookup"><span data-stu-id="dacf5-118">All of these ways are critical to building a quantum community that empowers people.</span></span>
<span data-ttu-id="dacf5-119">也就是说，这决不是一个详尽的清单，我们建议你探索其他方法，以便基于量子编程的承诺帮助构建社区！</span><span class="sxs-lookup"><span data-stu-id="dacf5-119">That said, this is definitely not an exhaustive list — we encourage you to explore other ways to help the community build on the promise of quantum programming!</span></span>

- <span data-ttu-id="dacf5-120">**报告 bug。**</span><span class="sxs-lookup"><span data-stu-id="dacf5-120">**Reporting bugs.**</span></span> <span data-ttu-id="dacf5-121">修复 bug 和其他类型的问题的第一步是识别它们。</span><span class="sxs-lookup"><span data-stu-id="dacf5-121">The first step in fixing bugs and other kinds of problems is to identify them.</span></span> <span data-ttu-id="dacf5-122">如果你在量子开发工具包中发现了 bug，请告知我们，这样有助于对其进行修复，并为量子编程社区创建更好的一组工具。</span><span class="sxs-lookup"><span data-stu-id="dacf5-122">If you've found a bug in the Quantum Development Kit, letting us know helps us fix it and make a better set of tools for the quantum programming community.</span></span>
- <span data-ttu-id="dacf5-123">**改进文档。**</span><span class="sxs-lookup"><span data-stu-id="dacf5-123">**Improving documentation.**</span></span> <span data-ttu-id="dacf5-124">任何文档集始终可以更好地提供更多详细信息，使其更易于访问。</span><span class="sxs-lookup"><span data-stu-id="dacf5-124">Any documentation set can always be better, can cover more details, be made more accessible.</span></span>
- <span data-ttu-id="dacf5-125">**贡献代码。**</span><span class="sxs-lookup"><span data-stu-id="dacf5-125">**Contributing code.**</span></span> <span data-ttu-id="dacf5-126">当然，贡献的最直接方法之一就是将新代码添加到量子开发工具包。</span><span class="sxs-lookup"><span data-stu-id="dacf5-126">Of course, one of the most direct ways to contribute is by adding new code to the Quantum Development Kit.</span></span>

<span data-ttu-id="dacf5-127">这些不同类型的贡献都非常宝贵，非常感谢。</span><span class="sxs-lookup"><span data-stu-id="dacf5-127">These different kinds of contributions are all immensely valuable, and are greatly appreciated.</span></span>
<span data-ttu-id="dacf5-128">在本指南的其余部分，我们将提供有关如何做出各种贡献的建议。</span><span class="sxs-lookup"><span data-stu-id="dacf5-128">In the rest of the guide, we'll offer advice on how to make each kind of contribution.</span></span>

## <a name="where-do-contributions-go"></a><span data-ttu-id="dacf5-129">贡献的目标位置在哪里？</span><span class="sxs-lookup"><span data-stu-id="dacf5-129">Where Do Contributions Go?</span></span>

<span data-ttu-id="dacf5-130">量子开发工具包包含许多不同的部分，它们组合在一起来实现用于编写量子程序的平台。</span><span class="sxs-lookup"><span data-stu-id="dacf5-130">The Quantum Development Kit includes a number of different pieces that all work together to realize a platform for writing quantum programs.</span></span>
<span data-ttu-id="dacf5-131">其中每个不同部分都在不同的存储库中找到它的位置，因此，要进行排序的早期位置之一是每个贡献最适合的目标位置。</span><span class="sxs-lookup"><span data-stu-id="dacf5-131">Each of these different pieces finds its home on a different repository, so the one of the earlier things to sort out is where each contribution best belongs.</span></span>

- <span data-ttu-id="dacf5-132">[**microsoft/Quantum**](https://github.com/Microsoft/Quantum)：有助于开始使用量子开发工具包的示例和工具。</span><span class="sxs-lookup"><span data-stu-id="dacf5-132">[**microsoft/Quantum**](https://github.com/Microsoft/Quantum): Samples and tools to help get started with the Quantum Development Kit.</span></span>
- <span data-ttu-id="dacf5-133">[**microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries)：量子开发工具包的标准和域特定库。</span><span class="sxs-lookup"><span data-stu-id="dacf5-133">[**microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries): Standard and domain-specific libraries for the Quantum Development Kit.</span></span>
- <span data-ttu-id="dacf5-134">[**microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas)：用于学习量子计算和 Q# 编程语言的自定进度编程练习。</span><span class="sxs-lookup"><span data-stu-id="dacf5-134">[**microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas): Self-paced programming exercises for learning quantum computing and the Q# programming language.</span></span>
- <span data-ttu-id="dacf5-135">[**microsoft/qsharp-compiler**](https://github.com/microsoft/qsharp-compiler)：Q# 编译器、Visual Studio 扩展和 Visual Studio Code 扩展。</span><span class="sxs-lookup"><span data-stu-id="dacf5-135">[**microsoft/qsharp-compiler**](https://github.com/microsoft/qsharp-compiler): The Q# compiler, Visual Studio extension, and Visual Studio Code extension.</span></span>
- <span data-ttu-id="dacf5-136">[**microsoft/qsharp-runtime**](https://github.com/microsoft/qsharp-runtime)：量子开发工具包的模拟框架、代码生成和模拟目标计算机。</span><span class="sxs-lookup"><span data-stu-id="dacf5-136">[**microsoft/qsharp-runtime**](https://github.com/microsoft/qsharp-runtime): Simulation framework, code generation, and simulation target machines for the Quantum Development Kit.</span></span>
- <span data-ttu-id="dacf5-137">[**microsoft/iqsharp**](https://github.com/microsoft/iqsharp)：用于 Q# 的 Jupyter 内核和 Python 主机功能，以及用于在云环境中使用 IQ# 的 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="dacf5-137">[**microsoft/iqsharp**](https://github.com/microsoft/iqsharp): Jupyter kernel and Python host functionality for Q#, as well as Docker images for using IQ# in cloud environments.</span></span>
- <span data-ttu-id="dacf5-138">[**MicrosoftDocs/quantum-docs-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr)： https://docs.microsoft.com/quantum 上发布的文档的源代码。</span><span class="sxs-lookup"><span data-stu-id="dacf5-138">[**MicrosoftDocs/quantum-docs-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr): Source code for the documentation published at https://docs.microsoft.com/quantum.</span></span>

> [!NOTE]
> <span data-ttu-id="dacf5-139">遗憾的是，我们目前无法接受 [**microsoft/Quantum-NC**](https://github.com/microsoft/Quantum-NC) 存储库上的代码和文档内容，但我们仍非常感谢你提供 bug 报表。</span><span class="sxs-lookup"><span data-stu-id="dacf5-139">We unfortunately cannot accept code and documentation contributions on the [**microsoft/Quantum-NC**](https://github.com/microsoft/Quantum-NC) repository at this time, but we still very much appreciate bug reports.</span></span>

<span data-ttu-id="dacf5-140">还有其他一些更具专门用途的存储库，专注于与 Quantum 开发工具包相关的辅助功能。</span><span class="sxs-lookup"><span data-stu-id="dacf5-140">There are also a few other, more specialized repositories focusing on auxiliary functionality related to the Quantum Development Kit.</span></span>

- <span data-ttu-id="dacf5-141">[**msr-quarc/qsharp.sty**](https://github.com/msr-quarc/qsharp.sty)：格式化对 Q# 语法的支持的 LaTeX。</span><span class="sxs-lookup"><span data-stu-id="dacf5-141">[**msr-quarc/qsharp.sty**](https://github.com/msr-quarc/qsharp.sty): LaTeX formatting support for Q# syntax.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dacf5-142">后续步骤</span><span class="sxs-lookup"><span data-stu-id="dacf5-142">Next steps</span></span>

<span data-ttu-id="dacf5-143">感谢你成为量子开发工具包社区的一员，我们很高应你做出了贡献！</span><span class="sxs-lookup"><span data-stu-id="dacf5-143">Thanks for being a part of the Quantum Development Kit community, we're excited for your contributions!</span></span>
<span data-ttu-id="dacf5-144">如果你想要了解有关贡献的详细信息，请继续阅读以下指南之一。</span><span class="sxs-lookup"><span data-stu-id="dacf5-144">If you'd like to learn more about contributing, please continue with one of the following guides.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="dacf5-145">了解如何报告 bug</span><span class="sxs-lookup"><span data-stu-id="dacf5-145">Learn how to report bugs</span></span>](xref:microsoft.quantum.contributing.reporting)

> [!div class="nextstepaction"]
> [<span data-ttu-id="dacf5-146">了解如何提供文档</span><span class="sxs-lookup"><span data-stu-id="dacf5-146">Learn how to contribute documentation</span></span>](xref:microsoft.quantum.contributing.docs)

> [!div class="nextstepaction"]
> [<span data-ttu-id="dacf5-147">了解如何打开拉取请求</span><span class="sxs-lookup"><span data-stu-id="dacf5-147">Learn how to open pull requests</span></span>](xref:microsoft.quantum.contributing.pulls)
