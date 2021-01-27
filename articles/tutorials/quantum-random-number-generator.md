---
title: 创建量子随机数生成器
description: 构建一个 Q# 项目，通过创建一个量程随机数生成器来演示 superposition 等基本的量程概念。
author: bromeg
ms.author: megbrow
ms.date: 10/25/2019
ms.topic: tutorial
uid: microsoft.quantum.quickstarts.qrng
no-loc:
- Q#
- $$v
ms.openlocfilehash: f36db426a8f0479580117cce44a67ad3a053d5de
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856350"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a>教程：使用 Q# 实现量子随机数生成器\#

用写入的量程算法的一个简单示例 Q# 是量程随机数生成器。 此算法利用量子力学特性来生成随机数。

## <a name="prerequisites"></a>先决条件

- Microsoft [Quantum 开发工具包](xref:microsoft.quantum.install)。
- Q#使用[Python 主机程序](xref:microsoft.quantum.install.python)或[c # 宿主程序](xref:microsoft.quantum.install.cs)为[ Q# 应用程序](xref:microsoft.quantum.install.standalone)创建项目。

## <a name="write-a-no-locq-operation"></a>编写 Q# 操作

### <a name="no-locq-operation-code"></a>Q# 操作代码

1. 将 Program.qs 文件的内容替换为以下代码：

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

如[了解量子计算](xref:microsoft.quantum.overview.understanding)一文中所述，量子比特是可以叠加的量子信息单位。 度量时，量子位只能是 0 或 1。 但是，在进行度量之前，qubit 的状态表示读取0或1（含度量值）的概率。 此概率状态称为叠加。 我们可以根据此概率生成随机数。

在我们的 Q# 操作中，我们将 `Qubit` 向提供本机数据类型 Q# 。 我们只能通过 `using` 语句来分配 `Qubit`。 分配后，量子位始终处于 `Zero` 状态。 

我们可以使用 `H` 操作将 `Qubit` 置于叠加态。 若要度量某个量子位并读取其值，请使用 `M` 内部操作。

将 `Qubit` 置于叠加态并对其进行度量以后，每次调用代码时，我们的结果都会是一个不同值。

取消分配 `Qubit` 时，必须将其显式设置回 `Zero` 状态，否则模拟器会报告运行时错误。 实现此目的的一种简单方法是调用 `Reset`。

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>使用 Bloch 球将代码可视化

在 Bloch 球中，北极表示经典值 **0**，南极表示经典值 **1**。 任何叠加态都可以用球上的某个点来表示（用箭头表示）。 箭头末端越靠近极点，量子位塌缩成经典值（在度量时分配给该极点）的概率越高。 例如，下面的红色箭头表示的量子位状态在我们度量它时有较高的概率给出值 **0**。

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

我们可以使用此表示法将代码的功能可视化：

* 首先，我们起初的量子位初始化为状态 **0**，并且我们应用 `H` 以产生一个叠加态，其中获得 **0** 和 **1** 的概率相同。

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">

* 然后，我们度量该量子位并保存输出：

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

由于度量结果是完全随机的，我们获得了一个随机位。 我们可以调用此操作多次来创建多个整数。 例如，如果我们调用此操作三次来获取三个随机位，我们就可以生成随机的 3 位数（即 0 到 7 之间的随机数）。


## <a name="creating-a-complete-random-number-generator"></a>创建完整的随机数生成器

现在，我们有了一个 Q# 生成随机位的操作，可以使用它来生成完整的量程随机数生成器。 可以使用 Q# 应用程序或使用主机程序。



### <a name="no-locq-applications-with-visual-studio-or-visual-studio-code"></a>[Q# 具有 Visual Studio 或 Visual Studio Code 的应用程序](#tab/tabid-qsharp)

若要创建完整的 Q# 应用程序，请在你的程序中添加以下入口点 Q# ： 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

该程序将使用模拟器或资源估计器上的特性标记的操作或函数 `@EntryPoint()` ，具体取决于项目配置和命令行选项。

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-34":::

在 Visual Studio 中，只需按 Ctrl + F5 即可运行脚本。

在 VS Code 中，通过在终端中键入以下内容来首次生成 Program.qs：

```dotnetcli
dotnet build
```

对于后续运行，则无需重新生成它。 若要运行它，请键入以下命令并按 Enter：

```dotnetcli
dotnet run --no-build
```

### <a name="python-with-visual-studio-code-or-the-command-prompt"></a>[Visual Studio Code 或命令提示符下的 Python](#tab/tabid-python)

若要 Q# 从 Python 运行新程序，请将以下代码另存为 `host.py` ：

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

然后，你可以从命令提示符运行 Python 主机程序：

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[C# 与 Visual Studio Code 或 Visual Studio](#tab/tabid-csharp)

若要 Q# 从 c # 运行新程序，请修改 `Driver.cs` 以包含以下 c # 代码：

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

然后，你可以从命令提示符运行 c # 宿主程序 (在 Visual Studio 中，你应按 F5) ：

```bash
$ dotnet run
The random number generated is 42
```

***
