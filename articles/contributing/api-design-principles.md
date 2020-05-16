---
title: 'Q # API 设计原则'
description: 'Q # API 设计原则'
author: cgranade
ms.author: chgranad
ms.date: 3/9/2020
ms.topic: article
uid: microsoft.quantum.contributing.api-design
ms.openlocfilehash: def6a9f12accfa399fd4db3783b9899fc743f025
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426447"
---
# <a name="q-api-design-principles"></a>Q # API 设计原则

## <a name="introduction"></a>简介

作为一种语言和平台，Q # 使用户能够编写、运行、了解和探索量程应用程序。
若要为用户提供支持，请在设计 Q # 库时，按照一组 API 设计原则来指导我们的设计，并帮助我们为量子开发社区提供可用库。
本文列出了这些原则，并提供示例来帮助指导如何在设计 Q # Api 时应用这些原则。

> [!TIP]
> 这是一个相当详细的文档，旨在帮助指导库开发和深度库内容。
> 如果你在 Q # 中编写自己的库，或者如果你要将更大的功能提供给[q # 库存储库](https://github.com/microsoft/QuantumLibraries)，则可能会发现它最有用。
>
> 另一方面，如果你想要了解如何更常见地参与量程开发工具包，则建议从[贡献指南](xref:microsoft.quantum.contributing)开始。
> 如果你要查找有关我们建议如何设置你的 Q # 代码格式的更多常规信息，你可能会对签出[样式指南](xref:microsoft.quantum.contributing.style)感兴趣。

## <a name="general-principles"></a>一般原则

**关键原则：** 公开将焦点放在量程应用程序上的 Api。

- ✅**选择反映**算法和应用程序的高级结构的操作和函数名称。
- ⛔️**不**公开主要依赖于低级别实现细节的 api。

**关键原则：** 使用示例用例启动每个 API 设计，以确保 Api 直观地使用。

- ✅**请确保公共**API 的每个组件都有相应的用例，而不是尝试针对所有可能的用法进行设计。
    以不同的方式进行设置，如果它们很有用，请不要引入公共 Api，但请确保 API 的每个部分都有一个*具体*的示例。

  *示例：*
  - @"microsoft.quantum.canon.applytoeachca"可用作 `ApplyToEachCA(H, _)` 以统一 superposition 状态准备寄存器，这是许多量程算法中的常见任务。 同样的操作还可用于准备、数字和基于 oracle 的算法中的许多其他任务。

- ✅**进行**集体讨论和研讨会新的 API 设计，以仔细检查它们是否直观，并满足建议的用例。

  *示例：*
  - 检查当前 \# 的问答代码，了解新的 API 设计如何简化和阐明现有实现。
  - 查看建议的 API 设计与主要受众的代表。

**关键原则：** 设计 Api 以支持和鼓励可读代码。

- ✅**请确保代码**可供域专家和非专家使用。
- ✅**请将重点放在**高级算法中的每个操作和功能的效果上，并使用文档深入了解具体的实现细节。
- ✅如果适用，**请遵循常见**的[Q \# 样式指南](xref:microsoft.quantum.contributing.style)。

**关键原则：** 设计稳定的 Api，提供向前兼容性。

- ✅如果需要进行重大更改，**请**正常弃用旧 api。

- ✅**请**提供 "填充程序" 操作和函数，使现有用户代码在弃用期间能够正常运行。

  *示例：*
  - 将调用的操作重命名 `EstimateExpectation` 为时 `EstimateAverage` ，引入一个名为的新操作， `EstimateExpectation` 该操作在其新名称上调用原始操作，以便现有代码可以继续正常工作。

- ✅**使用**属性将 @"microsoft.quantum.core.deprecated" 弃用功能传达给用户。

- ✅重命名操作或函数**时，请**将新名称提供为的字符串输入 `@Deprecated` 。

- ⛔️不会在预览版本至少包含六个月的时间内删除现有的函数或操作，也**不能**删除至少两年的支持版本。

## <a name="functions-and-operations"></a>函数和操作

**关键原则：** 确保每个函数和操作在 API 中都有一个明确定义的用途。

- ⛔️**不**公开执行多个不相关任务的函数和操作。

**关键原则：** 设计函数和操作以尽可能地重复使用，并预测将来的需求。

- ✅在同一 API 和之前的现有库中，**请设计函数**和操作，使其与其他函数和操作很好地结合。

  *示例：*
  - 此 @"microsoft.quantum.canon.delay" 操作对其输入做出最小假设，因此可用于延迟 Q # 标准库或用户定义的操作的应用程序。
    <!-- TODO: define bad example. -->

- ✅将纯粹确定的传统逻辑作为函数**而不是操作公开。**

  *示例：*
  - 可以确定如何以确定性的方式写入其浮点输入的子例程，因此应将其公开给用户， `Squared : Double -> Double` 而不是作为一个操作公开给用户 `Square : Double => Double` 。 这允许在更多位置（例如，在其他函数中）调用子例程，并向编译器提供有用的优化信息，从而影响性能和优化。
  - `ForEach<'TInput, 'TOutput>('TInput => 'TOutput, 'TInput[]) => 'TOutput[]`与 `Mapped<'TInput, 'TOutput>('TInput -> 'TOutput, 'TInput[]) -> 'TOutput[]` 确定性有关的保证不同; 两者在不同情况下都很有用。
  - 转换量程操作应用程序的 API 例程经常以确定性的方式执行，因此可作为函数提供 `CControlled<'T>(op : 'T => Unit) => ((Bool, 'T) => Unit)` 。

- ✅根据需要使用类型参数，对每个函数和操作尽可能多**地通用化输入**类型。

  *示例：*
  - `ApplyToEach`具有类型 `<'T>(('T => Unit), 'T[]) => Unit` ，而不是其最常见的应用程序的特定类型 `((Qubit => Unit), Qubit[]) => Unit` 。

> [!TIP]
> 务必要预测未来需求，但解决用户的具体问题也很重要。
> 因此，在这种关键原则上，始终需要仔细考虑和平衡，以避免开发 Api "以防万一"。

**关键原则：** 选择可预测的函数和操作的输入和输出类型，并传达可调用的用途。

- ✅**请**使用元组类型对输入和输出进行逻辑分组，这些输入和输出在一起被视为非常重要。 在这些情况下，请考虑使用用户定义的类型。

  *示例：*
  - 用于输出另一个函数的本地最小值的函数可能需要将搜索间隔的界限作为输入，以使 `LocalMinima(fn : (Double -> Double), (left : Double, right : Double)) : Double` 其成为适当的签名。
  - 使用参数移位技术估算机器学习分类器衍生的操作可能需要将移位和 unshifted 参数向量作为输入。 `(unshifted : Double[], shifted : Double[])`在这种情况下，可能适合使用类似于的输入。

- ✅在不同的函数和操作中一致地对输入和输出元组中的项**进行**排序。

  *示例：*
  - 如果考虑每个或函数或操作分别采用旋转角度和目标 qubit 作为输入，请确保在每个输入元组中对它们进行排序。 也就是说，使用和 `ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl` `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` `ApplyRotation(target : Qubit, angle : Double) : Unit is Adj + Ctl` `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` 。

**关键原则：** 设计函数和操作，以便与 \# 部分应用程序等 Q 语言功能正常工作。

- ✅在输入元组中对项**进行**排序，以便首先发生最常应用的输入（即：使部分应用程序的行为类似于 currying）。

  *示例：*
  - `ApplyRotation`采用浮点数和 qubit 作为输入的操作通常可能会部分应用于浮点输入，后者首先与需要类型输入的操作一起使用 `Qubit => Unit` 。 因此，签名为`operation ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl`
      与部分应用程序的工作方式最一致。
  - 通常，此指导是指将所有的传统数据放在输入元组中的所有 qubits 之前，但使用合理的判断，并检查如何在实践中调用 API。

## <a name="user-defined-types"></a>用户定义类型

**关键原则：** 使用用户定义的类型来帮助使 api 更具表现力且便于使用。

- ✅**请**引入新的用户定义类型，为长和/或复杂类型提供有用的速记。

  *示例：*
  - 在以下情况下，具有三个 qubit 数组输入的操作类型通常作为输入或作为输出返回，提供 UDT，如`newtype TimeDependentBlockEncoding = ((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl)`
      有助于提供有用的速记。

- ✅**请**引入新的用户定义类型，以指示给定的基类型仅应在非常特殊的意义上使用。

  *示例：*
  - 应专门将操作解释为将古典数据编码为量程寄存器的操作，可能适合使用用户定义类型进行标记 `newtype InputEncoder = (Apply : (Qubit[] => Unit))` 。

- ✅**确实**会引入新的用户定义类型，其中包含允许将来可扩展性的命名项（例如：以后可能包含其他命名项的结果结构）。

  *示例：*
  - 当某个操作 `TrainModel` 公开大量配置选项时，将这些选项公开为新的 `TrainingOptions` UDT 并提供新函数， `DefaultTrainingOptions : Unit -> TrainingOptions` 使用户能够在 TrainingOptions UDT 值中重写特定的已命名项，同时仍允许库开发人员根据需要添加新的 UDT 项。

- ✅为要求用户了解正确的元组析构，**请**为新的用户定义类型声明命名项。

  *示例：*
  - 如果在其极坐标分解中表示复数，则优先使用 `newtype ComplexPolar = (Magnitude: Double, Argument: Double)` `newtype ComplexPolar = (Double, Double)` 。

**关键原则：** 通过使用用户定义的类型来降低认知负载，无需用户了解其他概念和命名法。

- ⛔️**不**会引入要求用户频繁使用解包运算符（）的用户定义类型 `!` ，也不会引入通常需要多个解包级别的用户定义类型。 可能的缓解策略包括：

  - 使用单个项公开用户定义类型时，请考虑定义该项的名称。 例如， `newtype Encoder = (Apply : (Qubit[] => Unit is Adj + Ctl))` 将优先考虑到 `newtype Encoder = (Qubit[] => Unit is Adj + Ctl)` 。

  - 确保其他函数和操作可以直接接受 "包装的" UDT 实例。

- ⛔️**不**会引入重复内置类型的新用户定义类型，而不提供其他表现力。

  *示例：*
  - UDT `newtype QubitRegister = Qubit[]` 不提供任何其他表现力 `Qubit[]` ，因此更难使用而无明显权益。
  - UDT `newtype LittleEndian = Qubit[]` 记录了如何使用和解释基础寄存器，从而提供了超出其基类型的其他表现力。

- 除非严格要求，否则⛔️**不**引入访问器函数;  在这种情况下，强烈喜欢命名项。

  *示例：*
  - 引入 UDT 时 `newtype Complex = (Double, Double)` ，最好将定义修改为 `newtype Complex = (Real : Double, Imag : Double)` 以引入函数 `GetReal : Complex -> Double` 和 `GetImag : Complex -> Double` 。

## <a name="namespaces-and-organization"></a>命名空间和组织

**关键原则：** 选择可预测的命名空间名称，并在每个命名空间中清楚地传达函数、操作和用户定义类型的用途。

- ✅将命名**空间命名为** `Publisher.Product.DomainArea` 。

  *示例：*
  - 作为量程开发工具包的量程模拟功能的一部分，由 Microsoft 发布的函数、操作和 Udt 置于 `Microsoft.Quantum.Simulation` 命名空间中。
  - `Microsoft.Quantum.Math`表示由 Microsoft 发布的命名空间，它是与数学域区相关的量程开发工具包的一部分。

- ✅将用于特定功能的操作、函数和用户定义类型放置到描述该功能的命名空间中，即使在不同的问题域中使用该功能，也**是如此。**

  *示例：*
  - 作为量程开发工具包的一部分，由 Microsoft 发布的状态准备 Api 将放入中 `Microsoft.Quantum.Preparation` 。
  - 将 Microsoft 发布的量程模拟 Api 作为量程开发工具包的一部分进行放置 `Microsoft.Quantum.Simulation` 。

- ✅**将仅**在特定域中使用的操作、函数和用户定义类型放入命名空间，以指示其实用工具的域。 如果需要，请使用子命名空间来指示每个特定于域的命名空间中的焦点任务。

  *示例：*
  - Microsoft 发布的量程机器学习库主要放在 @"microsoft.quantum.machinelearning" 命名空间中，但示例数据集由 @"microsoft.quantum.machinelearning.datasets" 命名空间提供。
  - 作为量程开发工具包的一部分，由 Microsoft 发布的量程化学 Api 应置于 `Microsoft.Quantum.Chemistry` 。 用于实现约旦--Wigner 分解的特定功能可能会放在中 `Microsoft.Quantum.Chemistry.JordanWigner` ，因此，适用于量程化学域区域的主接口不涉及实现。

**关键原则：** 将命名空间和访问修饰符一起用于蓄意向用户公开的 API 图面，并隐藏与 Api 实现和测试相关的内部详细信息。

- ✅只要合理，就会将实现 API 所需的所有函数和操作放入与正在实现的 API 相同的命名空间中，但使用 "private" 或 "internal"**关键字进行标记**，以指示它们不属于库的公共 API 图面。 使用以下划线（）开头的名称 `_` ，以直观区分公共 callables 中的私有和内部操作和函数。

  *示例：*
  - 操作名称 `_Features` 指示一个专用于给定命名空间和程序集的函数，并且应带有 `internal` 关键字。

- ✅在极少数情况下，若要实现给定命名空间的**API，需要**使用一组丰富的私有函数或操作，请将它们放在一个与正在实现和结束的命名空间相匹配的新命名空间中 `.Private` 。

- ✅**将所有**单元测试置于与受测命名空间匹配的命名空间中，并以结尾 `.Tests` 。

## <a name="naming-conventions-and-vocabulary"></a>命名约定和词汇

**关键原则：** 跨各种受众（包括量子新手和专家），选择清晰、可访问和可读取的名称和术语。

- ⛔️**请勿**使用歧视或 exclusionary 标识符名称，也不会在 API 文档注释中使用术语。

- ✅**使用 API**文档注释来提供相关的上下文、示例和引用，尤其是对于更难的概念。

- ⛔️**不**会使用不必要的深奥或需要大量的量程算法知识来读取的标识符名称。

  *示例：*
  - 首选 "调幅放大迭代" 到 "Grover 迭代"。

- ✅**选择操作**和函数名称可以清楚地传达可调用的预期效果，而不是其实现。 请注意，可在[API 文档注释](xref:microsoft.quantum.guide.filestructure#documentation-comments)中记录实现。

  *示例：*
  - 由于后者传达了前者的实现方式，因此更喜欢 "估计重叠" 到 "Hadamard 测试"。

- ✅在所有 Q api 中以一致的**方式使用字词** \# ：

  - **谓词**

    - **断言**：检查有关目标计算机及其 qubits 的状态的假设，可能是通过使用 unphysical 资源来保存。 使用此谓词的操作应始终安全删除，而不会影响库和可执行程序的功能。 请注意，与事实不同，断言可能一般取决于外部状态，如 qubit 寄存器的状态、执行环境等。 由于与外部状态的依赖关系是一种副作用，因此必须将断言作为运算公开，而不是作为函数公开。

    - **估计**：使用一个或多个可能重复的度量，从度量结果中估计一个传统的数量。

      *示例：*
      - @"microsoft.quantum.characterization.estimatefrequency"
      - @"microsoft.quantum.characterization.estimateoverlapbetweenstates"

    - **准备**：将量程操作或一系列操作应用到一个或多个 qubits （通常是 $ \ket{00\cdots 0} $），这会导致这些 qubits 的状态发展到所需的结束状态。 通常，在给定的开始状态以外的其他状态下，**可能会**导致未定义的单一转换，但仍**应**保留操作及其 adjoint "取消"，并应用无操作。

      *示例：*
      - @"microsoft.quantum.preparation.preparearbitrarystate"
      - @"microsoft.quantum.preparation.prepareuniformsuperposition"

    - **Measure**：向一个或多个 qubits 应用量程操作或一系列操作，读取传统数据。

      *示例：*
      - @"microsoft.quantum.intrinsic.measure"
      - @"microsoft.quantum.arithmetic.measurefxp"
      - @"microsoft.quantum.arithmetic.measureinteger"

    - **Apply**：向一个或多个 qubits 应用量程运算或一系列操作，从而使这些 qubits 的状态以一致的方式进行更改。 此谓词是 Q 命名法中最常见的动词 \# ，**不应**在更具体的动词更直接相关时使用。

  - **名词**：

    - **事实**：一个布尔条件，它仅依赖于其输入，而不依赖于目标计算机、其环境或计算机的 qubits 的状态。 与断言相比，事实只是对为该事实提供的*值*敏感。 例如：

      *示例：*
      - @"microsoft.quantum.diagnostics.equalityfacti"：表示大约两个整数输入的相等性事实;作为输入提供的整数彼此相等，或不依赖于任何其他程序状态。

    - **选项：** 一个 UDT，其中包含多个可充当函数或操作的 "可选参数" 的命名项。 例如：

      *示例：*
      - @"microsoft.quantum.machinelearning.trainingoptions"UDT 包含用于学习速率、minibatch 大小和用于 ML 培训的其他可配置参数的命名项。

  - **形容词**：

    - ⛔️ **New**：**不应**使用此形容词，因为这样可以避免在许多编程语言（例如 c + +、c #、Java、TypeScript、PowerShell）中将其用法与谓词混淆。

  - **介词：** 在某些情况下，介词可用于进一步消除或阐明函数和操作名称中的名词和动词的角色。 不过，请注意，这种情况并不一致。

    - **如下：** 表示函数的输入和输出表示相同的信息，但输出将该信息表示**为** *X*而不是其原始表示形式。 这对于类型转换函数尤其常见。

      *示例：*
      - `IntAsDouble(2)`指示输入（ `2` ）和输出（ `2.0` ）表示定性的信息相同，但使用不同的 Q \# 数据类型执行此操作。

    - **源：** 为了确保一致性，**不应**使用此介词来指示类型转换函数或任何其他**适合的情况**。

    - ⛔️ **：** **不应**使用此介词，因为这样可以避免在许多编程语言中将其用法与谓词混淆。
