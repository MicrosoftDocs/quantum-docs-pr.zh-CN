---
title: 创建量子随机数生成器
description: 生成一个 Q# 项目，通过创建量子随机数生成器来演示基本的量子概念（例如叠加）。
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: d1ad2c1153814e2fa19a38307b2c668c77eae4e3
ms.sourcegitcommit: b7e205aaa7fa1ca9f0daa163e46154945f4bc965
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2020
ms.locfileid: "77441074"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a>快速入门：在 Q# 中实现量子随机数生成器
以 Q# 编写的量子算法的一个简单示例是量子随机数生成器。 此算法利用量子力学特性来生成随机数。 

## <a name="prerequisites"></a>必备条件

- Microsoft [Quantum 开发工具包](xref:microsoft.quantum.install)。
- [创建 Q# 项目](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a>编写 Q# 运算

### <a name="q-operation-code"></a>Q# 运算代码

1. 将 Operation.qs 文件的内容替换为以下代码：

 :::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-14":::

如 [What is Quantum Computing?](xref:microsoft.quantum.overview.what)（什么是量子计算？）一文所述，量子位是可以处于叠加态的量子信息单元。 度量时，量子位只能是 0 或 1。 但在执行时，量子位的状态表示进行度量时读取值为 0 或 1 的概率。 此概率状态称为叠加。 我们可以根据此概率生成随机数。

在 Q# 操作中，我们引入了 Q# 原生的 `Qubit` 数据类型。 我们只能通过 `using` 语句来分配 `Qubit`。 分配后，量子位始终处于 `Zero` 状态。 

我们可以使用 `H` 操作将 `Qubit` 置于叠加态。 若要度量某个量子位并读取其值，请使用 `M` 内部操作。

将 `Qubit` 置于叠加态并对其进行度量以后，每次调用代码时，我们的结果都会是一个不同值。 

取消分配 `Qubit` 时，必须将其显式设置回 `Zero` 状态，否则模拟器会报告运行时错误。 实现此目的的一种简单方法是调用 `Reset`。

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>使用 Bloch 球将代码可视化

在 Bloch 球中，北极表示经典值 **0**，南极表示经典值 **1**。 任何叠加态都可以用球上的某个点来表示（用箭头表示）。 箭头末端越靠近极点，量子位塌缩成经典值（在度量时分配给该极点）的概率越高。 例如，下面的红色箭头表示的量子位状态在我们度量它时有较高的概率给出值 **0**。

<img src="~/media/qrng-Bloch.png" width="175">

我们可以使用此表示法将代码的功能可视化：

* 首先，我们一开始的量子位初始化为状态 **0**，对其应用 `H` 后会产生一个叠加态，其中获得 **0** 和 **1** 的概率相同。

<img src="~/media/qrng-H.png" width="450">

* 然后，我们度量该量子位并保存输出：

<img src="~/media/qrng-meas.png" width="450">

由于度量结果是完全随机的，我们获得了一个随机位。 我们可以调用此操作多次来创建多个整数。 例如，如果我们调用此操作三次来获取三个随机位，我们就可以生成随机的 3 位数（即 0 到 7 之间的随机数）。

## <a name="creating-a-complete-random-number-generator-using-a-host-program"></a>使用主机程序创建完整的随机数生成器

有了一个生成随机位的 Q# 操作以后，即可使用它通过主机程序构建完整的量子随机数生成器。

 ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[在 Visual Studio Code 或命令行中使用 Python](#tab/tabid-python)
 
 要从 Python 运行你的新 Q# 程序，请将以下代码另存为 `host.py`：
 
:::code language="python" source="~/quantum/samples/getting-started/qrng/host.py" range="11-30":::

 然后便可以从命令行运行 Python 主机程序：
 ```bash
 $ python host.py
 Preparing Q# environment...
 ..The random number generated is 42
 ```
 ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[在 Visual Studio Code 或命令行中使用 C#](#tab/tabid-csharp)
 
 要从 C# 运行你的新 Q# 程序，请修改 `Driver.cs` 以包含以下 C# 代码：
 
 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::
 
 然后便可以从命令行运行 C# 主机程序：
 
 ```bash
 $ dotnet run
 The random number generated is 42
 ```

 ### <a name="c-with-visual-studio-2019"></a>[在 Visual Studio 2019 中使用 C#](#tab/tabid-vs2019)

 在 Visual Studio 中，若要通过 C# 运行新的 Q# 程序，请修改 `Driver.cs`，使之包含以下 C# 代码：

 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::

 然后按 F5，此时系统就会开始执行程序并弹出一个新窗口，其中包含生成的随机数： 

 ```bash
 $ dotnet run
 The random number generated is 42
 ```
 ***
