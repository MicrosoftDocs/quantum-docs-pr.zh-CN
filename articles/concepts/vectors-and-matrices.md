---
title: 向量和矩阵 |Microsoft Docs
description: 向量和矩阵
author: QuantumWriter
uid: microsoft.quantum.concepts.vectors
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 58c96f9cda22b712e1a408e5566e0a8ee987bd6e
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183737"
---
# <a name="vectors-and-matrices"></a>向量和矩阵

熟悉矢量和矩阵对于了解量程计算至关重要。 我们提供了下面的简要介绍，并建议读者阅读有关线性代数（如*Strang，G （1993））的标准引用。线性代数简介（卷3）。Wellesley、MA： Wellesley-剑桥按下*或联机引用，如[线性代数](http://joshua.smcvt.edu/linearalgebra/)。

列向量（或仅[*矢量*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))） $n $ $v $ 是 $n $ 复数 $ （v_1，v_2，\ldots，v_n） $ 排列为一列的集合：

$ $v = \begin{bmatrix} v_1\\\\ v_2\\\\ \vdots\\\\ v_n \end{bmatrix} $ $

向量 $v $ 的标准定义为 $ \sqrt{\sum\_i | v\_i | ^ 2} $。 如果向量的标准为 $1 $，则认为向量是单位规范（或者，也称为[*单位矢量*](https://en.wikipedia.org/wiki/Unit_vector)）。 向量 $v $ 的[*adjoint*](https://en.wikipedia.org/wiki/Adjoint_matrix)表示 $v ^ \dagger $，定义为以下行向量，其中 $\*$ 表示复数共轭，

$ $ \begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix} ^ \dagger = \begin{bmatrix}v_1 ^ * & \cdots & v_n ^ * \end{bmatrix} $ $

将两个矢量相乘的最常见方法是通过[*内部产品*](https://en.wikipedia.org/wiki/Inner_product_space)（也称为点积）。  内部产品提供了一个向量的投影到另一个向量，这在描述如何将一个向量表达为其他更简单的向量的总和方面非常有用。  $U $ 和 $v $ 之间的内部积（表示 $ \left\langle u，v\right\rangle $）定义为

$ $ \langle u，v\rangle = u ^ \dagger v = u\_1 ^ {\*} v_1 + \cdots + u\_n ^ {\*} v\_n。
$$

此表示法还允许以 $ \sqrt{\langle v，v\rangle} $ 形式写入矢量 $v $ 的标准。

我们可以将一个向量与一个数字 $c $ 相乘，以形成一个新向量，其项与 $c $ 相乘。 我们还可以添加两个向量 $u $ 和 $v $，以形成新的向量，其条目是 $u $ 和 $v $ 的条目之和。 这些操作如下所示：

$ $ \mathrm{If} ~ u = \begin{bmatrix} u_1\\\\ u_2\\\\ \vdots\\\\ u_n \end{bmatrix} ~ \mathrm{and} ~ v = \begin{bmatrix} v_1\\\\ v_2\\\\ \vdots\\\\ v_n \end{bmatrix}，~ \mathrm{then} ~ au + bv = \begin{bmatrix} au_1 + bv_1\\\\ au_2 + bv_2\\\\ \vdots\\\\ au_n + bv_n \end{bmatrix}。
$$

大小为的[*矩阵*](https://en.wikipedia.org/wiki/Matrix_(mathematics))$m \times n $ 是按 $m $ rows 和 $n $ 列排列的 $mn $ 复数的集合，如下所示：

$ $M = \begin{bmatrix} M_{11} ~ ~ M_{12} ~ ~ \cdots ~ ~ M_ {1n}\\\\ M_{21} ~{22} M_\\~ \\ \cdots\\\\ M_ {m1} ~ ~ \ddots {m2} ~ ~ M_ ~ ~ M_ {\cdots}\\\\ \end{bmatrix}. $ $

请注意，维度 $n $ 的矢量只是大小 $n \times $1 的矩阵。 与矢量一样，我们可以将矩阵与数字 $c $ 相乘，以获取一个新矩阵，其中每个条目都与 $c $ 相乘，我们可以添加两个相同大小的矩阵，以生成一个新矩阵，该矩阵的条目是两个矩阵各自条目的总和。 

## <a name="matrix-multiplication-and-tensor-products"></a>Matrix 乘法 and Tensor Products

还可以将两个矩阵 $M $ of dimension $m \times n $ 和 $N $ of dimension $n \times p $，以获取一个新的矩阵 $P $ of dimension $m \times p $，如下所示：

\begin{align} & \begin{bmatrix} M_{11} ~ ~ M_{12} ~ ~ \cdots ~ ~ M_ {1n}\\\\ M_{21} ~ M_{22} ~ ~ \cdots ~ ~ M_ {2n}\\\\ \ddots\\\\ M_ {m1} ~ ~ M_ {\cdots} M_ \begin {bmatrix} N_{11} ~ ~ N_{12} ~ ~ \cdots ~ ~ N_ {1 p}\\\\ N_{21} ~{22} N_\\~ ~ \cdots ~ N_ {2 p} \\\\\ddots \\ N_ {n1} ~ ~ N_ {\cdots} N_ = \end{bmatrix} \Begin{bmatrix}{11} ~ ~ P_{12} ~ ~ \cdots ~ P_ {1 p}\\\\ P_{21} ~{22} P_\\~ ~ \cdots ~ ~ P_ {2 p} \\\\\ddots \\ P_ {m1} ~ ~ P_ {\cdots} P_ \end{bmatrix}

其中 $P $ 的条目 $P _ {ik} = \sum_j M_ {ij} N_ {jk} $。 例如，$P _{11}$ 的条目是 $M $ 的第一行的内部积，其中第一列 $N $。 请注意，由于矢量只是矩阵的一种特殊情况，因此此定义延伸到矩阵向量乘法。 

我们考虑的所有矩阵均为方形矩阵，其中的行数和列数相等，或向量仅对应于 $1 $ 列。 一个特殊的正方形矩阵是[*标识矩阵*](https://en.wikipedia.org/wiki/Identity_matrix)，表示 $ \boldone $，其所有对角线元素都等于 $1 $，其余元素等于 $0 $：

$ $ \boldone = \begin{bmatrix} 1 ~ ~ 0 ~ ~ \cdots ~ ~ 0\\\\ 0 ~ ~ 1 ~ ~ \cdots ~ ~ 0\\\\ ~ ~ \ddots\\\\ 0 ~ ~ 0 ~ \cdots ~ ~ 1 \end{bmatrix}. $ $

对于正方形矩阵 $A $，我们说，如果 $AB = BA = \boldone $，则 $B $ 是其[*逆*](https://en.wikipedia.org/wiki/Invertible_matrix)矩阵。 矩阵的逆矩阵不需要存在，但如果它存在，则它是唯一的，并将其表示 $A ^{-1}$。 

对于任何矩阵 $M $，$M $ 的 adjoint 或共轭转置为一个矩阵 $N $，$N _ {ij} = M_ {ji} ^\*$。 $M $ 的 adjoint 通常表示 $M ^ \dagger $。 我们说，如果 $UU ^ \dagger = U ^ \dagger U = \boldone $ 或等效 $U ^{-1} = U ^ \dagger $，矩阵 $U $ 是[*单一*](https://en.wikipedia.org/wiki/Unitary_matrix)的。  单一矩阵的最重要的属性可能是它们保留向量的标准。  出现这种情况的原因是 

$ $ \langle v，v \rangle = v ^ \dagger v = v ^ \dagger U ^{-1} U v = v ^ \dagger U ^ \dagger U v = \langle U v，U v\rangle. $ $  

如果 $M = M ^ \dagger $，矩阵 $M $ 称为[*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) 。

最后，两个矩阵的[*tensor 产品*](https://en.wikipedia.org/wiki/Tensor_product)（或 Kronecker 产品） $M $ of size $m \times n $ 和 $N $ size $p \times q $ 是一个较大的矩阵 $P = M\otimes n $ of size $mp \times nq $，并按如下所示从 $M $ 和 $N $ 获取：

\begin{align} M \otimes N & = \begin{bmatrix} M_{11} ~ ~ \cdots ~ ~ M_ {1n} \\\\ \ddots\\\\ M_ {m1} ~ ~ \cdots ~ M_ {mn} \end{bmatrix} \otimes \begin{bmatrix} N_{11}\\\cdots \\t_8_ \\ N_ {p1} ~ ~ \cdots ~ ~ N_ {pq} \end{bmatrix}\\\\ & = \begin{bmatrix} M_{11} \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1q}\\\\ \ddots\\\\ N_ {p1} ~ ~ \cdots ~ ~ N_ {pq} \end{bmatrix}~ ~ \cdots ~ ~ M_ {1n} \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1q}\\\\ \ddots\\\\ N_ {p1} ~ ~ \cdots ~ N_ {pq} \end{bmatrix}\\\\ \ddots\\\\ M_ {m1} \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1q}\\\\ \ddots\\\\ N_ {p1} ~ ~ \cdots ~ ~ N_ {pq} \end{bmatrix} ~ ~ \cdots ~ ~ M_ {mn} \begin{bmatrix} N_{11} ~\\\cdots \\\\N_ {p1} ~ 1q ~ ~ \Ddots {N_} \cdots{bmatrix} \end{bmatrix}.
\end{align}

下面的示例对此进行了更好的演示：

$ $ \begin{bmatrix} a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} = \begin{bmatrix} a \begin{bmatrix} c \\\\ \\\\ e \end{bmatrix} \\\\[1.5 em] b \begin{bmatrix} c \\\\ d \\\\ e\end {bmatrix} \end{bmatrix} = \begin{bmatrix} a c \\\\ \\\\ e \\c \\\\ b d \\\\ be\end {bmatrix} $ $

and

$ $ \begin{bmatrix} a b \\\\ c \ d \end{bmatrix} \otimes \begin{bmatrix} e \ f\\\\g \ h \end{bmatrix} = \begin{bmatrix} a\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} b\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} \\\\[1em] c\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} d\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} \end{bmatrix} = \begin{bmatrix} ae \ af \ bf \\\\ ag \ ah \ bg \ bh \\\\ ce \ cf \ de \ df \\\\ cg \ ch \ dg \ dh \ dh \end{bmatrix}。
$$

围绕 tensor 产品的最终有用的符号约定是：对于任何向量 $v $ 或 matrix $M $，$v ^ {\otimes n} $ 或 $M ^ {\otimes n} $ 对于 $n $-折页重复的 tensor 产品而言是一小的。  例如：

\begin{align} & \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ {\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}，\qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}、\qquad\begin{bmatrix} 1 \\\\-1 \end{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 1 \\\\ \\\\\\\\1 \end{bmatrix}，\\\\ & \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ {\otimes 1} = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix}，\qquad\begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 &\\\\ & 1 & 0& 0 \ end {bmatrix}。
\end{align}

