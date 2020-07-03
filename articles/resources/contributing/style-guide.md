---
title: 'Microsoft Q # 样式指南'
description: '了解 Q # 程序和库的命名、输入、文档和格式设置约定。'
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
ms.openlocfilehash: 3ddb5d67b972f69df1774b476a10e74dd16d97b7
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884191"
---
# <a name="q-style-guide"></a>Q # 样式指南 #
## <a name="general-conventions"></a>一般约定 ##

本指南中建议的约定旨在帮助以 Q # 编写编写的程序和库更易于阅读和理解。

## <a name="guidance"></a>指南

建议：

- 永远不要忽略约定，除非你有意这样做，以便为用户提供更具可读性且更易理解的代码。

## <a name="naming-conventions"></a>命名约定 ##

在提供量子开发工具包时，我们努力实现函数和操作名称，这些名称有助于量子开发人员编写易于阅读的程序，并最大程度地减少意外情况。
这种情况的一个重要部分是，当我们为函数、操作和类型选择名称时，我们将建立编程人员用来表示量程概念的*词汇*;利用我们的选择，我们可以在很大程度上帮助或阻止他们进行清晰的沟通。
这会给我们带来责任，以确保我们引入的名称更清晰，而不是隐匿性。
在本部分中，我们将详细说明我们如何在明确指导下实现这一义务，帮助我们通过 Q # 开发社区获得最佳帮助。

### <a name="operations-and-functions"></a>操作和函数 ###

名称应建立的首要任务之一就是给定的符号表示函数还是操作。
函数和操作之间的区别对于理解代码块的行为方式至关重要。
为了向用户传达函数和操作之间的区别，我们依赖于该 Q # 模型，通过使用副作用来进行量程操作。
也就是说，操作*执行*一些操作。

与此相反，函数说明了数据之间的数学关系。
表达式 `Sin(PI() / 2.0)` *为* `1.0` ，而不表示程序或其 qubits 的状态。

汇总是，操作在函数时执行操作。
这种区别意味着我们将操作命名为动词和函数作为名词。

> [!NOTE]
> 声明用户定义类型时，将同时隐式定义用于构造该类型的实例的新函数。
> 从这个角度来看，用户定义类型应命名为名词，使类型本身和构造函数具有一致的名称。

在合理的情况下，请确保操作名称以明确指示操作所使用的效果的动词开头。
例如：

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

值得特别提的一种情况是，操作采用另一操作作为输入并调用它。
在这种情况下，在定义外部操作时，输入操作执行的操作不会被清除，这样就不会立即清除正确的谓词。
建议谓词 `Apply` ，如 `ApplyIf` 、 `ApplyToEach` 和 `ApplyToFirst` 。
在这种情况下，其他谓词也可能有用，如中所示 `IterateThroughCartesianPower` 。

| Verb | 预期效果 |
| ---- | ------ |
| 应用 | 作为输入提供的操作称为 |
| Assert | 模拟器检查可能的量程度量结果的假设 |
| 估价 | 返回一个传统值，表示从一个或多个度量值中提取的估计值 |
| 度量 | 将执行量程度量，并将其结果返回给用户 |
| 准备 | 给定的 qubits 寄存器初始化为特定状态 |
| 示例 | 从某一分布中随机返回一个传统值 |

对于函数，我们建议避免使用谓词来取代常用名词（请参阅下面正确名词的指导）或形容词：

- `ConstantArray`
- `Head`
- `LookupFunction`

特别是，在几乎所有情况下，我们建议使用过去的 participles，以指示函数名称与量程程序中其他位置的操作或副作用强连接。
例如， `ControlledOnInt` 使用谓词 "control" 的分词部分形式指示函数充当形容词来修改其参数。
此名称具有与内置函子的语义相匹配的额外权益 `Controlled` ，如下面进一步所述。
同样，可以使用_代理名词_构造操作名称中的函数和 UDT 名称，如 `Encoder` 与强关联的 UDT 的名称相同 `Encode` 。

# <a name="guidance"></a>[指南](#tab/guidance)

建议：

- 为操作名称使用谓词。
- 使用名词或形容词作为函数名称。
- 将名词用于用户定义的类型和属性。
- 对于所有可调用名称，请 `CamelCase` 在、或中使用强首选项 `pascalCase` `snake_case` `ANGRY_CASE` 。 具体而言，请确保可调用名称以大写字母开头。
- 对于所有局部变量，请 `pascalCase` 在、或中使用强首选项 `CamelCase` `snake_case` `ANGRY_CASE` 。 具体而言，请确保本地变量以小写字母开头。
- 避免 `_` 在函数和操作名称中使用下划线; 需要其他级别的层次结构时，请使用命名空间和命名空间别名。

# <a name="examples"></a>[示例](#tab/examples)

|   | “属性” | 描述 |
|---|------|-------------|
| ☑ | `operation ReflectAboutStart` | 清除动词的使用（"反射"）以指示操作的效果。 |
| ☒ | <s>`operation XRotation`</s> | 使用名词短语建议函数，而不是操作。 |
| ☒ | <s>`operation search_oracle`</s> | 使用 `snake_case` Contravenes Q # 表示法。 |
| ☒ | <s>`operation Search_Oracle`</s> | 在操作名称 contravenes Q # 表示法内部使用下划线。 |
| ☑ | `function StatePreparationOracle` | 使用名词短语建议函数返回操作。 |
| ☑ | `function EqualityFact` | 清除名词的使用（"事实"），以指示这是一个函数，而形容词却是一个函数。 |
| ☒ | <s>`function GetRotationAngles`</s> | 使用谓词（"get"）表示这是一个操作。 |
| ☑ | `newtype GeneratorTerm` | 名词短语的使用显然是指调用 UDT 构造函数的结果。 |
| ☒ | <s>`@Attribute() newtype RunOnce()`</s> | 使用谓词短语建议 UDT 构造函数为操作。 |
| ☑ | `@Attribute() newtype Deprecated(Reason : String)` | 使用名词短语会传达属性的使用情况。 |

***

### <a name="entry-points"></a>入口点

在将入口点定义为 Q # 程序时，Q # 编译器会识别该[ `@EntryPoint()` 属性](xref:microsoft.quantum.core.entrypoint)，而无需输入点具有特定的名称（例如： `main` 、 `Main` 或 `__main__` ）。
也就是说，从 Q # 开发人员的角度来看，入口点是使用批注的普通操作 `@EntryPoint()` 。
此外，Q # 入口点可能是整个应用程序的入口点（即，在 Q # 独立可执行文件中），或者可能是 Q # 程序与应用程序的主机程序（即：将 Q # 与 Python 或 .NET 一起使用时）之间的一个接口，因此，在应用于 Q # 入口点时，名称 "main" 可能会产生误导。

建议使用命名入口点来反映属性的使用情况， `@EntryPoint()` 方法是使用上面列出的命名操作的一般建议。


# <a name="guidance"></a>[指南](#tab/guidance)

建议：

- 不要将入口点操作命名为 "main"。
- 将入口点操作命名为普通操作。

# <a name="examples"></a>[示例](#tab/examples)

|   | “属性” | 描述 |
|---|------|-------------|
| ☑ | `@EntryPoint() operation RunSimulation` | 通过操作名称清楚地传达入口点的用途。 |
| ☒ | <s>`@EntryPoint() operation Main`</s> | 使用 `Main` 不会清晰地传达入口点的目的，它是属性冗余的 `@EntryPoint()` 。 |

***

### <a name="shorthand-and-abbreviations"></a>速记和缩写 ###

上述建议（尽管如此）有很多形式的速记，可在量程计算中了解常见和普遍使用情况。
建议使用现有的和常见的速记，特别是对于目标计算机操作的内部操作。
例如，我们选择名称而不是 `X` `ApplyX` ，而 `Rz` 不是 `RotateAboutZ` 。
使用此类速记时，操作名称应全部大写（例如： `MAJ` ）。

在使用常用首字母缩写词和缩略词（例如 "QFT" 表示 "量程傅立叶转换"）时，应用此约定时需要注意一些。
建议遵循以下常规 .NET 约定，以便在全名中使用首字母缩写词和缩略词，这规定：

- 以大写形式命名两字母首字母缩写词和缩略词（例如： `BE` 对于 "大字节序"），
- 所有更长的首字母缩写词和缩略词在中命名 `CamelCase` （例如： `Qft` "量程傅立叶变换"）

因此，实现 QFT 的操作可以被称为 `QFT` 速记，或写出为 `ApplyQft` 。

对于特别常用的操作和函数，可能需要提供一个较长格式的简短名称作为_别名_：

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidance"></a>[指南](#tab/guidance)

建议：

- 适当时，请考虑经常接受和广泛使用的速记名称。
- 将大写字母用于速记。
- 将大写字母用于短（两字母）首字母缩写词和缩略词。
- 使用 `CamelCase` 更长（三个或更多字母）的首字母缩写词和缩略词。

# <a name="examples"></a>[示例](#tab/examples)

|   | “属性” | 描述 |
|---|------|-------------|
| ☑ | `X` | "应用 $X $ 转换" 的公认简写 |
| ☑ | `CNOT` | "受控-非" 的理解简写 |
| ☒ | <s>`Cnot`</s> | 速记不得为 `CamelCase` 。 |
| ☑ | `ApplyQft` | 常见的 initialism "QFT" 显示为长格式的名称的一部分。 |
| ☑ | `QFT` | 常见的 initialism "QFT" 显示为简写名称的一部分。 |



***


### <a name="proper-nouns-in-names"></a>名称中的正确名词 ###

尽管在物理学中，在第一位用户发布相关任务后，通常还会对其进行命名，因此，大多数非 physicists 不熟悉所有人的姓名和所有历史记录。
由于来自物理学的命名约定太大，因此，可能会给输入带来巨大的障碍，因为其他背景中的用户必须了解大量看似模糊的名称才能使用常见操作和概念。
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
因此，我们建议无论在哪一种合理的情况下，都要将描述概念的常用名词视为强首选项，以使描述概念的发布历史记录的正确名词。
例如，单独控制的交换和双向受控 NOT 操作通常称为学术文献中的 "Fredkin" 和 "Toffoli" 操作，但在 Q # 中标识为 `CSWAP` 和 `CCNOT` 。
在这两种情况下，API 文档注释都提供基于正确名词的同义词名称以及所有合适的引文。

如果始终需要使用正确名词的某些使用方式，则此首选项非常重要，例如，Q # 遵循许多传统语言所设置的传统语言（例如），并引用对 `Bool` 布尔值逻辑的引用中的类型，这反过来又以 George Boole 为荣誉。
几个量程概念的命名方式类似于类似的命名方式，其中包括 `Pauli` 对 Q # 语言的内置类型。
通过最大限度地减少使用正确名词的情况并不是很重要，我们将减少不能合理避免正确名词的影响。

# <a name="guidance"></a>[指南](#tab/guidance) 

建议：

- 不要在名称中使用正确名词。

# <a name="examples"></a>[示例](#tab/examples)

***

### <a name="type-conversions"></a>类型转换 ###

由于 Q # 是一种强类型和 staticly 类型的语言，因此只能使用对类型转换函数的显式调用将一种类型的值用作另一种类型的值。
这与允许值隐式更改类型（例如，类型提升）或通过强制转换的语言不同。
因此，类型转换函数在 Q # 库开发中扮演着重要的角色，并且包含有关命名的一个更常见的决策。
但请注意，由于类型转换始终是_确定性_的，因此可以将它们作为函数编写，因而会在上述建议的范围之内。
具体而言，我们建议不要将类型转换函数命名为谓词（例如： `ConvertToX` ）或副词 prepositional 短语（ `ToX` ），但应将其命名为形容词 prepositional 短语，指示源和目标类型（ `XAsY` ）。
在类型转换函数名称中列出数组类型时，建议采用速记 `Arr` 。
避免异常情况，我们建议使用命名所有类型转换函数， `As` 以便可以快速识别它们。

# <a name="guidance"></a>[指南](#tab/guidance)

建议：

- 如果函数将类型的值转换 `X` 为类型的值 `Y` ，请使用名称 `AsY` 或 `XAsY` 。

# <a name="examples"></a>[示例](#tab/examples)

|   | “属性” | 描述 |
|---|------|-------------|
| ☒ | <s>`ToDouble`</s> | 介词 "to" 会生成谓词短语，指示操作而不是函数。 |
| ☒ | <s>`AsDouble`</s> | 函数名称中不明确输入类型。 |
| ☒ | <s>`PauliArrFromBoolArr`</s> | 输入和输出类型的显示顺序不正确。 |
| ☑ | `ResultArrAsBoolArr` | 输入类型和输出类型都是明确的。 |

***

### <a name="private-or-internal-names"></a>专用或内部名称 ###

在许多情况下，名称将严格地用于库或项目的内部，并且不是库提供的 API 的保证部分。
清楚地表明，在命名函数和操作时，这种情况很有帮助，使得对仅限内部的代码的意外依赖关系变得显而易见。
如果操作或函数不能直接使用，而是应由部分应用程序操作的匹配可调用的使用，请考虑使用以关键字开头的名称，该名称以 `internal` 部分应用的可调用的开头。

# <a name="guidance"></a>[指南](#tab/guidance)

建议：

- 当函数、操作或用户定义类型不是 Q # 库或程序的公共 API 的一部分时，请通过将 `internal` 关键字置于 `function` 、 `operation` 或声明之前来确保将其标记为内部 `newtype` 。

# <a name="examples"></a>[示例](#tab/examples)

|   | “属性” | 描述 |
|---|------|-------------|
| ☒ | <s>`operation _ApplyDecomposedOperation`</s> | 不要使用下划线 `_` 指示此操作仅供内部使用。 |
| ☑ | `internal operation ApplyDecomposedOperation` | `internal`开头的关键字清楚地指示此操作仅供内部使用。 |

***
### <a name="variants"></a>变量 ###

尽管此限制可能不会在 Q # 的未来版本中保持不变，但目前这种情况下，通常会有一组相关的操作或函数，这些操作或函数可由函子它们的输入支持，或其参数的具体类型区分开来。
可以通过使用相同的根名称，后跟一个或两个指示其变体的字母来区分这些组。

| Suffix | 含义 |
|--------|---------|
| `A` | 需要输入支持`Adjoint` |
| `C` | 需要输入支持`Controlled` |
| `CA` | 需要输入才能支持 `Controlled` 和`Adjoint` |
| `I` | 输入或输入的类型为`Int` |
| `D` | 输入或输入的类型为`Double` |
| `L` | 输入或输入的类型为`BigInt` |

# <a name="guidance"></a>[指南](#tab/guidance)

建议：

- 如果函数或操作不与任何类似的函数或操作（由类型和函子支持的输入）相关联，请不要使用后缀。
- 如果函数或操作由类型和函子对其输入的支持相关联，则可使用上表中所示的后缀来区分变体。

# <a name="examples"></a>[示例](#tab/examples)

***

### <a name="arguments-and-variables"></a>参数和变量 ###

函数或操作的 Q # 代码的主要目标是使其易于阅读和理解。
同样，输入和类型参数的名称应传达函数或自变量在提供后的使用方式。


# <a name="guidance"></a>[指南](#tab/guidance)

建议：

- 对于所有变量和输入名称，请 `pascalCase` 在、或中使用强首选项 `CamelCase` `snake_case` `ANGRY_CASE` 。
- 输入名称应为描述性值;如果可能，请避免一个或两个字母名称。
- 仅接受一个类型自变量的操作和函数应 `T` 在其角色非常明显时用它来表示该类型参数。
- 如果函数或操作采用多个类型自变量，或者如果单个类型参数的角色不明显，请考虑 `T` `TOutput` 对每个类型使用以（例如：）开头的简短大写单词。
- 不要在参数和变量名称中包括类型名称;此信息可以并且应由您的开发环境提供。
- 按复数（）表示标量类型 `flagQubit` ，并按复数（）表示数组类型 `measResults` 。
  对于 qubits 的数组，请考虑以某种方式引用此类类型， `Register` 其中名称是以某种方式密切相关的 qubits 序列。
- 用作数组索引的变量应以开头 `idx` ，并且应为单数（例如： `things[idxThing]` ）。
  具体而言，请特别避免使用单字母变量名作为索引;请考虑至少使用 `idx` 。
- 用于保存数组长度的变量应以开头 `n` ，并且应为复数（例如： `nThings` ）。

# <a name="examples"></a>[示例](#tab/examples)

***

### <a name="user-defined-type-named-items"></a>用户定义的名为 Items 的类型 ###

用户定义类型中的命名项应命名为 `CamelCase` ，即使是在对 UDT 构造函数的输入中。
使用访问器表示法（例如： `callable::Apply` ）或复制和更新表示法（）时，这有助于清晰地将命名项与对本地范围变量的引用区分开来 `set arr w/= Data <- newData` 。

# <a name="guidance"></a>[指南](#tab/guidance)

建议：

- UDT 构造函数中的命名项应命名为 `CamelCase` ; 即，它们应以首字母大写开头。
- 解析为操作的已命名项应命名为谓词阶段。
- 不解析为操作的已命名项应命名为名词短语。
- 对于包装操作的 Udt，应定义名为的单个名为的项 `Apply` 。

# <a name="examples"></a>[示例](#tab/examples)

|   | 片段 | 描述 |
|---|---------|-------------|
| ☑ | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | 该名称 `Apply` 是一个 `CamelCase` 格式的谓词短语，建议指定的项是操作。 |
| ☒ | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | 命名项的开头应为大写字母。 |
| ☒ | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | 解析为函数的命名项应命名为名词短语，而不是谓词短语。 |

***

## <a name="input-conventions"></a>输入约定 ##

当开发人员调入操作或函数时，必须按特定顺序指定对该操作或函数的各种输入，从而增加开发人员所面临的认知负载以便使用库。
特别是，记住输入排序的任务通常是任务的一项干扰：对量程算法的实现进行编程。
尽管丰富的 IDE 支持可以将这种情况缓解到很大的作用，但很好的设计和遵从常见约定也有助于最大程度地减少 API 施加的认知负载。

在可能的情况下，减少操作或函数预期的输入数量可能会很有帮助，因此，每个输入的角色对于调用到该操作或函数中的开发人员和以后读取该代码的开发人员来说都是非常明显的。
特别是在不可能或不合理地减少操作或函数的参数数量时，必须具有一致的顺序，以便在预测输入顺序时最大程度地减少用户面临的意外情况。

我们建议使用部分应用程序，这种类型的排序约定主要是为了 currying f （x，y）≡ f （x）（y）的泛化。
因此，部分应用第一个参数应该导致可调用的，只要这种方法合理，就会很有用。
遵循此原则时，请考虑使用以下参数顺序：

- 传统的不可调用的参数，如角度、动力向量等。
- 可调用参数（函数和参数）。
  如果函数和操作都作为参数执行，请考虑在函数后放置运算。
- 可调用参数对其进行操作的集合的方法与 `Map` 、 `Iter` 、和类似 `Enumerate` `Fold` 。
- 用作控件的 Qubit 参数。
- 用作目标的 Qubit 参数。

考虑一个操作， `ApplyPhaseEstimationIteration` 该操作在采用角度和 oracle 的阶段估计中使用，传递 `Rz` 不同缩放因子数组所修改的角度，然后控制 oracle 的应用程序。
我们会按以下方式对输入进行排序 `ApplyPhaseEstimationIteration` ：

```qsharp
operation ApplyPhaseEstimationIteration(
    angle : Double,
    callable : (Qubit => () is Ctl),
    scaleFactors : Double[],
    controlQubit : Qubit,
    targetQubits : Qubit[]
)
: Unit
...
```
作为最大程度地减少意外情况的一种特殊情况，一些函数和操作会模仿内置函子和的行为 `Adjoint` `Controlled` 。
例如， `ControlledOnInt<'T>` 具有类似于 `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)` 函子的类型， `ControlledOnInt<Qubit[]>(5, _)` `Controlled` 但在控件寄存器表示状态 $ \ket {5} = \ket $ 的条件下 {101} 。
这样一来，开发人员需要输入才能 `ControlledOnInt` 将正在转换的调用放在最后，并且生成的操作采用函子的 `(Qubit[], 'T)` 输出---相同的顺序 `Controlled` 。

# <a name="guidance"></a>[指南](#tab/guidance)

建议：

- 与使用部分应用程序的使用一致的输入排序。
- 使用与内置函子一致的输入排序。
- 将所有经典输入置于任何量子输入之前。

# <a name="examples"></a>[示例](#tab/examples)

***

## <a name="documentation-conventions"></a>文档约定 ##

使用 Q # 语言，可以通过使用特殊格式的文档注释，将文档附加到操作、函数和用户定义的类型。
这些文档注释由三斜杠（ `///` ）表示，这是[DocFX-风格 Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html)文档，可用于描述每个操作、函数和用户定义类型的用途、每个预期的输入，等等。
使用量子开发工具包提供的编译器可提取这些注释，并使用它们来帮助录入文档，如中所示 https://docs.microsoft.com/quantum 。
同样，随量子开发工具包一起提供的语言服务器使用这些注释在用户将鼠标悬停在其 Q # 代码中的符号上方时向用户提供帮助。
利用文档注释，可以通过提供有用的参考来帮助用户理解代码，这是使用本文档中的其他约定不容易表达的详细信息。

<div class="nextstepaction">
    [文档注释语法参考](xref:microsoft.quantum.guide.filestructure#documentation-comments)
</div>

为了有效地使用此功能来帮助用户，我们建议你在编写文档注释时，记住几个事项。

# <a name="guidance"></a>[指南](#tab/guidance)

建议：

- 每个公共函数、操作和用户定义的类型后面都应跟有文档注释。
- 每个文档注释至少应包含以下部分：
    - 总结
    - 输入
    - 输出（如果适用）
- 确保所有摘要都是两个句子或更少。 如果需要更多空间，请在 `# Description` 后面提供 `# Summary` 完整的详细信息部分。
- 如果合理，则不要在摘要中包含数学，因为并非所有客户端都支持摘要中的 TeX 表示法。 请注意，在编写 prose 文档（例如 TeX 或 Markdown）时，最好使用较长的行长度。
- 在部分中提供所有相关的数学表达式 `# Description` 。
- 在描述输入时，请不要重复每个输入的类型，因为编译器可以推断这些类型，并且会导致不一致的风险。
- 提供相应的示例，每个示例都在各自的 `# Example` 部分中。
- 在列出代码之前，请简要说明每个示例。
- 将所有相关学术出版物（例如：论文、诉讼、博客文章和替代实现）引用 `# References` 为一节中的链接列表。
- 请确保在可能的情况下，所有引文链接都是永久和不可变的标识符（DOIs 或版本控制的 arXiv 数字）。
- 当某个操作或函数通过函子变体与其他操作或函数相关时，请将其他变体作为此部分中的项目符号列出 `# See Also` 。
- 在第1级（）节之间留空注释行 `/// #` ，但不要在第2级（）部分之间留有空行 `/// ##` 。

# <a name="examples"></a>[示例](#tab/examples)

#### <a name=""></a>☑ ####

```
/// # Summary
/// Applies a rotation about the X-axis by a given angle.
///
///
/// # Description
/// This operation rotates a single qubit by the unitary operation
/// \begin{align}
///     R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2}.
/// \end{align}
///
/// # Input
/// ## theta
/// Angle about which the qubit is to be rotated.
/// ## qubit
/// Qubit to which the gate should be applied.
///
/// # Remarks
/// Equivalent to:
/// ```qsharp
/// R(PauliX, theta, qubit);
/// ```
///
/// # See Also
/// - Ry
/// - Rz
operation Rx(theta : Double, qubit : Qubit) : Unit
is Adj + Ctl {
    body (...) { R(PauliX, theta, qubit); }
    adjoint (...) { R(PauliX, -theta, qubit); }
}
```

***

## <a name="formatting-conventions"></a>格式设置约定 ##

除了上述建议外，还有助于使代码尽可能清晰地使用一致的格式设置规则。
这种格式设置规则按性质，这种格式略有意义，并且是个人美观。
尽管如此，我们建议在一组协作者内维护一组一致的格式设置约定，特别是对于较大的 Q # 项目（如量子开发工具包本身）。
可以通过使用与 Q # 编译器集成的格式设置工具来自动应用这些规则。

# <a name="guidance"></a>[指南](#tab/guidance) 

建议：

- 使用四个空格而不是制表符来实现可移植性。
  例如，在 VS Code 中：
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- 行在合理的位置换行79个字符。
- 在二元运算符周围使用空格。
- 使用用于类型批注的冒号两侧的空格。
- 在数组和元组文本中使用逗号后使用单个空格（例如：在函数和操作的输入中）。
- 在函数、操作或 UDT 名称后，或在属性声明后面不要使用空格 `@` 。
- 每个属性声明都应在自己的行上。

# <a name="examples"></a>[示例](#tab/examples)

|   | 片段 | 描述 |
|---|---------|-------------|
| ☒ | <s>`2+3`</s> | 在二元运算符周围使用空格。 |
| ☒ | <s>`target:Qubit`</s> | 在类型批注冒号前后使用空格。 |
| ☑ | `Example(a, b, c)` | 输入元组中的项会正确地分隔以便于阅读。 |
| ☒ | <s>`Example (a, b, c)`</s> | 应在函数、操作或 UDT 名称后禁止显示空间。 |

***
