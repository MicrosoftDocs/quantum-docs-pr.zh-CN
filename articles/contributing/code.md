---
title: 参与代码 |Microsoft Docs
description: 发布代码
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.code
ms.openlocfilehash: 3ff15a744bf15924564d5a8fee54f4fbce4c04ee
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864417"
---
# <a name="contributing-code"></a><span data-ttu-id="6dd9c-103">贡献代码</span><span class="sxs-lookup"><span data-stu-id="6dd9c-103">Contributing Code</span></span> #

<span data-ttu-id="6dd9c-104">除了报告问题和改进文档外，对量子开发工具包编写代码也是一种非常直接的方式，可帮助您在量子编程社区中进行同行。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-104">In addition to reporting issues and improving documentation, contributing code to the Quantum Development Kit can be a very direct way to help your peers in the quantum programming community.</span></span>
<span data-ttu-id="6dd9c-105">通过编写代码，你可以帮助解决问题、提供新示例、使现有库更易于使用，甚至添加全新的功能。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-105">By contributing code, you can help to fix issues, provide new examples, make existing libraries easier to use, or even add entirely new features.</span></span>

<span data-ttu-id="6dd9c-106">在本指南中，我们将详细介绍我们查看拉取请求以帮助你的内容最好的情况。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-106">In this guide, we'll detail a bit of what we look for when we review pull requests to help your contribution do the most good.</span></span>

## <a name="what-we-look-for"></a><span data-ttu-id="6dd9c-107">我们要查找的内容</span><span class="sxs-lookup"><span data-stu-id="6dd9c-107">What We Look For</span></span> ##

<span data-ttu-id="6dd9c-108">理想的代码依赖项在量程开发工具包存储库中的现有工作基础上构建，以解决问题、扩展现有功能或添加存储库范围内的新功能。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-108">An ideal code contribution builds on the existing work in a Quantum Development Kit repository to fix issues, expand existing features, or to add new features that are within the scope of a repository.</span></span>
<span data-ttu-id="6dd9c-109">当我们接受代码贡献时，它将成为量子开发工具包本身的一部分，这样，将以与量程开发工具包的其余部分相同的方式发布、维护和开发新功能。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-109">When we accept a code contribution, it becomes a part of the Quantum Development Kit itself, such that new features will be released, maintained, and developed in the same way as the rest of the Quantum Development Kit.</span></span>
<span data-ttu-id="6dd9c-110">因此，当内容添加的功能经过充分测试并记录在文档中时，这会很有帮助。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-110">Thus, it is helpful when functionality added by a contribution is well-tested and is documented.</span></span>

### <a name="unit-tests"></a><span data-ttu-id="6dd9c-111">单元测试</span><span class="sxs-lookup"><span data-stu-id="6dd9c-111">Unit Tests</span></span> ###

<span data-ttu-id="6dd9c-112">构成库（如 canon）的 Q # 函数、操作和用户定义类型在[**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/)存储库中作为开发的一部分自动进行测试。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-112">The Q# functions, operations, and user-defined types that make up libraries such as the canon are automatically tested as a part of development on the [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) repository.</span></span>
<span data-ttu-id="6dd9c-113">例如，当打开一个新的拉取请求时， [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/)配置将检查拉取请求中的更改是否不会破坏该量程编程社区依赖的任何现有功能。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-113">When a new pull request is opened, for instance, our [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) configuration will check that the changes in the pull request do not break any existing functionality that the quantum programming community depends on.</span></span>

<span data-ttu-id="6dd9c-114">使用最新的 Q # 版本时，将使用 `@Test("QuantumSimulator")` 特性定义单元测试。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-114">With the latest Q# version, unit test are defined using the `@Test("QuantumSimulator")` attribute.</span></span> <span data-ttu-id="6dd9c-115">参数可以是 "QuantumSimulator"、"ToffoliSimulator"、"TraceSimulator"，也可以是指定执行目标的任何完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-115">The argument may be either "QuantumSimulator", "ToffoliSimulator", "TraceSimulator", or any fully qualified name specifying the execution target.</span></span> <span data-ttu-id="6dd9c-116">定义不同执行目标的多个属性可能附加到同一个可调用的。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-116">Several attributes defining different execution targets may be attached to the same callable.</span></span> <span data-ttu-id="6dd9c-117">某些测试仍使用不推荐使用的[Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/)包，该程序包公开以 `Test` 结束的[Xunit](https://xunit.github.io/)框架中的所有 Q # 函数和操作。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-117">Some of our tests still use the deprecated [Microsoft.Quantum.Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) package that exposes all Q# functions and operations ending in `Test` to the [xUnit](https://xunit.github.io/) framework.</span></span> <span data-ttu-id="6dd9c-118">定义单元测试不再需要此包。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-118">This package is no longer needed for defining unit tests.</span></span> 

<span data-ttu-id="6dd9c-119">以下函数用于确保 <xref:microsoft.quantum.canon.fst> 和 <xref:microsoft.quantum.canon.snd> 函数在一个代表性示例中返回正确的输出。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-119">The following function is used to ensure that the <xref:microsoft.quantum.canon.fst> and <xref:microsoft.quantum.canon.snd> functions both return the right outputs in a representative example.</span></span>
<span data-ttu-id="6dd9c-120">如果 `Fst` 或 `Snd` 的输出不正确，则使用 `fail` 语句来导致测试失败。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-120">If the output of `Fst` or `Snd` is incorrect, the `fail` statement is used to cause the test to fail.</span></span>

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

<span data-ttu-id="6dd9c-121">使用标准库指南的 "[测试" 部分](xref:microsoft.quantum.libraries.diagnostics)中的技术可以检查更复杂的条件。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-121">More complicated conditions can be checked using the techniques in the [testing section](xref:microsoft.quantum.libraries.diagnostics) of the standard libraries guide.</span></span>
<span data-ttu-id="6dd9c-122">例如，下面的测试检查 <xref:microsoft.quantum.canon.applywith> 调用的 `H(q); X(q); H(q);` 与 `Z(q)`执行的操作相同。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-122">For instance, the following test checks that `H(q); X(q); H(q);` as called by <xref:microsoft.quantum.canon.applywith> does the same thing as `Z(q)`.</span></span>

```qsharp
@Test("QuantumSimulator")
operation WithTest () : Unit {
    let actual = ApplyWith(H, X, _);
    let expected = Z;
    AssertOperationsEqualReferenced(ApplyToEach(actual, _), ApplyToEachA(expected, _), 4);
}
```

<span data-ttu-id="6dd9c-123">添加新功能时，最好还要添加新的测试，以确保你的内容可以执行该操作。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-123">When adding new features, it's a good idea to also add new tests to make sure that your contribution does what it's supposed to.</span></span>
<span data-ttu-id="6dd9c-124">这可以帮助其他社区维护和开发功能，特别有助于其他开发人员了解他们可以依赖你的功能。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-124">This helps the rest of the community to maintain and develop your feature, and in particular helps other developers know that they can rely on your feature.</span></span>

> [!NOTE]
> <span data-ttu-id="6dd9c-125">这也是另一种方法的工作原理！</span><span class="sxs-lookup"><span data-stu-id="6dd9c-125">This works the other way around, too!</span></span>
> <span data-ttu-id="6dd9c-126">如果现有功能缺少某些测试，请帮助我们添加测试覆盖范围，使其成为社区的良好贡献。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-126">If there's an existing feature that's missing some tests, helping us add test coverage would make a great contribution to the community.</span></span>

<span data-ttu-id="6dd9c-127">在本地，可以使用 Visual Studio 测试资源管理器或 `dotnet test` 命令来运行单元测试，以便在打开拉取请求之前查看你的发布。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-127">Locally, unit tests can be run using the Visual Studio Test Explorer or the `dotnet test` command, so that you can check your contribution before opening up a pull request.</span></span>

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->

## <a name="when-well-reject-a-pull-request"></a><span data-ttu-id="6dd9c-128">当我们拒绝拉取请求时</span><span class="sxs-lookup"><span data-stu-id="6dd9c-128">When We'll Reject a Pull Request</span></span> ##

<span data-ttu-id="6dd9c-129">有时，我们将拒绝对发布内容的拉取请求。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-129">Sometimes, we'll reject the pull request for a contribution.</span></span>
<span data-ttu-id="6dd9c-130">如果发生这种情况，这并不意味着这一点很糟糕，因为有许多原因导致我们无法接受特定的内容。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-130">If this happens to you, it doesn't mean that it's bad, as there's a number of reasons why we might not be able to accept a particular contribution.</span></span>
<span data-ttu-id="6dd9c-131">最常见的情况是，对量程编程社区的贡献非常不错，但量程开发工具包不是正确的开发工具包。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-131">Perhaps most commonly, a contribution to the quantum programming community is a really good one, but the Quantum Development Kit repositories aren't the right place to develop it.</span></span>
<span data-ttu-id="6dd9c-132">在这种情况下，我们强烈建议你将自己的存储库---部分的量程开发工具包，因为使用 GitHub 和 NuGet.org 可以轻松地创建和分发自己的库，这与分发 canon 和化学的方式相同。库。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-132">In such cases, we strongly encourage you to make your own repository --- part of the strength of the Quantum Development Kit is that it's easy to make and distribute your own libraries using GitHub and NuGet.org, the same way that we distribute the canon and chemistry libraries today.</span></span>

<span data-ttu-id="6dd9c-133">在其他时候，我们可能只是因为我们还没有准备好维护和开发它。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-133">At other times, we may reject a good contribution simply because we aren't yet ready to maintain and develop it.</span></span>
<span data-ttu-id="6dd9c-134">这可能很难完成所有操作，因此我们计划我们最能作为路线图来处理的功能。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-134">It can be difficult to do everything, so we plan out what features we're best able to work on as a roadmap.</span></span>
<span data-ttu-id="6dd9c-135">这可能是另一种用来将功能作为第三方库发布的情况。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-135">This can be another case where releasing a feature as a third-party library can make a lot of sense.</span></span>
<span data-ttu-id="6dd9c-136">另外，我们可能会要求你修改功能以更好地适应我们的路线图，以便我们能够完成我们的最佳工作。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-136">Alternatively, we may ask for your help in modifying a feature to better fit into our roadmap so that we can do the best work we can with it.</span></span>

<span data-ttu-id="6dd9c-137">如果拉取请求需要更多文档或单元测试来帮助我们使用它，或者与其他 Q # 库的其他样式有足够的样式，则还会询问拉取请求的更改，这会使用户难以找到功能。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-137">We'll also ask for changes to a pull request if it requires more documentation or unit tests to help us make use of it, or if it differs enough in style from the rest of the Q# libraries that it will make it harder for users to find your feature.</span></span>
<span data-ttu-id="6dd9c-138">在这些情况下，我们将尝试在代码评审中提供一些建议，以帮助你更轻松地加入你的内容。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-138">In these cases, we'll try to offer some advice in code reviews about what can be added or changed to make your contribution easier for us to include.</span></span>

<span data-ttu-id="6dd9c-139">最后，我们不能接受会损害量子计算社区的贡献，如[Microsoft 开放源代码行为准则](https://opensource.microsoft.com/codeofconduct/)中所述。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-139">Finally, we cannot accept contributions that cause harm the quantum computing community, as outlined in the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).</span></span>
<span data-ttu-id="6dd9c-140">我们想要确保贡献为整个量子计算社区提供服务，这两者都在其当前的日益多元化，在未来越来越多的情况下都是如此。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-140">We want to ensure that contributions serve the entire quantum computing community, both in its current wonderful diversity, and in the future as it grows to become still more inclusive.</span></span>
<span data-ttu-id="6dd9c-141">我们非常感谢您的帮助。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-141">We appreciate your help in realizing this goal.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6dd9c-142">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6dd9c-142">Next steps</span></span> ##

<span data-ttu-id="6dd9c-143">感谢帮助您为整个量程编程社区提供很大的资源。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-143">Thanks for helping to make the Quantum Development Kit a great resource for the entire quantum programming community!</span></span>
<span data-ttu-id="6dd9c-144">若要了解详细信息，请继续阅读有关 Q # 样式的以下指南。</span><span class="sxs-lookup"><span data-stu-id="6dd9c-144">To learn more, please continue with the following guide on Q# style.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6dd9c-145">了解 Q # 样式准则</span><span class="sxs-lookup"><span data-stu-id="6dd9c-145">Learn about Q# style guidelines</span></span>](xref:microsoft.quantum.contributing.style)
