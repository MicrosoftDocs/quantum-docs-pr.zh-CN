---
title: Microsoft QDK 的相关文档
description: 了解如何向 Microsoft 量程文档集提供概念性或 API 内容。
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: contributor-guide
uid: microsoft.quantum.contributing.docs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8602705d2dd071e822e2ff58a9a44cd0684f77f1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857356"
---
# <a name="improving-documentation"></a>改进文档

量程开发工具包的文档采用多种不同的形式，以使该信息可供量子开发人员使用。

按照文档的原则 [编写为代码](https://www.writethedocs.org/guide/docs-as-code/)，所有量子开发工具包文档都被格式化为代码，并使用 Git 进行管理，其方式与用于构建量程开发工具包的源代码相同。
大多数情况下，代码支持文档由各种形式的 [Markdown](https://daringfireball.net/projects/markdown/)组成，一种语言，用于以纯文本格式编写格式丰富的文本，该语言可在命令行、ide 和源代码管理中轻松使用。
同样，我们采用 [MathJax](https://www.mathjax.org/) 库来允许使用 LaTeX 语言在文档中设置数学格式，如下所述。


也就是说，每种形式的文档在细节上都不同：

- **概念文档** 包含一组发布到的文章 https://docs.microsoft.com/quantum ，这些文章介绍了从量程计算的基本知识到交换格式的技术规范的所有内容。 这些文章以 [DocFX-风格 Markdown (DFM) ](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html)（一种用于创建丰富文档集的 Markdown 变量）编写。
- **API 引用** 是发布到的每个 Q# 函数、操作和用户定义类型的一组页 https://docs.microsoft.com/qsharp/api/ 。 这些页面记录每个可调用的输入和操作，以及示例和指向详细信息的链接。 在每个版本中，将自动从源代码中的小型 DFM 文档中提取 API 引用 Q# 。
- 每个示例和 kata 附带的 **readme.txt <!---->** 文件介绍了如何使用该示例或 kata，它所涵盖的内容以及它如何与量程开发工具包的其余部分相关。 这些文件使用 [GitHub 风格 Markdown (GFM) ](https://github.github.com/gfm/)，这是一种更轻量的替代方法，用于将文档直接附加到代码存储库。

## <a name="contributing-to-the-conceptual-documentation"></a>参与概念文档

若要为概念文档或自述文档提供改进，请从拉取请求开始到 [**MicrosoftDocs/量子**](https://github.com/MicrosoftDocs/quantum-docs-pr/
)、 [**microsoft/量子**](https://github.com/Microsoft/Quantum)或 [**microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas)（适用时）。
我们将在下面介绍有关拉取请求的详细信息，但现在，当你改进文档时，有几个问题值得注意：

- 读者从非常多的背景到了量程开发工具包文档。 高中学生中的每个人都希望了解一些新的、令人兴奋的终身，执行量程计算研究应能够从文档中排除内容。 在这种情况下，请不要对读者的部分进行广泛的了解，因为他们可能只是开始。如果可以提供清晰和可访问的说明，或者可提供其他资源的链接以获取详细信息，则此功能非常有用。
- 文档集不像书籍或文章那样布局，因为读者会收到类似于 "中间" 的内容。 例如，搜索引擎可能不建议索引，也可能是由朋友尝试帮助他们提供的链接。尝试通过始终提供清晰的上下文以及适当的链接来帮助读者。
- 有些读者将查找抽象语句和定义，这些语句和定义最有用，而其他读者最好通过推断具体的示例。 同时提供常规事例和具体的示例可帮助读者充分利用量程编程。
- 尤其是在编写记录的代码的情况下，如果您的读者并不明显，您可能会很明显。 没有一种独特的最佳方式来编程，因此无论读者有多么聪明，都不能猜到您在代码中表达创意最有用的设计模式。 清楚地了解读者如何预期使用您的代码可以帮助提供该上下文。
- 量程编程社区的许多成员都是学术研究人员，主要通过向社区发布内容的引文来识别。 除了帮助读者查找其他资料外，还请确保正确引用学术输出（如论文、讨论、博客文章和软件工具），以帮助学术撰稿人继续提高社区的工作效果。
- 量程编程社区是广泛且 wonderfully 多样的社区。 在第三人示例中使用 gendered 代词 (例如： "如果用户 ...，它们将 ..." ) 可用于排除，而不是包括在内。 如果要在引文和链接中 cognizant 人们的姓名，并正确包含非 ASCII 字符，则可以通过显示其成员来为社区的多样性提供服务。 同样，英语中的许多词语通常以 hateful 的方式使用，因此，它们在技术文档中的使用可能会对单个读者和大型团体造成损害。

### <a name="referencing-sample-code-from-conceptual-articles"></a>从概念文章中引用示例代码

如果要将代码包含在 [示例存储库](https://github.com/Microsoft/Quantum)中，可以使用特殊的 DocFX-Flavored Markdown 命令执行此操作：

```markdown
:::code language="qsharp" source="~/quantum/samples/algorithms/chsh-game/Game.qs" range="4-8":::
```

此命令将[ `Game.qs` 从该 `chsh-game` 示例](https://github.com/microsoft/Quantum/blob/main/samples/algorithms/chsh-game/Game.qs)中导入第4行到第8行的文件，并将它们标记为 Q# 代码以进行语法突出显示。
使用此命令，您可以避免在概念项目和示例存储库之间复制代码，以便文档中的示例代码始终尽可能地保持最新。

### <a name="contributing-image-files"></a>参与图像文件

**重要提示**：若要使图像在暗色模式下正确呈现，必须避免使用透明胶片。

- 对于 .jpg 文件。 不需要执行任何操作，因为 .jpg 格式不支持透明元素。
- 对于 .png 文件，必须添加白色背景或将 alpha 通道的值更改为 **100**。 在 Windows 中执行此操作的最简单方法是在 " **画图** " 中打开该文件，并保存该文件，覆盖原始文件。
- 对于 svg 文件，必须在最底层添加白色矩形。 可以通过 **Inkscape** 执行此操作：
  1. 打开 svg 文件。
  1. 选择 "方形 maker" 工具，并在原始图形顶部绘制一个白色矩形。
  1. 选择工具 **选择并转换对象，** 方法是单击黑色箭头或按 **F1**。
  1. 选择该矩形时，单击工具栏元素 **将 (末尾) 底部的选定内容减小**。
  1. 用鼠标或箭头键调整矩形。

## <a name="contributing-to-the-api-references"></a>参与 API 参考

若要对 API 引用做出改进，最有帮助的方法是直接在所记录的代码上打开拉取请求。
每个函数、操作或用户定义的类型都支持文档注释 (用 `///` 代替) 表示 `//` 。
当我们编译量程开发工具包的每个版本时，这些注释用于生成 API 参考， https://docs.microsoft.com/qsharp/api/ 其中包括有关每个可调用的输入和输出的详细信息，每个可调用的假设，以及如何使用它们的示例。

> [!IMPORTANT]
> 请确保不手动编辑生成的 API 文档，因为每个新版本会覆盖这些文件。
> 我们会将你对社区的贡献价值，并希望确保你的更改在发布后继续帮助用户发布。

例如，请考虑函数 `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)` 。
文档注释应有助于用户了解如何解释 `bits` 和 `oracle` 以及函数的作用。
每个不同的信息片段都可 Q# 通过文档注释中特殊命名的 Markdown 部分提供给编译器。
对于的示例 `ControlledOnBitString` ，我们可能会编写如下所示的内容：

```qsharp
 /// # Summary
 /// Returns a unitary operation that applies an oracle on the target register if the 
 /// control register state corresponds to a specified bit mask.
 ///
 /// # Description
 /// The output of this function is an operation that can be represented by a
 /// unitary transformation $U$ such that
 /// \begin{align}
 ///     U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes
 ///     \begin{cases}
 ///         V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\
 ///         \ket{\psi} & \textrm{otherwise}
 ///     \end{cases},
 /// \end{align}
 /// where $V$ is a unitary transformation that represents the action of the
 /// `oracle` operation.
 ///
 /// # Input
 /// ## bits
 /// The bit string to control the given unitary operation on.
 /// ## oracle
 /// The unitary operation to be applied on the target register.
 ///
 /// # Output
 /// A unitary operation that applies `oracle` on the target register if the control 
 /// register state corresponds to the bit mask `bits`.
 ///
 /// # Remarks
 /// The length of `bits` and `controlRegister` must be equal.
 ///
 /// Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function
 /// is an operation that performs the following steps:
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits`;
 /// * apply `Controlled oracle` to the control and target registers;
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits` again to return the control register to the original state.
 ///
 /// The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.
 ///
 /// # Example
 /// The following code snippets are equivalent:
 /// ```qsharp
 /// (ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
 /// ```
 /// and
 /// ```qsharp
 /// within {
 ///     ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
 /// } apply {
 ///     Controlled oracle(controlRegister, targetRegister);
 /// }
 /// ```
 ///
 /// The following code prepares a state $\frac{1}{2}(\ket{00} - \ket{01} + \ket{10} + \ket{11})$:
 /// ```qsharp
 /// using (register = Qubit[2]) {
 ///     ApplyToEach(H, register);
 ///     (ControlledOnBitString([false], Z))(register[0..0], register[1]);
 /// }
 /// ```
 function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
 {
     return ControlledOnBitStringImpl(bits, oracle, _, _);
 }
```

可以在 [ `ControlledOnBitString` 函数的 API 文档](xref:Microsoft.Quantum.Canon.ControlledOnBitString)中查看上述代码的呈现版本。

除了文档编写的一般做法之外，在编写 API 文档注释中，这有助于保持几个要点：

- 每个文档注释的格式必须与 Q# 编译器要求文档正确显示的内容相匹配。 某些部分（例如 " `/// # Remarks` 允许" 自由格式的内容）和节等部分 `/// # See Also` 的限制更强。
- 读者可以在主 API 参考站点、每个命名空间的摘要或通过使用悬停信息的 IDE 中读取 API 文档。 确保 `/// # Summary` 不超过与句子相关的帮助读者快速确定是否需要进一步阅读或查看其他位置，并可帮助快速扫描命名空间摘要。
- 您的文档与代码本身相比，您的文档可能会长得多，但这是正常的！ 即使是一小段代码，用户也不知道该代码存在的上下文。 通过提供具体的示例和清晰的说明，您可以帮助用户充分利用他们所提供的代码。

<!-- ## LaTeX Formatting ##

**TODO** -->
