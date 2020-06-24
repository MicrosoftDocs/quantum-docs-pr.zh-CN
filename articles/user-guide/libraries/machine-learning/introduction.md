---
title: 量子机器学习库
author: alexeib2
ms.author: alexei.bocharov@microsoft.com
ms.date: 11/22/2019
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.introduction
ms.openlocfilehash: 4c42612fee3a58e15368677bb2c77a70c5680f45
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274464"
---
# <a name="introduction-to-quantum-machine-learning"></a>量程机器学习简介

## <a name="framework-and-goals"></a>框架和目标

量程编码和信息处理是传统机器学习量程分类器的一种强大替代方法，特别是在量程寄存器中对数据进行编码，这种方式相对于功能的数量非常简单，系统会将量程牵连用作计算资源，并使用量程度量来进行类推理。
以环路为中心的量程分类器是一个相对简单的量程解决方案，它将数据编码与快速 entangling/disentangling 量程线路结合起来，并使用度量来推断数据示例的类标签。
其目标是确保使用的是传统的主题线路和存储，还可以确保线路参数的混合量子/经典定型，甚至是非常大的功能空间。

## <a name="classifier-architecture"></a>分类器体系结构

分类是一种监督的机器学习任务，其中的目标是推断类标签 $ \{ y_1、y_2、\ldots、y_d \} $ 的某些数据示例。 "定型数据集" 是示例 $ \mathcal{D} = \{ （x，y）} $ 的集合，其中包含已知的预分配标签。 此处 $x $ 是数据样本，并且 $y $ 是其称为 "定型标签" 的已知标签。
类似于传统方法，量程分类包含三个步骤：
- 数据编码
- 分类器状态的准备工作
- 由于度量值的概率，需要多次重复这三个步骤。 度量值可以视为非线性激活的量程。
分类器状态的编码和计算都是通过*量程线路*来完成的。 尽管编码线路通常是数据驱动的和无参数的，但分类器线路包含一组足够的 learnable 参数。 

在建议的解决方案中，分类器线路由单 qubit 旋转和两 qubit 控制旋转组成。 此处的 learnable 参数为旋转角度。 对于量程计算，旋转和控制旋转入口已知为*通用*，这意味着任何单一权重矩阵都可以分解为包含此类入口的足够长的线路。

![多层感知器与以线路为中心的分类器](~/media/DLvsQCC.png)

我们可以将此模型与多层感知器进行比较，以更好地了解基本结构。 在感知器中，预测器 $p （y | x，\theta） $ 由一组权重 $ \theta $ 参数化，后者确定连接非线性激活函数（神经元）的线性函数。 这些参数可以定型来创建模型。 在输出层，我们可以通过使用非线性激活函数（如 softmax）来获取属于某个类的示例的概率。 在以线路为中心的分类器中，预测器由模型线路的 qubit 和两 qubit 控制旋转的旋转角度参数化。 类似地，这些参数可以通过混合量程/经典版本的梯度下降算法进行训练。 若要计算输出，而不是使用非线性激活函数，则可以通过在受控旋转后通过特定 qubit 读取重复度量来获取类的概率。 若要在量程状态中对传统数据进行编码，我们使用可控编码线路来准备状态。

这种体系结构探讨了相对浅的线路，因此必须*快速 entangling*才能捕获所有范围内数据功能之间的所有相关性。 下图显示了最有用的快速 entangling 线路组件示例。 尽管具有此几何的线路仅包含 $3 n + 1 $ 入口，但它计算的单一权重矩阵可确保 $ 2 ^ n $ 功能之间的明显交叉对话。

![快速 entangling 5 qubits 上的量程线路（具有两个循环层）。](~/media/5-qubit-qccc.png)

上述示例中的线路包含6个 qubit 入口 $ （G_1、\ldots、G_5;G_ {16} ） $ 和 10 2-qubits 入口 $ （G_6，\ldots，G_ {15} ） $。 假设每个入口都是使用一个 learnable 参数定义的，我们有16个 learnable 参数，而 5 qubit Hilbert 空间的维度为32。 当 $n $ 为奇数时，可以轻松地将此类线路几何通用化为任何 $n 的 qubit 寄存器，并为 $ 2 ^ n $ 维特征空间产生 $3 n + 1 $ 参数的线路。

## <a name="classifier-training-as-a-supervised-learning-task"></a>作为监督式学习任务的分类器培训

分类器模型的定型涉及到查找其操作参数的最佳值，从而最大程度地提高在定型样本中推断正确训练标签的平均可能性。
在这里，我们只关心两种级别的分类，即 $d = $2 的情况，只有两个标签 $y _1，y_2 $。

> [!NOTE]
> 将方法通用化为任意数量的类的一种原则性方法是将 qubits 替换为 qudits，即，将替换为 $d $ basis 状态，并使用双向度量来 $d $-双向度量。

### <a name="likelihood-as-the-training-goal"></a>作为定型目标的可能性

给定一个 learnable 量程电路 $U （\theta） $ （其中 $ \theta $ 是参数的一个向量，并通过 $M $ 表示最终度量值），正确标签推理的平均可能性是 $ $ \begin{align} \mathcal{L} （\theta） = \frac {1} {| \mathcal{D} |} \left （\ sum_ {（x，y_1） \In\mathcal{D}} P （M = y_1 |U （\theta） x） + \ sum_ {（x，y_2） \in\mathcal{D}} P （M = y_2 |U （\theta） x） \right） \end{align} $ $ where $P （M = y | z） $ 是在量程状态下测量 $y $ $z $ 的概率。
在这里，它后缀了解到，函数 $ \mathcal{L} （\theta） $ 非常平滑，$ \theta $ 和它在任何 $ \ theta_j $ 中的导数可以通过实质上与用于计算可能性函数本身相同的量程协议来计算。 这允许按梯度下降优化 $ \mathcal{L} （\theta） $。

### <a name="classifier-bias-and-training-score"></a>分类器偏差和定型分数

如果 $ \theta $ 中有一些参数的中间（或最后一个）值，我们需要标识一个真实值 $b $ 称为*分类器偏差*来执行推理。 标签推理规则的工作原理如下所示： 
- 当且仅当 $P （M = y_2 | 时，将 $x $ 赋值 $yU （\theta） x） + b > $0.5 （RULE1）（否则 $y _1 $ 为其分配标签）

明确 $b $ 必须是要有意义的间隔 $ （-0.5，+ 0.5） $。

如果为每个 $y RULE1 推断 $x $ $ 的标签，则将定型事例 $ （x，y） \in \mathcal{D} $ 视为 $b*错误分类*。 Misclassifications 的总数是分类器的*定型分数*（给定偏差 $b $）。 *最佳*分类器偏差 $b $ 将定型分数降到最低。 在给定预计算概率估计 $ \{ P （M = y_2 |U （\theta） x） |（x，*） \in\mathcal{D} \} $，通过最多 $ \ log_2 （| \mathcal{D} |），可以通过二进制搜索在间隔 $ （-0.5，+ 0.5） $ 中找到最佳分类符偏移$ 步骤。

### <a name="reference"></a>参考

此信息应该足以开始播放代码。 但是，如果想要了解有关此模型的详细信息，请阅读原始提议： [ *' 以线路为中心的量程分类器 '、Maria Schuld、Alex Bocharov、Krysta Svore 和 Nathan Wiebe*](https://arxiv.org/abs/1804.00633)
