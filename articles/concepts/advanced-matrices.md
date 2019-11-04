---
title: 高级矩阵概念 |Microsoft Docs
description: 高级矩阵概念
author: QuantumWriter
uid: microsoft.quantum.concepts.matrix-advanced
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: f87b3bcd19d2f98fea2a9724a280781a78c4cbb9
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183754"
---
# <a name="advanced-matrix-concepts"></a>高级矩阵概念 #

现在，我们将矩阵操作扩展到[*本征值、本征向量*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors)和[*指数*](https://en.wikipedia.org/wiki/Matrix_exponential)，这构成了我们需要描述和实现量程算法的一组基本工具。

## <a name="eigenvalues-and-eigenvectors"></a>本征值和本征向量 ##

让 $M $ 是正方形矩阵，$v $ 是不是全零向量（即，其所有条目都等于 $0 $）的矢量。

我们说 $v $ 是 $M $ $Mv = cv $[*的某个数字*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors)$c $。 我们说 $c $ 是对应于 eigenvector $v $ 的[*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) 。 通常情况下，矩阵 $M $ 可以将矢量转换为任何其他向量，但 eigenvector 是特殊的，因为它是不变的，但会乘以数字。 请注意，如果 $v $ 是 eigenvalue $c $ 的 eigenvector，则 $av $ 也是具有相同 eigenvalue 的 eigenvector （适用于任何非零 $a $）。

例如，对于恒等矩阵，每个向量 $v $ 是 eigenvalue $1 $ 的 eigenvector。

作为另一个示例，请考虑使用[*对角矩阵*](https://en.wikipedia.org/wiki/Diagonal_matrix)$D $，其对角线上只包含非零条目：

$ $ \begin{bmatrix} d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix}。
$$

矢量

$ $ \begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}、\begin{bmatrix}0 \\\\ 1 \\\\ 0 \ end {bmatrix} 和 \begin{bmatrix}0 \\\\ 0 \\\\1 \ 结束 {bmatrix} $ $

此矩阵的本征向量是本征值 $d _1 $、$d _2 $ 和 $d _3 $）。 如果 $d _1 $、$d _2 $ 和 $d _3 $ 是不同的数字，则这些矢量（及其序列图）是矩阵 $D $ 的唯一本征向量。 通常，对于对角矩阵，可以轻松地将本征值和本征向量读取。 本征值是显示在对角线上的所有数字，其各自的本征向量是单位矢量，其中一项等于 $1 $，剩余项等于 $0 $。

请注意，在上面的示例中，$D $ 构成 $ 3 $ 维向量的基础。 基础是一组矢量，以便可以将任何矢量编写为它们的线性组合。 更明确地 $v _1 $、$v _2 $ 和 $v _3 $ 窗体，如果任何向量 $v $ 可以编写为 $v = a_1 v_1 + a_2 v_2 + a_3 v_3 $ for 某些数字 $a _1 $、$a _2 $ 和 $a _3 $。

回忆一下，Hermitian 矩阵（也称为 adjoint）是一个复杂的正方形矩阵，它等于其自身的共轭复数，而单一矩阵是一个复杂的正方形矩阵，其反转等于其复数共轭。
对于 Hermitian 和单一矩阵，它们实质上是在量程计算中遇到的唯一矩阵，一般结果称为[*spectral 定理*](https://en.wikipedia.org/wiki/Spectral_theorem)，这会断言以下内容：对于任何 Hermitian 或单一矩阵 $M $，都存在单一 $U $ $M = U ^ \dagger D U $ 表示某个对角矩阵 $D $。 而且，$D $ 的对角线条目将是 $M $ 的本征值。

我们已经知道如何计算对角矩阵的本征值和本征向量 $D $。 使用此定理，我们知道，如果 $v $ 是 $D $ 的 eigenvector 为 eigenvalue $c $，即 $Dv = cv $，则 $U ^ \dagger v $ 将是 $M $ 的 eigenvector $c $。 这是因为

$ $M （U ^ \dagger v） = U ^ \dagger D U （U ^ \dagger v） = U ^ \dagger D （U U ^ \dagger） v = U ^ \dagger D v = c U ^ \dagger v. $ $

## <a name="matrix-exponentials"></a>Matrix 指数
[*矩阵指数*](https://en.wikipedia.org/wiki/Matrix_exponential)还可以精确地定义为指数函数。  矩阵的矩阵指数 $A $ 可以表示为

$ $ e ^ A = \boldone + A + \frac{A ^ 2} {2！}+ \frac{A ^ 3} {3！}+ \cdots $ $

这一点很重要，因为对于 Hermitian matrix $B $，其形式为 $e ^ {iB} $ 的单一矩阵。  出于此原因，执行 matrix 指数是量程计算的基本组成部分，因此，此类 Q # 提供了用于描述这些操作的内部例程。
有很多方法可用于计算传统计算机上的矩阵指数，一般为数值逼近，这类指数为充满 with 担风险。  请参阅[*Cleve Moler 和 Charles Van 贷款。"用于计算矩阵指数的可疑方法。"SIAM 评审20.4 （1978）： 801-836*](https://doi.org/10.1137/S00361445024180) ，详细了解涉及的挑战。

了解如何计算矩阵指数的最简单方法是通过该矩阵的本征值和本征向量。  具体而言，以上所述的 spectral 定理说明对于每个 Hermitian 或单一矩阵 $A $ $U $ 和对角矩阵 $D $，$A = U ^ \dagger D U $。  由于 unitarity 的属性，因此，我们已 $A ^ 2 = U ^ \dagger D ^ 2 U $，并且类似于任何 power $p $ $A ^ p = U ^ \dagger D ^ p U $。  如果将此替换为我们获得的运算符指数的运算符定义：

$ $ e ^ A = U ^ \dagger \left （\boldone + D + \frac{D ^ 2} {2！}+ \cdots \right） U = U ^ \dagger \begin{bmatrix}\exp （D_{11}） & 0 & \cdots & 0\\\\ 0 & \exp （D_{22}） & \cdots & 0\\\\ \vdots & \vdots & \ddots & \vdots\\\\ 0& 0 & \cdots & \exp （D_ {NN}） \end{bmatrix} U. $ $

换言之，如果您转换为矩阵的 eigenbasis $A $，则计算矩阵指数等效于计算矩阵本征值的普通指数。  在量程计算中，许多操作都涉及到执行矩阵指数，这种转换为矩阵的 eigenbasis 以简化执行运算符指数的这一技巧经常出现，这是许多量程算法（如）的基础Trotter –本指南稍后介绍的 Suzuki 的量程模拟方法。

另一种有用的属性是，如果 $B $ 既是单一项又是 Hermitian，即 $B = B ^{-1}= B ^ \dagger $，则 $B ^ 2 = \boldone $。 通过将此规则应用于矩阵指数的以上扩展，并将 $ \boldone $ 与 $B $ 词组合在一起，可以看到 $x $ 标识的任何实值

$ $e ^ {iBx} = \boldone \cos （x） + iB\sin （x） $ $


保留. 这一技巧特别有用，因为它允许有关操作矩阵指数的原因，$B 即使 $B $ 既是单一还是 Hermitian 的情况下，也是如此。
