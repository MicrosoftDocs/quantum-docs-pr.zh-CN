---
title: 用于量子计算的线性代数
description: 了解需要哪些基础的线性代数概念才能理解量子计算
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.algebra
ms.openlocfilehash: 4750643d16ad8af6240df42c1b93353565561429
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327588"
---
# <a name="linear-algebra-for-quantum-computing"></a>用于量子计算的线性代数

线性代数是量子计算的语言。 虽然你无需了解它即可实现或编写量子程序，但线性代数已被广泛用于描述量子比特的状态、量子操作以及预测量子计算机将执行哪些操作来响应一系列说明。

就像熟悉[量子物理学的基本概念](xref:microsoft.quantum.overview.understanding)可以帮助你了解量子计算一样，了解一些线性代数基础知识也可以帮助你了解量子算法的工作原理。 至少需要熟悉向量和矩阵乘法 。 如需重温这些代数概念的知识，请参阅下面这些介绍基础知识的教程：

- [关于线性代数的 Jupyter 笔记本教程](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra)
- [关于复数算术的 Jupyter 笔记本教程](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic)
- [用于量子计算的线性代数](https://cds.cern.ch/record/1522001/files/978-1-4614-6336-8_BookBackMatter.pdf)
- [线性代数的基础知识](https://www.math.ubc.ca/~carrell/NB.pdf)
- [量子计算入门](https://www.codeproject.com/Articles/5155638/Quantum-Computation-Primer-Part-1#exploring-quantum-superposition)

## <a name="vectors-and-matrices-in-quantum-computing"></a>量子计算中的向量和矩阵

在主题[了解量子计算](xref:microsoft.quantum.overview.understanding)中，你了解到量子比特的状态可以为 1 或 0，或者其中一个或这两者的各种叠加态。 使用线性代数，可将量子比特的状态描述为向量，并由单列矩阵 $\begin{bmatrix} a \\\\  b \end{bmatrix}$ 表示。 它也称为量子状态向量，并且必须满足 $|a|^2 + |b|^2 = 1$ 的要求。  

矩阵的元素表示量子比特坍缩方式的概率，其中 $|a|^2$ 是坍缩为零的概率，而 $|b|^2$ 是坍缩为 1 的概率。 以下矩阵均表示有效的量子状态向量：

$$\begin{bmatrix} 1 \\\\  0 \end{bmatrix}, \begin{bmatrix} 0 \\\\  1 \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{1}{\sqrt{2}} \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{-1}{\sqrt{2}} \end{bmatrix}, \text{ and }\begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{i}{\sqrt{2}} \end{bmatrix}.$$

在[量子计算机和量子模拟器](xref:microsoft.quantum.overview.simulators)中，你还了解到用于修改量子比特状态的量子操作。  量子操作也可以由矩阵表示。 将量子操作应用于量子比特时，代表它们的两个矩阵将相乘，得到的答案表示执行该操作后量子比特的新状态。  

下面是用矩阵乘法表示的两个常见的量子操作。


[`X` 操作](xref:microsoft.quantum.intrinsic.x)由 Pauli 矩阵 $X$ 表示，

$$X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix},$$
    
用于将量子比特的状态从 0 翻转到 1（反之亦然），例如

$$\begin{bmatrix}0 &1\\\\ 1 &0\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \begin{bmatrix} 0 \\\\  1 \end{bmatrix}.$$

[“H”操作](xref:microsoft.quantum.intrinsic.h)由 Hadamard 变换 $H$ 表示，

$$H = \dfrac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix},$$

 并将量子比特置于叠加状态，在这种状态下它甚至有可能以任一方式坍缩，如下所示

$$\frac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix}=\frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  1 \end{bmatrix}=\left(\frac{1}{\sqrt{2}}\right)^2=\frac{1}{2}.$$

代表量子操作的矩阵有一个要求 - 该矩阵必须是酉矩阵。 只要矩阵的逆等于矩阵的共轭转置，就是酉矩阵 。

## <a name="representing-two-qubit-states"></a>表示两个量子比特的状态

在上面的示例中，使用单列矩阵 $\begin{bmatrix} a \\\\  b \end{bmatrix}$ 描述一个量子比特的状态，并通过将两个矩阵相乘来对其应用操作。 但如果量子计算机使用多个量子比特，那么如何描述两个量子比特的组合状态呢？ 

请记住，每个量子比特都是一个向量空间，因此不能只将其相乘。 而是使用张量积，这是一个相关操作，可以从各个向量空间创建新的向量空间，并用 $\otimes$ 符号表示。 例如，计算两个量子比特的状态的张量积 $\begin{bmatrix} a \\\\  b \end{bmatrix}$ and $\begin{bmatrix} c \\\\  d \end{bmatrix}$

$$ \begin{bmatrix} a \\\\  b \end{bmatrix} \otimes \begin{bmatrix} c \\\\  d \end{bmatrix} =\begin{bmatrix} a \begin{bmatrix} c \\\\  d \end{bmatrix} \\\\ b \begin{bmatrix}c \\\\  d \end{bmatrix} \end{bmatrix} = \begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}.
$$

结果是一个四维矩阵，其中每个元素都代表一个概率。 例如，$ac$ 是两个量子比特坍缩为 0 和 0 的概率，$ad$ 是坍缩为 0 和 1 的概率，依此类推。 

就像单个量子比特的状态 $\begin{bmatrix} a \\\\  b \end{bmatrix}$ 必须满足要求 $|a|^2 + |b|^2 = 1$ 才能表示量子状态一样，两个量子比特的状态 $\begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}$ 也必须满足要求 $|ac|^2 + |ad|^2 + |bc|^2+ |bd|^2 = 1$。

## <a name="summary"></a>总结

线性代数是用于描述量子计算和量子物理学的标准语言。 虽然 Microsoft Quantum 开发工具包附带的[库](xref:microsoft.quantum.libraries)将有助于你运行高级量子算法，而无需深入研究基础数学，但了解基础知识将有助于你快速入门，并为你提供坚实的基础。

## <a name="next-steps"></a>后续步骤

[安装 QDK](xref:microsoft.quantum.install)