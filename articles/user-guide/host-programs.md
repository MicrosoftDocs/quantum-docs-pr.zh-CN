---
title: 运行程序的方式 Q#
description: 运行程序的不同方法的概述 Q# 。 Q#在 Python 或 .net 语言的命令行中，Jupyter 笔记本和经典主机程序。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8e3fa83700417a4ffaf9e3be91796c9e9513b253
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869726"
---
# <a name="ways-to-run-a-no-locq-program"></a>运行程序的方式 Q#

量程开发工具包的最大优势之一是其跨平台和开发环境的灵活性。
但是，这也意味着，新 Q# 用户可能会发现，在[安装指南](xref:microsoft.quantum.install)中找到的众多选项可能会混淆或淹没。
在此页上，我们将介绍运行程序时所发生的情况 Q# ，并比较用户可执行此操作的不同方式。

主要区别在于， Q# 可以运行：
- 作为独立的应用程序，其中 Q# 是所涉及的唯一语言，直接调用程序。 这两种方法实际上属于此类别：
  - 命令行接口
  - Q#Jupyter 笔记本
- 使用以 Python 或 .NET 语言编写的其他*主机程序* (例如 c # 或 F # ) ，然后调用程序并可以进一步处理返回的结果。

为了更好地了解这些过程及其区别，我们考虑了一个简单 Q# 的程序并对其执行方式进行比较。

## <a name="basic-no-locq-program"></a>基本 Q# 计划

基本的量程计划可能包含：在状态 $ \ket {0} $ 和 $ \ket $ 的 superposition 中准备 qubit {1} ，对其进行度量，并返回结果，这两种状态将随机成为具有相同概率的两种状态之一。
事实上，此过程是[量程随机数生成器](xref:microsoft.quantum.quickstarts.qrng)快速入门的核心。

在中 Q# ，这将由以下代码执行：

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

但是，此代码本身不能由执行 Q# 。
为此，它需要构成操作的主体，然后在直接或通过其他操作---调用时执行该[操作](xref:microsoft.quantum.guide.basics#q-operations-and-functions)。 因此，您可以编写以下形式的操作：
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
您定义了一个操作， `MeasureSuperposition` 该操作不使用输入并返回类型[Result](xref:microsoft.quantum.guide.types)的值。

虽然此页上的示例只包含 Q# *操作*，但我们所讨论的所有概念将同样适用于 Q# *函数*，因此，我们将它们统称为*callables*。 它们的差异在基础上进行了讨论[ Q# ：操作和功能](xref:microsoft.quantum.guide.basics#q-operations-and-functions)，以及有关如何定义它们的详细信息，请参阅[操作和函数](xref:microsoft.quantum.guide.operationsfunctions)。

### <a name="callable-defined-in-a-no-locq-file"></a>在文件中定义的可调用 Q#

可调用只是由调用和运行的 Q# 。
但是，它需要额外添加一些内容才能包含完整 `*.qs` Q# 文件。

所有 Q# 类型和 callables 都 (您定义的类型和) 在命名空间中定义的，这些都是在命名空间中定义的，这些*命名空间*提供了可引用的全名。

例如，在 [`H`](xref:microsoft.quantum.intrinsic.h) [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) 和命名空间中找到和操作 [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) ， [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) ([ Q# 标准库](xref:microsoft.quantum.qsharplibintro)) 的一部分。
因此，它们始终可以通过其*完整*名称调用， `Microsoft.Quantum.Intrinsic.H(<qubit>)` `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` 但始终执行此操作会导致代码非常杂乱。

相反， `open` 语句允许用更简洁的速记来引用 callables，正如以上操作体中所做的那样。
Q#因此，包含我们的操作的完整文件将由定义自己的命名空间，为操作使用的 callables 打开命名空间，然后执行以下操作：

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

> [!NOTE]
> 命名空间也可以在打开时为*别名*，这在两个命名空间中的可调用/类型名称冲突时非常有用。
> 例如，我们可以使用 `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` 上面的，然后 `H` 通过调用 `NamespaceWithH.H(<qubit>)` 。

> [!NOTE]
> 所有这些都是一个例外，即 [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) 始终自动打开的命名空间。
> 因此， [`Length`](xref:microsoft.quantum.core.length) 可以始终直接使用 callables 等。

### <a name="execution-on-target-machines"></a>在目标计算机上执行

现在，程序的常规执行模型 Q# 变得清晰。

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

首先，要执行的特定可调用有权访问在同一命名空间中定义的任何其他 callables 和类型。
它还从任何库访问这些库，但必须通过其全名或使用上述语句来引用这些[ Q# 库](xref:microsoft.quantum.libraries) `open` 。

然后在*[目标计算机](xref:microsoft.quantum.machines)* 上执行可调用本身。
此类目标计算机可以是实际的量程硬件，也可以是多个模拟器作为 QDK 的一部分提供。
对于我们的目的，最有用的目标计算机是[全状态模拟器](xref:microsoft.quantum.machines.full-state-simulator)的实例， `QuantumSimulator` 它计算程序的行为，就好像是在无噪音的量程计算机上执行。

到目前为止，我们已介绍了在执行特定的可调用时将发生的情况 Q# 。
无论 Q# 是在独立应用程序还是主机程序中使用，此常规过程都---相同的，因此 QDK 的灵活性。
因此，调用量子开发工具包的不同方法之间的不同之处在于*如何* Q# 调用可调用的，并以何种方式返回任何结果。
更具体地说，区别在于 
1. 指示 Q# 要执行的可调用的，
2. 如何提供可能的可调用参数，
3. 指定要在其上执行它的目标计算机，以及
4. 返回结果的方式。

首先，我们将讨论如何在 Q# 命令行中使用独立的应用程序完成此操作，然后继续使用 Python 和 c # 宿主程序。
我们保留了 Jupyter 笔记本的独立应用程序 Q# ，因为它与前三个不同，主要功能并不围绕本地 Q# 文件。

> [!NOTE]
> 虽然我们在这些示例中并不说明这种情况，但执行方法之间的一个通用性是，从程序内部打印的任何消息都 Q# (通过 [`Message`](xref:microsoft.quantum.intrinsic.message) 或 [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) ，例如) 通常将始终打印到各自的控制台。

## <a name="no-locq-from-the-command-line"></a>Q#从命令行
开始编写程序的最简单方法之一 Q# 是避免担心单独的文件和另一种语言。
通过使用 Visual Studio Code 或带有 QDK 扩展的 Visual Studio，可以实现一个无缝的工作流，其中 Q# 仅从一个文件中运行 callables Q# 。

为此，我们将通过输入
```dotnetcli
dotnet run
```
在命令行中。
最简单的工作流是：终端的目录位置与 Q# 文件相同，例如，可以 Q# 使用 VS Code 中的集成终端轻松地与文件编辑进行处理。
但是，该[ `dotnet run` 命令](https://docs.microsoft.com/dotnet/core/tools/dotnet-run)接受多个选项，也可以通过仅提供文件的位置，在其他位置运行该程序 `--project <PATH>` Q# 。


### <a name="add-entry-point-to-no-locq-file"></a>向文件添加入口点 Q#

大多数 Q# 文件将包含多个可调用的，因此，我们当然需要让编译器知道在提供命令时要执行*的可*调用项 `dotnet run` 。
这是通过简单更改文件本身来完成的 Q# ： 
    - `@EntryPoint()`在可调用的前面添加一行。

这样，我们的文件就会成为
```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    @EntryPoint()
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

现在， `dotnet run` 从命令行调用 `MeasureSuperposition` 会导致运行，然后将返回值直接打印到终端。
因此，您将看到 `One` 或已 `Zero` 打印。 

请注意，如果下面定义了更多的 callables，则将只 `MeasureSuperposition` 运行。
此外，如果您的可调用内容在其声明之前包含[文档注释](xref:microsoft.quantum.guide.filestructure#documentation-comments)，则不会出现问题 `@EntryPoint()` 。

### <a name="callable-arguments"></a>可调用参数

到目前为止，我们只被视为不需要输入的操作。
假设我们想要执行类似的操作，但在多个 qubits 上---作为参数提供的数量。
此类操作可以编写为
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
其中，返回值是度量结果的数组。
请注意， [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) 和 [`ForEach`](xref:microsoft.quantum.arrays.foreach) 位于 [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) 和 [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) 命名空间中，每个都需要其他 `open` 语句。

如果将属性移 `@EntryPoint()` 到此新操作之前 (请注意，在文件中只能有一个这样的行) ，尝试运行它只会 `dotnet run` 导致错误消息，指出需要其他哪些命令行选项以及如何表达它们。

命令行的常规格式实际上是 `dotnet run [options]` ，并在此处提供了可调用的参数。
在这种情况下， `n` 缺少参数，并显示需要提供选项 `-n <n>` 。 若要 `MeasureSuperpositionArray` 运行 `n=4` qubits，我们将使用

```dotnetcli
dotnet run -n 4
```

生成类似于的输出

```output
[Zero,One,One,One]
```

当然，这种情况下会扩展到多个参数。

> [!NOTE]
> 在中定义的参数名称在编译器中进行 `camelCase` 了轻微更改，作为 Q# 输入接受。 例如，如果 `n` 使用上面的名称， `numQubits` 则此输入将通过 `--num-qubits 4` 而不是在命令行中提供 `-n 4` 。

错误消息还提供可供使用的其他选项，包括如何更改目标计算机。

### <a name="different-target-machines"></a>不同的目标计算机

由于我们的操作的输出在实际 qubits 上是其操作的预期结果，因此，从命令行到默认的目标计算机是完全状态的 quauntum 模拟器，这一点很明显 `QuantumSimulator` 。
但是，我们可以指示 callables 在特定目标计算机上运行， `--simulator` (或简写 `-s`) 。

例如，可以在上运行它 [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) ：

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

然后，打印输出

```output
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

有关这些指标的含义的详细信息，请参阅[Resource 估计器：报告的度量值](xref:microsoft.quantum.machines.resources-estimator#metrics-reported)。

### <a name="command-line-execution-summary"></a>命令行执行摘要
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-no-locq-dotnet-run-options"></a>非 Q# `dotnet run` 选项

如上所述 `--project` ，此[ `dotnet run` 命令](https://docs.microsoft.com/dotnet/core/tools/dotnet-run)还接受与可调用参数无关的选项 Q# 。
如果同时提供这两种选项，则 `dotnet` 必须先提供特定于的选项，然后再提供分隔符 `--` ，然后 Q# 选择特定的选项。
例如，指定将路径与上述操作的数字 qubits 一起执行 `dotnet run --project <PATH> -- -n <n>` 。

## <a name="no-locq-with-host-programs"></a>Q#具有主机程序

使用我们的 Q# 文件，从命令行直接调用操作或函数的替代方法是使用另一种传统语言的*主机程序*。 具体而言，可以使用 Python 或 .NET 语言（如 c # 或 F # (）实现此目的。为了简单起见，我们只会在此处) 详细说明 c #。
若要启用互操作性，还需要进行一些设置，但这些详细信息可在[安装指南](xref:microsoft.quantum.install)中找到。

简而言之，这种情况下，这种情况下包括主机程序文件 (例如， `*.py` 或 `*.cs`) 在与文件相同的位置 Q# 。
它现在是运行的*主机*程序，在执行过程中，它可以 Q# 从文件调用特定的操作和函数 Q# 。
互操作性的核心基于 Q# 编译器使文件内容可供 Q# 主机程序访问，以便可以调用。

使用主机程序的一个主要优点是， Q# 可以使用主机语言进一步处理程序返回的传统数据。
这可能包括一些高级的数据处理 (例如，不能在内部执行 Q#) ，然后 Q# 基于这些结果调用更多操作，也可以像绘制结果那样简单 Q# 。

此处显示了一般方案，并讨论了下面的 Python 和 c # 的具体实现。 有关使用 F # 宿主程序的示例，请参阅[.net 互操作性示例](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)。

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> 用于 `@EntryPoint()` Q# 命令行应用程序的属性不能与主机程序一起使用。
> 如果主机正在调用的文件中存在错误，则会引发错误 Q# 。 

若要使用不同的主机程序，不需要对文件进行任何更改 `*.qs` Q# 。
以下主机程序实现均使用相同的 Q# 文件：

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // contains H
    open Microsoft.Quantum.Measurement;   // MResetZ
    open Microsoft.Quantum.Canon;         // ApplyToEach
    open Microsoft.Quantum.Arrays;        // ForEach

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }

    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {  
            ApplyToEach(H, qubits); 
            return ForEach(MResetZ, qubits);    
        }
    }
}
```

选择与您感兴趣的主机语言对应的选项卡。

### <a name="python"></a>[Python](#tab/tabid-python)
Python 主机计划如下所示：
1. 导入 `qsharp` 模块，该模块将注册模块加载程序以实现 Q# 互操作性。 
    这允许 Q# 命名空间显示为 Python 模块，我们可以将其 "导入" callables "导入" Q# 。
    请注意，从技术上讲，它并不是 Q# 导入的 callables 本身，而是允许调用它们的 Python 存根。
    然后，它们将作为 Python 类的对象，使用方法指定要为执行操作而发送操作的目标计算机。

2. 导入这些 Q# callables，我们将在此示例中直接调用--- `MeasureSuperposition` 和 `MeasureSuperpositionArray` 。
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    `qsharp`导入模块后，还可以直接从 Q# 库命名空间导入 callables。

3. 在其他任何 Python 代码中，现在可以在特定目标计算机上调用这些 callables，并将其返回值分配给变量 (如果它们返回值) 以便进一步使用。

#### <a name="specifying-target-machines"></a>指定目标计算机
调用要在特定目标计算机上运行的操作是通过导入的对象上的不同 Python 方法完成的。
例如， `.simulate(<args>)` 使用 `QuantumSimulator` 运行操作，而 `.estimate_resources(<args>)` 在上执行此操作 `ResourcesEstimator` 。

#### <a name="passing-inputs-to-q"></a>向 Q 传递输入\#
Q#应以关键字参数的形式提供可调用的参数，其中，关键字是可调用定义中的参数名称 Q# 。
这是 `MeasureSuperpositionArray.simulate(n=4)` 有效的，但 `MeasureSuperpositionArray.simulate(4)` 会引发错误。

因此，Python 主机程序 

```python
import qsharp
from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray

single_qubit_result = MeasureSuperposition.simulate()
single_qubit_resources = MeasureSuperposition.estimate_resources()

multi_qubit_result = MeasureSuperpositionArray.simulate(n=4)
multi_qubit_resources = MeasureSuperpositionArray.estimate_resources(n=4)

print('Single qubit:\n' + str(single_qubit_result))
print(single_qubit_resources)

print('\nMultiple qubits:\n' + str(multi_qubit_result))
print(multi_qubit_resources)
```

生成如下所示的输出：

```python
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

### <a name="c"></a>[C#](#tab/tabid-csharp)

C # 主机程序具有多个组件，并与 QDK 的某些组件（如模拟器）非常紧密，这些组件是在 c # 的基础上构建的。

Q#编译器在此处通过 Q# 在文件的命名空间中生成一个等效的 c # 命名空间来工作 Q# 。
它针对其中定义的每个 callables 或类型进一步生成一个等效的命名 c # 类 Q# 。

首先，我们将在主机程序中使用的类与语句一起使用 `using` ，这些语句大致类似于 `open` 文件中的语句 Q# ：

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (e.g. QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

接下来，我们声明 c # 命名空间，一些其他位和部分 (查看以下完整的代码块) ，然后需要 (如计算 callables) 的参数。 Q#
在本例中，后者不是必需的，但在[.net 互操作性示例](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)中可以找到此类用法的示例。

#### <a name="target-machines"></a>目标计算机

返回到 Q# ，我们必须创建将对其执行操作的任何目标计算机的实例。

```csharp
            using var sim = new QuantumSimulator();
```

使用其他目标计算机非常简单，只需要实例化不同的计算机，但执行此操作和处理返回的方式可能略有不同。
为简洁起见，我们现在坚持到 [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) ，并包括 [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [以下](#including-the-resources-estimator)。

每个从操作生成的 c # 类 Q# 都有一个 `Run` 方法，第一个参数必须是目标计算机实例。
因此，若要 `MeasureSuperposition` 在上运行 `QuantumSimulator` ，我们将使用 `MeasureSuperposition.Run(sim)` 。
然后，可以将返回的结果分配给 c # 中的变量：

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> `Run`此方法是异步执行的，因为这将是真实量程硬件的情况，因此， `await` 关键字会阻止进一步执行，直到任务完成。

如果可 Q# 调用的不包含任何返回 (即) 返回类型 `Unit` ，则仍可通过相同的方式执行该操作，而无需将其分配给变量。
在这种情况下，整行只包含 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a>自变量

可调用的任何参数 Q# 只是作为附加参数传递叫目标计算机。
因此， `MeasureSuperpositionArray` qubits 上的结果 `n=4` 将通过 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

因此，完整的 c # 宿主程序可能类似于

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine($"Multiple qubit result: {multiQubitResult}");
        }
    }
}
```

在 c # 文件的位置，通过输入，可以从命令行运行主机程序
```dotnetcli
dotnet run
```
在这种情况下，你将看到写入到控制台的输出，类似于 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> 由于编译器与命名空间的互操作性，因此，我们可以 Q# 在不使用语句的情况下让 callables 可用 `using NamespaceName;` ，并且只需将 c # 命名空间标题与它进行匹配即可。
> 也就是说，将替换 `namespace host` 为 `namespace NamespaceName` 。

#### <a name="including-the-resources-estimator"></a>包括资源估计器

[`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator)需要略有不同的实现来检索输出。

首先，不会将它们实例化为带有语句的变量 `using` (与 `QuantumSimulator`) 一样，我们通过

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

请注意， Q# 我们已为每个操作实例化一个目标模拟器，而不是由多个操作使用单个目标模拟器。 这是因为在用作目标计算机时，对象本身会被修改，然后可以使用类方法在以后检索这些对象的结果 `.ToTSV()` 。

若要在资源估算上运行操作，请使用

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
然后，将结果作为制表符分隔的值（ (TSV) 与和一起提取 `estimatorSingleQ.ToTSV()` `estimatorMultiQ.ToTSV()` 。

因此，使用和的完整 c # 宿主程序 `QuantumSimulator` `ResourcesEstimator` 可以采用以下形式：

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine("Single qubit resources:");
            Console.WriteLine(estimatorSingleQ.ToTSV());

            Console.WriteLine($"\nMultiple qubit result: {multiQubitResult}");
            Console.WriteLine("Multiple qubit resources:");
            Console.WriteLine(estimatorMultiQ.ToTSV());
        }
    }
}
```


这会生成类似于的输出

```output
Single qubit result: One
Single qubit resources:
Metric          Sum
CNOT            0
QubitClifford   1
R               0
Measure         1
T               0
Depth           0
Width           1
BorrowedWidth   0

Multiple qubit result: [One,One,One,Zero]
Multiple qubit resources:
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

***

## <a name="no-locq-jupyter-notebooks"></a>Q#Jupyter 笔记本
Q#Jupyter 笔记本利用 I Q# 内核，使你能够在单个笔记本中定义、编译和运行 Q# callables，---所有说明、注释和其他内容。
这意味着，虽然可以导入和使用文件的内容，但 `*.qs` Q# 它们在执行模型中不是必需的。

在这里，我们将详细介绍如何运行 Q# 上面定义的操作，但 Q# 在[简介 Q# 和 Jupyter 笔记本](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)中提供了有关使用 Jupyter 笔记本的更广泛的介绍。

### <a name="defining-operations"></a>定义操作

在 Q# Jupyter Notebook 中，你可以 Q# 像在文件的命名空间内一样输入代码 Q# 。

因此，可以从具有相应命名空间的语句的[ Q# 标准库](xref:microsoft.quantum.qsharplibintro)中启用对 callables 的访问 `open` 。
使用此类语句运行单元时，这些命名空间中的定义在整个工作区中都可用。

> [!NOTE]
> Callables 和[Microsoft.Quantum.Intrinsic](xref:microsoft.quantum.intrinsic) [Canon](xref:microsoft.quantum.canon) (（例如 [`H`](xref:microsoft.quantum.intrinsic.h) [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) ）和) 自动可用于 Jupyter 笔记本的单元中定义的操作。 Q#
> 不过，对于从外部源文件引入的代码)  (，这种情况并不是如此 Q# 。 [ Q# ](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb) 
> 

同样，定义操作只需编写 Q# 代码并运行单元。

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="600">

然后，输出会列出这些操作，随后可以从未来的单元格中调用这些操作。

### <a name="target-machines"></a>目标计算机

通过[I Q# 幻命令](xref:microsoft.quantum.guide.quickref.iqsharp)提供在特定目标计算机上运行操作的功能。
例如， `%simulate` 利用 `QuantumSimulator` ，并 `%estimate` 使用 `ResourcesEstimator` ：

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Simulate and estimate resources Jupyter cell" width="500">

### <a name="passing-inputs-to-functions-and-operations"></a>将输入传递到函数和操作

目前，执行幻命令仅可用于不采用任何参数的操作。 因此，若要运行 `MeasureSuperpositionArray` ，我们需要定义一个 "包装" 操作，该操作随后使用参数调用操作：

<img src="../media/hostprograms_jupyter_wrapper_def_sim_crop.png" alt="Wrapper function and simulate Jupyter cell" width="550">

当然，此操作可以与 `%estimate` 和其他执行命令一起使用。
