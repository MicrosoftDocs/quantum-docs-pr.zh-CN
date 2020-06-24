---
title: 向 Microsoft QDK 发布代码
description: 了解如何将示例和库代码提供给 Microsoft Quantum Development Kit （QDK）。
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.code
ms.openlocfilehash: edc52dc4434e91258bece28812fd76b66329c6f9
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274383"
---
# <a name="contributing-code"></a>贡献代码

除了报告问题和改进文档外，对量子开发工具包编写代码也是一种非常直接的方式，可帮助您在量子编程社区中进行同行。
通过编写代码，你可以帮助解决问题、提供新示例、使现有库更易于使用，甚至添加全新的功能。

在本指南中，我们将详细介绍我们查看拉取请求以帮助你的内容最好的情况。

## <a name="what-we-look-for"></a>我们要查找的内容

理想的代码依赖项在量程开发工具包存储库中的现有工作基础上构建，以解决问题、扩展现有功能或添加存储库范围内的新功能。
当我们接受代码贡献时，它将成为量子开发工具包本身的一部分，这样，将以与量程开发工具包的其余部分相同的方式发布、维护和开发新功能。
因此，当内容添加的功能经过充分测试并记录在文档中时，这会很有帮助。

### <a name="unit-tests"></a>单元测试

构成库（如 canon）的 Q # 函数、操作和用户定义类型在[**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/)存储库中作为开发的一部分自动进行测试。
例如，当打开一个新的拉取请求时， [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/)配置将检查拉取请求中的更改是否不会破坏该量程编程社区依赖的任何现有功能。

使用最新的 Q # 版本，使用特性定义单元测试 `@Test("QuantumSimulator")` 。 参数可以是 "QuantumSimulator"、"ToffoliSimulator"、"TraceSimulator"，也可以是指定执行目标的任何完全限定名称。 定义不同执行目标的多个属性可能附加到同一个可调用的。 某些测试仍使用不推荐使用的[Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/)包，该包公开 `Test` 以[Xunit](https://xunit.github.io/) framework 结尾的所有 Q # 函数和操作。 定义单元测试不再需要此包。 

以下函数用于确保 <xref:microsoft.quantum.canon.fst> 和 <xref:microsoft.quantum.canon.snd> 函数在有代表性的示例中返回正确的输出。
如果或的输出 `Fst` 不 `Snd` 正确，则 `fail` 使用语句来导致测试失败。

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

使用标准库指南的 "[测试" 部分](xref:microsoft.quantum.libraries.diagnostics)中的技术可以检查更复杂的条件。
例如，下面的测试检查 `H(q); X(q); H(q);` 调用者是否执行与 <xref:microsoft.quantum.canon.applywith> 相同的操作 `Z(q)` 。

```Q#
@Test("QuantumSimulator")
operation TestApplyWith() : Unit {
    let actual = ApplyWith(H, X, _);
    let expected = Z;
    AssertOperationsEqualReferenced(ApplyToEach(actual, _), ApplyToEachA(expected, _), 4);
}
```

添加新功能时，最好还要添加新的测试，以确保你的内容可以执行该操作。
这可以帮助其他社区维护和开发功能，特别有助于其他开发人员了解他们可以依赖你的功能。

> [!NOTE]
> 这也是另一种方法的工作原理！
> 如果现有功能缺少某些测试，请帮助我们添加测试覆盖范围，使其成为社区的良好贡献。

在本地，可以使用 Visual Studio 测试资源管理器或命令运行单元测试 `dotnet test` ，以便您可以在打开拉取请求前检查您的发布内容。

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->


## <a name="when-well-reject-a-pull-request"></a>当我们拒绝拉取请求时

有时，我们将拒绝对发布内容的拉取请求。
如果发生这种情况，这并不意味着这一点很糟糕，因为有许多原因导致我们无法接受特定的内容。
最常见的情况是，对量程编程社区的贡献非常不错，但量程开发工具包不是正确的开发工具包。
在这种情况下，我们强烈建议你将自己的存储库---成为量程开发工具包的一部分，即使用 GitHub 和 NuGet.org 轻松创建和分发自己的库，这与我们目前分发 canon 和化学库的方式相同。

在其他时候，我们可能只是因为我们还没有准备好维护和开发它。
这可能很难完成所有操作，因此我们计划我们最能作为路线图来处理的功能。
这可能是另一种用来将功能作为第三方库发布的情况。
另外，我们可能会要求你修改功能以更好地适应我们的路线图，以便我们能够完成我们的最佳工作。

如果拉取请求需要更多文档或单元测试来帮助我们使用它，或者与其他 Q # 库的其他样式有足够的样式，则还会询问拉取请求的更改，这会使用户难以找到功能。
在这些情况下，我们将尝试在代码评审中提供一些建议，以帮助你更轻松地加入你的内容。

最后，我们不能接受会损害量子计算社区的贡献，如[Microsoft 开放源代码行为准则](https://opensource.microsoft.com/codeofconduct/)中所述。
我们想要确保贡献为整个量子计算社区提供服务，这两者都在其当前的日益多元化，在未来越来越多的情况下都是如此。
我们非常感谢您的帮助。

## <a name="next-steps"></a>后续步骤

感谢帮助您为整个量程编程社区提供很大的资源。
若要了解详细信息，请继续阅读有关 Q # 样式的以下指南。

> [!div class="nextstepaction"]
> [了解 Q # 样式准则](xref:microsoft.quantum.contributing.style)

根据你所提供的代码的类型，可能会有其他一些需要记住的事项，可帮助你使你的参与对社区的处理方式尽可能好。

> [!div class="nextstepaction"]
> [了解相关示例](xref:microsoft.quantum.contributing.samples)
