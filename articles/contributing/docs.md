---
title: 参与文档 |Microsoft Docs
description: 参与文档
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.docs
ms.openlocfilehash: 1e24dd859c0b75a161f4f3c7151e2eec227075a2
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183669"
---
# <a name="improving-documentation"></a><span data-ttu-id="4d59f-103">改进文档</span><span class="sxs-lookup"><span data-stu-id="4d59f-103">Improving Documentation</span></span> #

<span data-ttu-id="4d59f-104">量程开发工具包的文档采用多种不同的形式，以使该信息可供量子开发人员使用。</span><span class="sxs-lookup"><span data-stu-id="4d59f-104">The documentation for the Quantum Development Kit takes on several different forms, such that information is readily available to quantum developers.</span></span>

<span data-ttu-id="4d59f-105">按照文档的原则[编写为代码](https://www.writethedocs.org/guide/docs-as-code/)，所有量子开发工具包文档都被格式化为代码，并使用 Git 进行管理，其方式与用于构建量程开发工具包的源代码相同。</span><span class="sxs-lookup"><span data-stu-id="4d59f-105">Following the principles of [Docs as Code](https://www.writethedocs.org/guide/docs-as-code/), all Quantum Development Kit documentation is formatted as code and is managed using Git in the same way as the source code that is used to build the Quantum Development Kit.</span></span>
<span data-ttu-id="4d59f-106">大多数情况下，代码支持文档由各种形式的[Markdown](https://daringfireball.net/projects/markdown/)组成，一种语言，用于以纯文本格式编写格式丰富的文本，该语言可在命令行、ide 和源代码管理中轻松使用。</span><span class="sxs-lookup"><span data-stu-id="4d59f-106">For the most part, the code backing documentation consists of various forms of [Markdown](https://daringfireball.net/projects/markdown/), a language for writing out richly formatted text in a plain text format that's easy to use at the command line, in IDEs, and with source control.</span></span>
<span data-ttu-id="4d59f-107">同样，我们采用[MathJax](https://www.mathjax.org/)库来允许使用 LaTeX 语言在文档中设置数学格式，如下所述。</span><span class="sxs-lookup"><span data-stu-id="4d59f-107">We similarly adopt the [MathJax](https://www.mathjax.org/) library to allow for formatting mathematics in documentation using the LaTeX language, as detailed further below.</span></span>


<span data-ttu-id="4d59f-108">也就是说，每种形式的文档在细节上都不同：</span><span class="sxs-lookup"><span data-stu-id="4d59f-108">That said, each form of documentation does vary somewhat in the details:</span></span>

- <span data-ttu-id="4d59f-109">**概念文档**包含一组发布到 https://docs.microsoft.com/quantum 的文章，这些文章介绍了从量程计算的基本知识到交换格式的技术规范的所有内容。</span><span class="sxs-lookup"><span data-stu-id="4d59f-109">The **conceptual documentation** consists of a set of articles that are published to https://docs.microsoft.com/quantum, and that describe everything from the basics of quantum computing to the technical specifications for interchange formats.</span></span> <span data-ttu-id="4d59f-110">这些文章以[DocFX-风格 Markdown （DFM）](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html)编写，后者用于创建丰富的文档集。</span><span class="sxs-lookup"><span data-stu-id="4d59f-110">These articles are written in [DocFX-Flavored Markdown (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), a Markdown variant used for creating rich documentation sets.</span></span>
- <span data-ttu-id="4d59f-111">**API 参考**是为每个 Q # 函数、操作和用户定义类型发布到 https://docs.microsoft.com/qsharp/api/ 的一组页。</span><span class="sxs-lookup"><span data-stu-id="4d59f-111">The **API reference** is a set of pages for each Q# function, operation, and user-defined type, published to https://docs.microsoft.com/qsharp/api/.</span></span> <span data-ttu-id="4d59f-112">这些页面记录每个可调用的输入和操作，以及示例和指向详细信息的链接。</span><span class="sxs-lookup"><span data-stu-id="4d59f-112">These pages document the inputs and operations to each callable, along with examples and links to more information.</span></span> <span data-ttu-id="4d59f-113">在每个版本中，将从 Q # 源代码中的小型 DFM 文档自动提取 API 引用。</span><span class="sxs-lookup"><span data-stu-id="4d59f-113">The API reference is automatically extracted from small DFM documents in Q# source code as a part of each release.</span></span>
- <span data-ttu-id="4d59f-114">每个示例和 kata 中包含的**自述文件<!---->** 的文件介绍了如何使用该示例或 kata、它所涵盖的内容以及它如何与量程开发工具包的其余部分相关。</span><span class="sxs-lookup"><span data-stu-id="4d59f-114">The **README<!---->.md** files included with each sample and kata describe how to use that sample or kata is used, what it covers, and how it relates to the rest of the Quantum Development Kit.</span></span> <span data-ttu-id="4d59f-115">这些文件是使用[GitHub 风格 Markdown （GFM）](https://github.github.com/gfm/)编写的，它是一种更轻量的替代方法，用于将文档直接附加到代码存储库。</span><span class="sxs-lookup"><span data-stu-id="4d59f-115">These files are written using [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/), a more lightweight alternative to DFM that's popular for attaching documentation directly to code repositories.</span></span>

## <a name="contributing-to-the-conceptual-documentation"></a><span data-ttu-id="4d59f-116">参与概念文档</span><span class="sxs-lookup"><span data-stu-id="4d59f-116">Contributing to the Conceptual Documentation</span></span> ##

<span data-ttu-id="4d59f-117">若要为概念文档或自述文档提供改进，请从拉取请求开始到[**MicrosoftDocs/量子**](https://github.com/MicrosoftDocs/quantum-docs-pr/
)、 [**microsoft/量子**](https://github.com/Microsoft/Quantum)或[**microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas)（适用时）。</span><span class="sxs-lookup"><span data-stu-id="4d59f-117">To contribute an improvement to the conceptual or README documentation, then, starts with a pull request onto either [**MicrosoftDocs/quantum-docs-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum), or [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), as is appropriate.</span></span>
<span data-ttu-id="4d59f-118">我们将在下面介绍有关拉取请求的详细信息，但现在，当你改进文档时，有几个问题值得注意：</span><span class="sxs-lookup"><span data-stu-id="4d59f-118">We'll describe more about pull requests below, but for now there's a few things that are good to keep in mind as you improve documentation:</span></span>

- <span data-ttu-id="4d59f-119">读者从非常多的背景到了量程开发工具包文档。</span><span class="sxs-lookup"><span data-stu-id="4d59f-119">Readers come to the Quantum Development Kit documentation from a very wide range of backgrounds.</span></span> <span data-ttu-id="4d59f-120">高中学生中的每个人都希望了解一些新的、令人兴奋的终身，执行量程计算研究应能够从文档中排除内容。</span><span class="sxs-lookup"><span data-stu-id="4d59f-120">Everyone from high school students looking to learn something new and exciting through to tenured faculty performing quantum computing research should be able to get something out of reading the documentation.</span></span> <span data-ttu-id="4d59f-121">在这种情况下，请不要对读者的部分进行广泛的了解，因为他们可能只是开始。如果可以提供清晰和可访问的说明，或者可提供其他资源的链接以获取详细信息，则此功能非常有用。</span><span class="sxs-lookup"><span data-stu-id="4d59f-121">To the extent that's possible, please don't assume extensive knowledge on the part of your readers, as they may just be starting out. It's most helpful if you can provide clear and accessible descriptions, or can provide links to other resources for more information.</span></span>
- <span data-ttu-id="4d59f-122">文档集不像书籍或文章那样布局，因为读者会收到类似于 "中间" 的内容。</span><span class="sxs-lookup"><span data-stu-id="4d59f-122">Documentation sets aren't laid out like books or papers, in that readers will arrive in what might seem like the "middle."</span></span> <span data-ttu-id="4d59f-123">例如，搜索引擎可能不建议索引，也可能是由朋友尝试帮助他们提供的链接。尝试通过始终提供清晰的上下文以及适当的链接来帮助读者。</span><span class="sxs-lookup"><span data-stu-id="4d59f-123">For example, search engines might not suggest the index, or they might have been sent a link by a friend trying to help them out. Try to help your reader by always providing a clear context, along with links where appropriate.</span></span>
- <span data-ttu-id="4d59f-124">有些读者将查找抽象语句和定义，这些语句和定义最有用，而其他读者最好通过推断具体的示例。</span><span class="sxs-lookup"><span data-stu-id="4d59f-124">Some readers will find abstract statements and definitions most helpful, while other readers work best by extrapolating from concrete examples.</span></span> <span data-ttu-id="4d59f-125">同时提供常规事例和具体的示例可帮助读者充分利用量程编程。</span><span class="sxs-lookup"><span data-stu-id="4d59f-125">Providing both the general case and specific examples can help both readers get the most out of quantum programming.</span></span>
- <span data-ttu-id="4d59f-126">尤其是在编写记录的代码的情况下，如果您的读者并不明显，您可能会很明显。</span><span class="sxs-lookup"><span data-stu-id="4d59f-126">Especially if you also wrote the code being documented, things may be obvious to you that are not at all obvious to your reader.</span></span> <span data-ttu-id="4d59f-127">没有一种独特的最佳方式来编程，因此无论读者有多么聪明，都不能猜到您在代码中表达创意最有用的设计模式。</span><span class="sxs-lookup"><span data-stu-id="4d59f-127">There's no one unique best way to program, so no matter how clever or experienced a reader might be, they can't guess at what design patterns you found the most helpful to express your ideas in code.</span></span> <span data-ttu-id="4d59f-128">清楚地了解读者如何预期使用您的代码可以帮助提供该上下文。</span><span class="sxs-lookup"><span data-stu-id="4d59f-128">Being clear about how a reader can expect to make use of your code can help provide that context.</span></span>
- <span data-ttu-id="4d59f-129">量程编程社区的许多成员都是学术研究人员，主要通过向社区发布内容的引文来识别。</span><span class="sxs-lookup"><span data-stu-id="4d59f-129">Many members of the quantum programming community are academic researchers, and are recognized mainly through citations for their contributions to the community.</span></span> <span data-ttu-id="4d59f-130">除了帮助读者查找其他资料外，还请确保正确引用学术输出（如论文、讨论、博客文章和软件工具），以帮助学术撰稿人继续提高社区的工作效果。</span><span class="sxs-lookup"><span data-stu-id="4d59f-130">In addition to helping readers find additional materials, making sure to properly cite academic outputs such as papers, talks, blog posts, and software tools can help academic contributors to keep doing their best work to improve the community.</span></span>
- <span data-ttu-id="4d59f-131">量程编程社区是广泛且 wonderfully 多样的社区。</span><span class="sxs-lookup"><span data-stu-id="4d59f-131">The quantum programming community is a broad and wonderfully diverse community.</span></span> <span data-ttu-id="4d59f-132">在第三人示例中使用 gendered 代词（例如： "如果用户 ...，他将 ..."）可以避免排除，而不是包括在内。</span><span class="sxs-lookup"><span data-stu-id="4d59f-132">The use of gendered pronouns in third-person examples (e.g.: "if a user ..., he will ...") can work to exclude rather than include.</span></span> <span data-ttu-id="4d59f-133">如果要在引文和链接中 cognizant 人们的姓名，并正确包含非 ASCII 字符，则可以通过显示其成员来为社区的多样性提供服务。</span><span class="sxs-lookup"><span data-stu-id="4d59f-133">Being cognizant of people's names in citations and links, and of the correct inclusion of non-ASCII characters can serve the diversity of the community by showing respect to its members.</span></span> <span data-ttu-id="4d59f-134">同样，英语中的许多词语通常以 hateful 的方式使用，因此，它们在技术文档中的使用可能会对单个读者和大型团体造成损害。</span><span class="sxs-lookup"><span data-stu-id="4d59f-134">Similarly, many words in the English language are often used in a hateful manner, such that their use in technical documentation can cause harm both to individual readers and to the community at large.</span></span>

## <a name="contributing-to-the-api-references"></a><span data-ttu-id="4d59f-135">参与 API 参考</span><span class="sxs-lookup"><span data-stu-id="4d59f-135">Contributing to the API References</span></span> ##

<span data-ttu-id="4d59f-136">若要对 API 引用做出改进，最有帮助的方法是直接在所记录的代码上打开拉取请求。</span><span class="sxs-lookup"><span data-stu-id="4d59f-136">To contribute an improvement to the API references, it's most helpful to open a pull request directly on the code being documented.</span></span>
<span data-ttu-id="4d59f-137">每个函数、操作或用户定义的类型都支持文档注释（用 `///` 而不是 `//`表示）。</span><span class="sxs-lookup"><span data-stu-id="4d59f-137">Each function, operation, or user-defined type supports a documentation comment (denoted with `///` instead of `//`).</span></span>
<span data-ttu-id="4d59f-138">当我们编译量程开发工具包的每个版本时，这些注释用于在 https://docs.microsoft.com/qsharp/api/ 生成 API 参考，其中包括有关每个可调用的输入和输出的详细信息，每个可调用的假设，以及如何使用它们的示例。</span><span class="sxs-lookup"><span data-stu-id="4d59f-138">When we compile each release of the Quantum Development Kit, these comments are used to generate the API reference at https://docs.microsoft.com/qsharp/api/, including details about the inputs to and outputs from each callable, the assumptions each callable makes, and examples of how to use them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d59f-139">请确保不手动编辑生成的 API 文档，因为每个新版本会覆盖这些文件。</span><span class="sxs-lookup"><span data-stu-id="4d59f-139">Please make sure to not manually edit the generated API documentation, as these files are overwritten with each new release.</span></span>
> <span data-ttu-id="4d59f-140">我们会将你对社区的贡献价值，并希望确保你的更改在发布后继续帮助用户发布。</span><span class="sxs-lookup"><span data-stu-id="4d59f-140">We value your contribution to the community, and want to make sure that your changes continue to help users release after release.</span></span>

<span data-ttu-id="4d59f-141">例如，请考虑一个 `PrepareTrialState(angles : Double[], register : Qubit[]) : Unit`的操作。</span><span class="sxs-lookup"><span data-stu-id="4d59f-141">For example, consider an operation `PrepareTrialState(angles : Double[], register : Qubit[]) : Unit`.</span></span>
<span data-ttu-id="4d59f-142">文档注释应有助于用户了解如何解释 `angles`、操作假定 `register`的初始状态、对 `register` 的影响等内容。</span><span class="sxs-lookup"><span data-stu-id="4d59f-142">A documentation comment should help a user learn how to interpret `angles`, what the operation assumes about the initial state of `register`, what the effect on `register` is, and so forth.</span></span>
<span data-ttu-id="4d59f-143">每个不同的信息片段都可通过文档注释中特殊命名的 Markdown 部分提供给 Q # 编译器。</span><span class="sxs-lookup"><span data-stu-id="4d59f-143">Each of these different pieces of information can be provided to the Q# compiler by a specially named Markdown section in the documentation comment.</span></span>
<span data-ttu-id="4d59f-144">在 `PrepareTrialState`的示例中，我们可能会编写如下所示的内容：</span><span class="sxs-lookup"><span data-stu-id="4d59f-144">For the example of `PrepareTrialState`, we might write something like the following:</span></span>

```qsharp
/// # Summary
/// Given a register of qubits, prepares them in a trial state by rotating each
/// independently.
///
/// # Description
/// This operation prepares the input register by performing a
/// $Y$ rotation on each qubit by an angle given in `angles`.
///
/// # Input
/// ## angles
/// An array of parameters
/// ## register
/// A register of qubits initially in the $\ket{00\cdots0}$ state.
///
/// # Example
/// To prepare an equal superposition $\ket{++\cdots+}$ over all input qubits:
/// ```qsharp
/// PrepareTrialState(ConstantArray(Length(register), PI() / 2.0), register);
/// ```
///
/// # Remarks
/// This operation is generally useful in the inner loop of an optimization
/// algorithm.
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.Ry
operation PrepareTrialState(angles : Double[], register : Qubit[]) : Unit {
    // ...
}
```

<span data-ttu-id="4d59f-145">除了文档编写的一般做法之外，在编写 API 文档注释中，这有助于保持几个要点：</span><span class="sxs-lookup"><span data-stu-id="4d59f-145">In addition to the general practice of documentation writing, in writing API documentation comments it helps to keep a few things in mind:</span></span>

- <span data-ttu-id="4d59f-146">每个文档注释的格式必须与 Q # 编译器要求文档正确显示的内容相匹配。</span><span class="sxs-lookup"><span data-stu-id="4d59f-146">The format of each documentation comment has to match what the Q# compiler expects for your documentation to appear correctly.</span></span> <span data-ttu-id="4d59f-147">某些部分（例如 `/// # Remarks` 允许任意格式的内容），而 `/// # See Also` 节等部分的限制更严格。</span><span class="sxs-lookup"><span data-stu-id="4d59f-147">Some sections, such as `/// # Remarks` allow for freeform content, while sections such as `/// # See Also` section are more restrictive.</span></span>
- <span data-ttu-id="4d59f-148">读者可以在主 API 参考站点、每个命名空间的摘要或通过使用悬停信息的 IDE 中读取 API 文档。</span><span class="sxs-lookup"><span data-stu-id="4d59f-148">A reader may read your API documentation on the main API reference site, on the summary for each namespace, or even from within their IDE through the use of hover information.</span></span> <span data-ttu-id="4d59f-149">确保 `/// # Summary` 比句子更长的时间可帮助读者快速确定是否需要进一步阅读或查看其他地方，并可帮助快速扫描命名空间摘要。</span><span class="sxs-lookup"><span data-stu-id="4d59f-149">Making sure that `/// # Summary` isn't longer than about a sentence helps your reader quickly sort out whether they need to read further or look elsewhere, and can help in quickly scanning through namespace summaries.</span></span>
- <span data-ttu-id="4d59f-150">您的文档与代码本身相比，您的文档可能会长得多，但这是正常的！</span><span class="sxs-lookup"><span data-stu-id="4d59f-150">Your documentation may well wind up being much longer than the code itself, but that's OK!</span></span> <span data-ttu-id="4d59f-151">即使是一小段代码，用户也不知道该代码存在的上下文。</span><span class="sxs-lookup"><span data-stu-id="4d59f-151">Even a small piece of code can have unexpected effects to users that don't know the context in which that code exists.</span></span> <span data-ttu-id="4d59f-152">通过提供具体的示例和清晰的说明，您可以帮助用户充分利用他们所提供的代码。</span><span class="sxs-lookup"><span data-stu-id="4d59f-152">By providing concrete examples and clear explanations, you can help users make the best use of the code that's available to them.</span></span>

<!-- ## LaTeX Formatting ##

**TODO** -->
