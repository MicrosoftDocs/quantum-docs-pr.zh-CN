---
title: 向 Microsoft QDK 发布代码
description: 了解如何将示例和库代码提供给 Microsoft Quantum Development Kit (QDK) 。
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.code
no-loc:
- Q#
- $$v
ms.openlocfilehash: 7a258a915a807b8e1ee7c2c9c062017d90f6a454
ms.sourcegitcommit: 685a8ab16d7e6a25e63a168d6e7c385fa6e876cc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91489759"
---
# <a name="contributing-code"></a><span data-ttu-id="a61bc-103">贡献代码</span><span class="sxs-lookup"><span data-stu-id="a61bc-103">Contributing Code</span></span>

<span data-ttu-id="a61bc-104">除了报告问题和改进文档外，对量子开发工具包编写代码也是一种非常直接的方式，可帮助您在量子编程社区中进行同行。</span><span class="sxs-lookup"><span data-stu-id="a61bc-104">In addition to reporting issues and improving documentation, contributing code to the Quantum Development Kit can be a very direct way to help your peers in the quantum programming community.</span></span>
<span data-ttu-id="a61bc-105">通过编写代码，你可以帮助解决问题、提供新示例、使现有库更易于使用，甚至添加全新的功能。</span><span class="sxs-lookup"><span data-stu-id="a61bc-105">By contributing code, you can help to fix issues, provide new examples, make existing libraries easier to use, or even add entirely new features.</span></span>

<span data-ttu-id="a61bc-106">在本指南中，我们将详细介绍我们查看拉取请求以帮助你的内容最好的情况。</span><span class="sxs-lookup"><span data-stu-id="a61bc-106">In this guide, we'll detail a bit of what we look for when we review pull requests to help your contribution do the most good.</span></span>

## <a name="what-we-look-for"></a><span data-ttu-id="a61bc-107">我们要查找的内容</span><span class="sxs-lookup"><span data-stu-id="a61bc-107">What We Look For</span></span>

<span data-ttu-id="a61bc-108">理想的代码依赖项在量程开发工具包存储库中的现有工作基础上构建，以解决问题、扩展现有功能或添加存储库范围内的新功能。</span><span class="sxs-lookup"><span data-stu-id="a61bc-108">An ideal code contribution builds on the existing work in a Quantum Development Kit repository to fix issues, expand existing features, or to add new features that are within the scope of a repository.</span></span>
<span data-ttu-id="a61bc-109">当我们接受代码贡献时，它将成为量子开发工具包本身的一部分，这样，将以与量程开发工具包的其余部分相同的方式发布、维护和开发新功能。</span><span class="sxs-lookup"><span data-stu-id="a61bc-109">When we accept a code contribution, it becomes a part of the Quantum Development Kit itself, such that new features will be released, maintained, and developed in the same way as the rest of the Quantum Development Kit.</span></span>
<span data-ttu-id="a61bc-110">因此，当内容添加的功能经过充分测试并记录在文档中时，这会很有帮助。</span><span class="sxs-lookup"><span data-stu-id="a61bc-110">Thus, it is helpful when functionality added by a contribution is well-tested and is documented.</span></span>

### <a name="unit-tests"></a><span data-ttu-id="a61bc-111">单元测试</span><span class="sxs-lookup"><span data-stu-id="a61bc-111">Unit Tests</span></span>

<span data-ttu-id="a61bc-112">Q#构成库（如 canon）的函数、操作和用户定义类型在[**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/)存储库中作为开发的一部分自动进行测试。</span><span class="sxs-lookup"><span data-stu-id="a61bc-112">The Q# functions, operations, and user-defined types that make up libraries such as the canon are automatically tested as a part of development on the [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) repository.</span></span>
<span data-ttu-id="a61bc-113">例如，当打开一个新的拉取请求时， [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) 配置将检查拉取请求中的更改是否不会破坏该量程编程社区依赖的任何现有功能。</span><span class="sxs-lookup"><span data-stu-id="a61bc-113">When a new pull request is opened, for instance, our [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) configuration will check that the changes in the pull request do not break any existing functionality that the quantum programming community depends on.</span></span>

<span data-ttu-id="a61bc-114">使用最新 Q# 版本，将使用属性定义单元测试 `@Test("QuantumSimulator")` 。</span><span class="sxs-lookup"><span data-stu-id="a61bc-114">With the latest Q# version, unit tests are defined using the `@Test("QuantumSimulator")` attribute.</span></span> <span data-ttu-id="a61bc-115">参数可以是 "QuantumSimulator"、"ToffoliSimulator"、"TraceSimulator"，也可以是指定运行目标的任何完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="a61bc-115">The argument may be either "QuantumSimulator", "ToffoliSimulator", "TraceSimulator", or any fully qualified name specifying the run target.</span></span> <span data-ttu-id="a61bc-116">定义不同的运行目标的多个属性可能附加到同一个可调用的。</span><span class="sxs-lookup"><span data-stu-id="a61bc-116">Several attributes defining different run targets may be attached to the same callable.</span></span> <span data-ttu-id="a61bc-117">某些测试仍使用不推荐使用的 [Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) 包，此包公开所有 Q# `Test` 以 [Xunit](https://xunit.github.io/) framework 结尾的函数和操作。</span><span class="sxs-lookup"><span data-stu-id="a61bc-117">Some of our tests still use the deprecated [Microsoft.Quantum.Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) package that exposes all Q# functions and operations ending in `Test` to the [xUnit](https://xunit.github.io/) framework.</span></span> <span data-ttu-id="a61bc-118">定义单元测试不再需要此包。</span><span class="sxs-lookup"><span data-stu-id="a61bc-118">This package is no longer needed for defining unit tests.</span></span> 

<span data-ttu-id="a61bc-119">以下函数用于确保 <xref:microsoft.quantum.canon.fst> 和 <xref:microsoft.quantum.canon.snd> 函数在有代表性的示例中返回正确的输出。</span><span class="sxs-lookup"><span data-stu-id="a61bc-119">The following function is used to ensure that the <xref:microsoft.quantum.canon.fst> and <xref:microsoft.quantum.canon.snd> functions both return the right outputs in a representative example.</span></span>
<span data-ttu-id="a61bc-120">如果或的输出 `Fst` 不 `Snd` 正确，则 `fail` 使用语句来导致测试失败。</span><span class="sxs-lookup"><span data-stu-id="a61bc-120">If the output of `Fst` or `Snd` is incorrect, the `fail` statement is used to cause the test to fail.</span></span>

```qsharp
@Test("QuantumSimulator")
function PairTest () : Unit {
    let pair = (12, PauliZ);

    if (Fst(pair) != 12) {
        let actual = Fst(pair);
        fail $"Expected 12, actual {actual}.";
    }

    if (Snd(pair) != PauliZ) {
        let actual = Snd(pair);
        fail $"Expected PauliZ, actual {actual}.";
    }
}
```

<span data-ttu-id="a61bc-121">使用标准库指南的 " [测试" 部分](xref:microsoft.quantum.libraries.diagnostics) 中的技术可以检查更复杂的条件。</span><span class="sxs-lookup"><span data-stu-id="a61bc-121">More complicated conditions can be checked using the techniques in the [testing section](xref:microsoft.quantum.libraries.diagnostics) of the standard libraries guide.</span></span>
<span data-ttu-id="a61bc-122">例如，下面的测试检查 `H(q); X(q); H(q);` 调用者是否执行与 <xref:microsoft.quantum.canon.applywith> 相同的操作 `Z(q)` 。</span><span class="sxs-lookup"><span data-stu-id="a61bc-122">For instance, the following test checks that `H(q); X(q); H(q);` as called by <xref:microsoft.quantum.canon.applywith> does the same thing as `Z(q)`.</span></span>

```Q#
@Test("QuantumSimulator")
operation TestApplyWith() : Unit {
    let actual = ApplyWith(H, X, _);
    let expected = Z;
    AssertOperationsEqualReferenced(ApplyToEach(actual, _), ApplyToEachA(expected, _), 4);
}
```

<span data-ttu-id="a61bc-123">添加新功能时，最好还要添加新的测试，以确保你的内容可以执行该操作。</span><span class="sxs-lookup"><span data-stu-id="a61bc-123">When adding new features, it's a good idea to also add new tests to make sure that your contribution does what it's supposed to.</span></span>
<span data-ttu-id="a61bc-124">这可以帮助其他社区维护和开发功能，特别有助于其他开发人员了解他们可以依赖你的功能。</span><span class="sxs-lookup"><span data-stu-id="a61bc-124">This helps the rest of the community to maintain and develop your feature, and in particular helps other developers know that they can rely on your feature.</span></span>

> [!NOTE]
> <span data-ttu-id="a61bc-125">这也是另一种方法的工作原理！</span><span class="sxs-lookup"><span data-stu-id="a61bc-125">This works the other way around, too!</span></span>
> <span data-ttu-id="a61bc-126">如果现有功能缺少某些测试，请帮助我们添加测试覆盖范围，使其成为社区的良好贡献。</span><span class="sxs-lookup"><span data-stu-id="a61bc-126">If there's an existing feature that's missing some tests, helping us add test coverage would make a great contribution to the community.</span></span>

<span data-ttu-id="a61bc-127">在本地，可以使用 Visual Studio 测试资源管理器或命令运行单元测试 `dotnet test` ，以便您可以在打开拉取请求前检查您的发布内容。</span><span class="sxs-lookup"><span data-stu-id="a61bc-127">Locally, unit tests can be run using the Visual Studio Test Explorer or the `dotnet test` command, so that you can check your contribution before opening up a pull request.</span></span>

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->

## <a name="pull-requests"></a><span data-ttu-id="a61bc-128">拉取请求</span><span class="sxs-lookup"><span data-stu-id="a61bc-128">Pull Requests</span></span>

<span data-ttu-id="a61bc-129">准备好进行工作时，请通过 GitHub 将拉取请求发送到相应的存储库。</span><span class="sxs-lookup"><span data-stu-id="a61bc-129">When you are ready to contribute your work, please send a Pull Request via GitHub to the corresponding repository.</span></span>
<span data-ttu-id="a61bc-130">团队将查看并提供反馈。</span><span class="sxs-lookup"><span data-stu-id="a61bc-130">The team will review and provide feedback.</span></span> <span data-ttu-id="a61bc-131">所有注释都需要回答和解决，并且在将代码合并到分支之前，所有检查都需要经过 `main` 。</span><span class="sxs-lookup"><span data-stu-id="a61bc-131">All comments need to be answered and resolved and all checks need to pass before the code is merged to the `main` branch.</span></span>

## <a name="when-well-reject-a-pull-request"></a><span data-ttu-id="a61bc-132">当我们拒绝拉取请求时</span><span class="sxs-lookup"><span data-stu-id="a61bc-132">When We'll Reject a Pull Request</span></span>

<span data-ttu-id="a61bc-133">有时，我们将拒绝对发布内容的拉取请求。</span><span class="sxs-lookup"><span data-stu-id="a61bc-133">Sometimes, we'll reject the pull request for a contribution.</span></span>
<span data-ttu-id="a61bc-134">如果发生这种情况，这并不意味着这一点很糟糕，因为有许多原因导致我们无法接受特定的内容。</span><span class="sxs-lookup"><span data-stu-id="a61bc-134">If this happens to you, it doesn't mean that it's bad, as there's a number of reasons why we might not be able to accept a particular contribution.</span></span>
<span data-ttu-id="a61bc-135">最常见的情况是，对量程编程社区的贡献非常不错，但量程开发工具包不是正确的开发工具包。</span><span class="sxs-lookup"><span data-stu-id="a61bc-135">Perhaps most commonly, a contribution to the quantum programming community is a really good one, but the Quantum Development Kit repositories aren't the right place to develop it.</span></span>
<span data-ttu-id="a61bc-136">在这种情况下，我们强烈建议你将自己的存储库---成为量程开发工具包的一部分，即使用 GitHub 和 NuGet.org 轻松创建和分发自己的库，这与我们目前分发 canon 和化学库的方式相同。</span><span class="sxs-lookup"><span data-stu-id="a61bc-136">In such cases, we strongly encourage you to make your own repository --- part of the strength of the Quantum Development Kit is that it's easy to make and distribute your own libraries using GitHub and NuGet.org, the same way that we distribute the canon and chemistry libraries today.</span></span>

<span data-ttu-id="a61bc-137">在其他时候，我们可能只是因为我们还没有准备好维护和开发它。</span><span class="sxs-lookup"><span data-stu-id="a61bc-137">At other times, we may reject a good contribution simply because we aren't yet ready to maintain and develop it.</span></span>
<span data-ttu-id="a61bc-138">这可能很难完成所有操作，因此我们计划我们最能作为路线图来处理的功能。</span><span class="sxs-lookup"><span data-stu-id="a61bc-138">It can be difficult to do everything, so we plan out what features we're best able to work on as a roadmap.</span></span>
<span data-ttu-id="a61bc-139">这可能是另一种用来将功能作为第三方库发布的情况。</span><span class="sxs-lookup"><span data-stu-id="a61bc-139">This can be another case where releasing a feature as a third-party library can make a lot of sense.</span></span>
<span data-ttu-id="a61bc-140">另外，我们可能会要求你修改功能以更好地适应我们的路线图，以便我们能够完成我们的最佳工作。</span><span class="sxs-lookup"><span data-stu-id="a61bc-140">Alternatively, we may ask for your help in modifying a feature to better fit into our roadmap so that we can do the best work we can with it.</span></span>

<span data-ttu-id="a61bc-141">如果拉取请求需要更多文档或单元测试来帮助我们使用它，或者与库的其余部分的样式完全不同，则还会询问拉取请求的更改，这 Q# 会使用户更难查找功能。</span><span class="sxs-lookup"><span data-stu-id="a61bc-141">We'll also ask for changes to a pull request if it requires more documentation or unit tests to help us make use of it, or if it differs enough in style from the rest of the Q# libraries that it will make it harder for users to find your feature.</span></span>
<span data-ttu-id="a61bc-142">在这些情况下，我们将尝试在代码评审中提供一些建议，以帮助你更轻松地加入你的内容。</span><span class="sxs-lookup"><span data-stu-id="a61bc-142">In these cases, we'll try to offer some advice in code reviews about what can be added or changed to make your contribution easier for us to include.</span></span>

<span data-ttu-id="a61bc-143">最后，我们不能接受会损害量子计算社区的贡献，如 [Microsoft 开放源代码行为准则](https://opensource.microsoft.com/codeofconduct/)中所述。</span><span class="sxs-lookup"><span data-stu-id="a61bc-143">Finally, we cannot accept contributions that cause harm the quantum computing community, as outlined in the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).</span></span>
<span data-ttu-id="a61bc-144">我们想要确保贡献为整个量子计算社区提供服务，这两者都在其当前的日益多元化，在未来越来越多的情况下都是如此。</span><span class="sxs-lookup"><span data-stu-id="a61bc-144">We want to ensure that contributions serve the entire quantum computing community, both in its current wonderful diversity, and in the future as it grows to become still more inclusive.</span></span>
<span data-ttu-id="a61bc-145">我们非常感谢您的帮助。</span><span class="sxs-lookup"><span data-stu-id="a61bc-145">We appreciate your help in realizing this goal.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a61bc-146">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a61bc-146">Next steps</span></span>

<span data-ttu-id="a61bc-147">感谢帮助您为整个量程编程社区提供很大的资源。</span><span class="sxs-lookup"><span data-stu-id="a61bc-147">Thanks for helping to make the Quantum Development Kit a great resource for the entire quantum programming community!</span></span>
<span data-ttu-id="a61bc-148">若要了解详细信息，请继续阅读以下 Q# 样式指南。</span><span class="sxs-lookup"><span data-stu-id="a61bc-148">To learn more, please continue with the following guide on Q# style.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a61bc-149">了解 Q# 样式准则</span><span class="sxs-lookup"><span data-stu-id="a61bc-149">Learn about Q# style guidelines</span></span>](xref:microsoft.quantum.contributing.style)

<span data-ttu-id="a61bc-150">根据你所提供的代码的类型，可能会有其他一些需要记住的事项，可帮助你使你的参与对社区的处理方式尽可能好。</span><span class="sxs-lookup"><span data-stu-id="a61bc-150">Depending on what kind of code you're contributing, there may be additional things to keep in mind that can help you make your contribution do as much good for the community as possible.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a61bc-151">了解相关示例</span><span class="sxs-lookup"><span data-stu-id="a61bc-151">Learn about contributing samples</span></span>](xref:microsoft.quantum.contributing.samples)
