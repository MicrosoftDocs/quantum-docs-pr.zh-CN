---
title: 量子机器学习库
description: 了解如何在量程系统上使用机器学习
author: alexeib2
ms.author: alexeib
ms.date: 11/22/2019
ms.topic: conceptual
uid: microsoft.quantum.libraries.machine-learning.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: e2f4a4a63eef40474856426b3b29652b5d3053b2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854030"
---
# <a name="introduction-to-quantum-machine-learning"></a>量程机器学习简介

## <a name="framework-and-goals"></a>框架和目标

量程编码和信息处理是传统机器学习量程分类器的一种强大替代方法。 具体而言，它使我们能够对量程寄存器中的数据进行编码，这种方式相对于功能的数量非常简单，并将量程牵连用作计算资源并采用类推理的量程度量。
以环路为中心的量程分类器是一个相对简单的量程解决方案，它将数据编码与快速 entangling/disentangling 量程线路结合起来，并使用度量来推断数据示例的类标签。
其目标是确保使用的是传统的主题线路和存储，还可以确保线路参数的混合量子/经典定型，甚至是非常大的功能空间。

## <a name="classifier-architecture"></a>分类器体系结构

分类是一种监督的机器学习任务，其中的目标是推断类标签 $ \{ y_1、y_2、\ldots、y_d \} $ 的某些数据示例。 "定型数据集" 是示例 $ \mathcal{D} = \{ (x，y) } $ 的集合，其中包含已知的预分配标签。 此处 $x $ 是数据样本，并且 $y $ 是其称为 "定型标签" 的已知标签。
类似于传统方法，量程分类包含三个步骤：
- 数据编码
- 分类器状态的准备工作
- 由于度量值的概率，需要多次重复这三个步骤。 分类器状态的编码和计算都是通过 *量程线路* 来完成的。 尽管编码线路通常是数据驱动的和无参数的，但分类器线路包含一组足够的 learnable 参数。 

在建议的解决方案中，分类器线路由单 qubit 旋转和两 qubit 控制旋转组成。 此处的 learnable 参数为旋转角度。 对于量程计算，旋转和控制旋转入口已知为 *通用* ，这意味着任何单一权重矩阵都可以分解为包含此类入口的足够长的线路。

在建议的版本中，只支持后跟单频率估算的一条线路。
因此，解决方案是具有低度多项式内核的支持向量计算机的量程模拟。

![多层感知器与以线路为中心的分类器](~/media/DLvsQCC.png)

可以将简单的量程分类器设计与传统的支持向量计算机进行比较 (SVM) 解决方案。 使用最佳内核窗体 $ \sum \ alpha_j k (x_j，x) $，其中 $k $ 是特定内核函数，SVM 的数据 $x 示例的推理。

与此相反，量程分类器使用预测器 $p (y │ x，U ( \theta) # B3 = 〈 U ( \theta) x | M | U ( \theta) x 〉 $，这在精神中类似，但在技术上非常不同。 因此，在使用简单的幅度编码时，$p (y │ x，U ( \theta) # B3 $ 是 $x $ 的 amplitudes 中的二次窗体，但不再单独了解此窗体的系数;它们改为从线路的矩阵元素聚合 $U ( \theta) $，通常，learnable 参数 $ \theta $ 比向量 $x $ 的维度少很多。 通过在 $l $ $x $ 个副本上使用量程产品编码，可以将原始功能中 $p (y │ x、U ( \theta) # B3 $ 的多项式度提高到 $ 2 ^ l $。

这种体系结构探讨了相对浅的线路，因此必须 *快速 entangling* 才能捕获所有范围内数据功能之间的所有相关性。 下图显示了最有用的快速 entangling 线路组件示例。 尽管具有此几何的线路仅包含 $3 n + 1 $ 入口，但它计算的单一权重矩阵可确保 $ 2 ^ n $ 功能之间的明显交叉对话。

![快速 entangling 5 qubits (上的量子线路，) 两个循环层。](~/media/5-qubit-qccc.png)

上述示例中的线路包含6个 qubit 入口 $ (G_1，\ldots，G_5;G_ {16}) $ 和 10 2-qubits 入口 $ (G_6，\ldots，G_ {15}) $。 假设每个入口都是使用一个 learnable 参数定义的，我们有16个 learnable 参数，而 5 qubit Hilbert 空间的维度为32。 当 $n $ 为奇数时，可以轻松地将此类线路几何通用化为任何 $n 的 qubit 寄存器，并为 $ 2 ^ n $ 维特征空间产生 $3 n + 1 $ 参数的线路。

## <a name="classifier-training-as-a-supervised-learning-task"></a>作为监督式学习任务的分类器培训

分类器模型的定型涉及到查找其操作参数的最佳值，从而最大程度地提高在定型样本中推断正确训练标签的平均可能性。
在这里，我们只关心两种级别的分类，即 $d = $2 的情况，只有两个标签 $y _1，y_2 $。

> [!NOTE]
> 将方法通用化为任意数量的类的一种原则性方法是将 qubits 替换为 qudits，即，将替换为 $d $ basis 状态，并使用双向度量来 $d $-双向度量。

### <a name="likelihood-as-the-training-goal"></a>作为定型目标的可能性

给定一个 learnable 量程线路 $U ( \theta) $，其中 $ \theta $ 是参数的一个向量，并通过 $M $ 来表示最终度量值，正确标签推理的平均可能性是 $ $ \begin{align} \mathcal{L} ( \theta) = \frac {1} {| \mathcal{D} |} \left ( \ sum_ { (x，y_1) \in\mathcal{d}} (Y_1 M = |U ( \theta) x) + \ sum_ { (x，y_2) \in\mathcal{D}} P (M = y_2 |U ( \theta) x) \right) \end{align} $ $，其中 $P (M = y | z) $ 是在量程状态 $y $ 的度量的概率。
在这里，它后缀了解到 $ \theta $) $ \theta $ 的 ( 可能性，并且它的 theta_j 派生方式实质上是与用于计算可能性函数本身相同的量程协议。 这允许按梯度下降量优化 $ \mathcal{L} ( \theta) $。

### <a name="classifier-bias-and-training-score"></a>分类器偏差和定型分数

如果 $ \theta $ 中的参数有一些中间 (或最终) 值，则需要确定单个实数值 $b $ 称为 *分类器偏差* 来执行推理。 标签推理规则的工作原理如下所示： 
- 当且仅当 $P (M = y_2 时，为 _2 $ 赋值 $y $x $ 的示例U ( \theta) x) + b > $0.5 ()  ($y) 

明确 $b $ 必须在时间间隔 $ (-0.5，+ 0.5) $ 才能有意义。

如果根据 RULE1 为 $x $ $b 推断的标签与 $y $) ，则将定型事例 $ (x、y \in \mathcal{D} $ 视为 *错误分类* 。 Misclassifications 的总数是分类器的 *定型分数* （给定偏差 $b $）。 *最佳* 分类器偏差 $b $ 将定型分数降到最低。 在给定预计算概率估计 $ \{ P (M = y_2 的情况下，很容易就会看到。U ( \theta) x) | (x，* ) \in\mathcal{D} \} $，通过最多 $ \ log_2 (| \mathcal{D} |) $ 个步骤，可以通过二进制搜索以 "间隔 $ (-0.5，+ 0.5) $" 来找到最佳分类符偏移量。

### <a name="reference"></a>参考

此信息应该足以开始播放代码。 但是，如果想要了解有关此模型的详细信息，请阅读原始提议： [ *' 以线路为中心的量程分类器 '、Maria Schuld、Alex Bocharov、Krysta Svore 和 Nathan Wiebe*](https://arxiv.org/abs/1804.00633)

除了接下来的步骤中所示的代码示例外，还可以在[本教程](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/QuantumClassification)中开始探索量程分类 
