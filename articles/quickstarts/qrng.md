---
title: 创建量子随机数生成器
description: 生成一个 Q# 项目，通过创建量子随机数生成器来演示基本的量子概念（例如叠加）。
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: a7c077eda3e46430cbe6598cb899adb460451f75
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443913"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a>快速入门：在 Q# 中实现量子随机数生成器
以 Q# 编写的量子算法的一个简单示例是量子随机数生成器。 此算法利用量子力学特性来生成随机数。 

## <a name="prerequisites"></a>先决条件

- Microsoft [Quantum 开发工具包](xref:microsoft.quantum.install)。
- [创建 Q# 项目](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a>编写 Q# 运算

### <a name="q-operation-code"></a>Q# 运算代码

1. 将 Operation.qs 文件的内容替换为以下代码：

    ```qsharp
    namespace Quantum {
        open Microsoft.Quantum.Intrinsic;

        operation QuantumRandomNumberGenerator() : Result {
            using(q = Qubit())  { // Allocate a qubit.
                H(q);             // Put the qubit to superposition. It now has a 50% chance of being 0 or 1.
                let r = M(q);     // Measure the qubit value.
                Reset(q);
                return r;
            }
        }
    }
    ```

如 [What is Quantum Computing?](xref:microsoft.quantum.overview.what)（什么是量子计算？）一文所述，量子位是可以处于叠加态的量子信息单元。 度量时，量子位只能是 0 或 1。 但在执行时，量子位的状态表示进行度量时读取值为 0 或 1 的概率。 此概率状态称为叠加。 我们可以根据此概率生成随机数。

在 Q# 操作中，我们引入了 Q# 原生的 `Qubit` 数据类型。 我们只能通过 `using` 语句来分配 `Qubit`。 分配后，量子位始终处于 `Zero` 状态。 

我们可以使用 `H` 操作将 `Qubit` 置于叠加态。 若要度量某个量子位并读取其值，请使用 `M` 内部操作。

将 `Qubit` 置于叠加态并对其进行度量以后，每次调用代码时，我们的结果都会是一个不同值。 

取消分配 `Qubit` 时，必须将其显式设置回 `Zero` 状态，否则模拟器会报告运行时错误。 实现此目的的一种简单方法是调用 `Reset`。

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>使用 Bloch 球将代码可视化

在 Bloch 球中，北极表示经典值 **0**，南极表示经典值 **1**。 任何叠加态都可以用球上的某个点来表示（用箭头表示）。 箭头末端越靠近极点，量子位塌缩成经典值（在度量时分配给该极点）的概率越高。 例如，下面的红色箭头表示的量子位状态在我们度量它时有较高的概率给出值 **0**。

<img src="./Bloch.svg" width="175">

我们可以使用此表示法将代码的功能可视化：

* 首先，我们一开始的量子位初始化为状态 **0**，对其应用 `H` 后会产生一个叠加态，其中获得 **0** 和 **1** 的概率相同。

<img src="./H.svg" width="450">

* 然后，我们度量该量子位并保存输出：

<img src="./Measurement2.svg" width="450">

由于度量结果是完全随机的，我们获得了一个随机位。 我们可以调用此函数多次来创建多个整数。 例如，如果我们调用此函数三次来获取三个随机位，我们就可以生成随机的 3 位数（即 0 到 7 之间的随机数）。
