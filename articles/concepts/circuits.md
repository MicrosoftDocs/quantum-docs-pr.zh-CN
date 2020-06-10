---
title: 量子线路
description: 了解如何以视觉方式表示简单和复杂的量程操作和量子线路关系图。
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
ms.openlocfilehash: 745f0570bf62c5d98c2896cdc893ec385abd7115
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630409"
---
# <a name="quantum-circuits"></a>量程线路
请考虑一下单一转换 $ \text { cnot-contains} _ {01 } （H \otimes 1） $。
此入口序列对量程计算至关重要，因为它创建最大化放大二 qubit 状态：

$ $ \mathrm{CNOT}_{01 } （H \otimes 1） \ket{00 } = \frac{1 } {\sqrt{2 } } \left （\ket{00 } + \ket{11 } \right），$ $

具有这种或更大复杂性的操作在量程算法和量程错误更正中无处不在，因此它应该会很好地降低，其中有一种简单的方法可以将其可视化称为 "*量程*"。
准备此最大化放大量程状态的线路关系图为：

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![最大化放大双 qubit 状态的布线图](~/media/1.svg)

## <a name="quantum-circuit-diagram-conventions"></a>量程线路约定
当你了解表示量子线路的约定后，这种适用于量程操作的视觉语言比写下其等效矩阵更容易理解。
我们将在下面查看这些约定。

在电路图中，每个实线都描述了 qubit 或更常见的 qubit 寄存器。
按照约定，顶行是 qubit register $0 $ ，余数按顺序标记。 上面的示例线路描述为在两个 qubits （或由一个 qubit 组成的等效两个寄存器）上操作。
在一个或多个 qubit 寄存器上操作的入口表示为一个框。
例如，符号

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![对 qubit 寄存器执行的 Hadamard 操作的符号](~/media/2.svg)

是对 qubit 寄存器进行的[Hadamard](xref:microsoft.quantum.intrinsic.h)操作。

量程入口按时间顺序排列，并将最左侧的入口排列为第一个应用到 qubits 的入口。
换而言之，如果将电缆画为包含量程状态，则电缆会从左到右从图中的每个入口开始显示量程状态。
这就是说 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![从左向右应用的量程入口示意图](~/media/3.svg)

是单一矩阵 $CBA $ 。
矩阵相乘服从相反的约定：首先应用最右侧的矩阵。 但在量程电路关系图中，首先应用最左侧的入口。
这种差异可能会导致混淆，因此请务必注意线性代数表示法和量子电路关系图之间的明显差异。

## <a name="inputs-and-outputs-of-quantum-circuits"></a>量程线路的输入和输出
前面给出的所有示例都与从量子入口传出的线路数（qubits）输入完全相同。
这种情况可能会在一开始就显得合理，一般情况下，量程线路可能比输入更多或更少的输出。
但是，这是不可能的，因为所有的量程操作（节省度量值）都是单一的，因此是可逆的。
如果它们没有与输入相同的输出数，则它们不是可逆的，因而不是一个冲突。
出于此原因，在线路图中绘制的任何一个框必须与输入它的线路完全相同。

多 qubit 线路关系图遵循类似的约定来 qubit。
作为示例，我们可以定义 qubit 单一操作 $B $ 为 $ （H S \otimes X） $，并表示与

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Qubit 单一操作的线路关系图](~/media/4.svg)

我们还可以查看 $B $ ，使其在单个 qubit 注册上执行操作，而不 2 1 是 qubit 寄存器上的操作，具体取决于使用该线路的上下文。 此类抽象线路的最有用的属性可能是，它们允许在较高级别对复杂的量程算法进行描述，而不必将它们编译为基本入口。
这意味着，你可以获取有关大型量程算法的数据流的直觉，而无需了解算法中每个子例程的工作方式的所有详细信息。

## <a name="controlled-gates"></a>受控入口
内置于 qubit 量程线路关系图的另一种构造是控件。
量程单向控制入口的操作（表示 $ \Lambda （G） $，其中单个 qubit 的值控制 $G 的应用 $ ），可以通过查看以下示例：产品状态输入 $ \Lambda （g）（\alpha \ket{0 } + \beta \ket{1 } ） \ket { \psi } = \alpha \ket{0 } \ket { \psi } + \beta \ket{1 } G \ket { \psi } $。
也就是说， $ $ 当且仅当控件 qubit 采用值 $1 时，受控的入口才会将 $G 应用到包含 $ \psi 的寄存器 $ 。
通常，我们会将这些受控操作介绍为

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![单个受控入口的回路图](~/media/5.svg)

此时，黑色圆圈表示控制门的量程位，垂直线表示在控件 qubit 采用值 $1 时应用的单一 $ 。
对于 $G = X $ 和 $G = Z 的特殊情况， $ 我们引入了以下表示法，用于描述控制的入口版本（请注意，受控的 X 门是[$CNOT $ 门](xref:microsoft.quantum.intrinsic.cnot)）：

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![受控入口的特殊情况的电路图](~/media/6.svg)

Q # 提供自动生成控制版本的操作的方法，此操作使程序员不必为这些操作编写代码。 下面显示了一个示例：

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a>度量运算符
在 "电路图" 中显示的剩余操作是度量值。
度量采用 qubit 注册，对其进行度量，并将结果输出为传统信息。
度量运算由计量符号表示，并始终将 qubit 寄存器（由实线表示）作为输入，并输出古典信息（用双线表示）。
具体而言，此类 subcircuit 如下所示：

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![表示度量操作的符号](~/media/7.svg)

Q # 为此目的实现了[度量运算符](xref:microsoft.quantum.intrinsic.measure)。
有关详细信息，请参阅[有关度量值的部分](xref:microsoft.quantum.libraries.standard.prelude#measurements)。

同样，subcircuit

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![表示受控操作的线路关系图](~/media/8.svg)

提供一个经典控制的入口，其中 $G $ 适用于经典控件位上的值为 $1 $ 。

## <a name="teleportation-circuit-diagram"></a>Teleportation 线路图
量程 teleportation 可能是用于阐释这些组件的最佳量程算法。
你可以使用相应的[量程 Kata](xref:microsoft.quantum.overview.katas)量子 teleportation 来了解如何使用牵连和度量在量程计算机（甚至是在量程网络中的远程量子计算机之间）移动数据。
有趣的是，实际上可以将给定 qubit 中的值表示为从一个 qubit 移动到另一个，而无需了解 qubit 的值！
这是协议根据量程机制的法律工作所必需的。
下面给出了量子 teleportation 线路;我们还提供了一条带批注的线路，用于说明如何读取量程线路。

<!--- ![](.\media\tp2.svg){ width=50% } --->
![量程 teleportation 线路](~/media/tp2.svg)
