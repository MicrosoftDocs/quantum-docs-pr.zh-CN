---
title: 量子计算中的向量和矩阵
description: 了解有关如何使用向量和矩阵的基本知识。
author: QuantumWriter
uid: microsoft.quantum.concepts.vectors
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
ms.openlocfilehash: 6c09531cd8bee8f5efb472c95c575daed04d3040
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630207"
---
# <a name="vectors-and-matrices"></a><span data-ttu-id="f120a-103">向量和矩阵</span><span class="sxs-lookup"><span data-stu-id="f120a-103">Vectors and Matrices</span></span>

<span data-ttu-id="f120a-104">熟悉矢量和矩阵对于了解量程计算至关重要。</span><span class="sxs-lookup"><span data-stu-id="f120a-104">Some familiarity with vectors and matrices is essential to understand quantum computing.</span></span> <span data-ttu-id="f120a-105">我们提供了下面的简要介绍，并建议读者阅读有关线性代数（如*Strang，G （1993））的标准引用。线性代数简介（卷3）。Wellesley、MA： Wellesley-剑桥按下*或联机引用，如[线性代数](http://joshua.smcvt.edu/linearalgebra/)。</span><span class="sxs-lookup"><span data-stu-id="f120a-105">We provide a brief introduction below and interested readers are recommended to read a standard reference on linear algebra such as *Strang, G. (1993). Introduction to linear algebra (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* or an online reference such as [Linear Algebra](http://joshua.smcvt.edu/linearalgebra/).</span></span>

<span data-ttu-id="f120a-106">[*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics)) $ 维度（或大小） $n 的列向量 $v $ 为 $n $ 复数 $ （v_1，v_2，\ldots，v_n） $ （按列排列）的集合：</span><span class="sxs-lookup"><span data-stu-id="f120a-106">A column vector (or simply [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v$ of dimension (or size) $n$ is a collection of $n$ complex numbers $(v_1,v_2,\ldots,v_n)$ arranged as a column:</span></span>

<span data-ttu-id="f120a-107">$ $v = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-107">$$v =\begin{bmatrix}</span></span>
<span data-ttu-id="f120a-108">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="f120a-108">v_1\\\\</span></span>
<span data-ttu-id="f120a-109">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="f120a-109">v_2\\\\</span></span>
<span data-ttu-id="f120a-110">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="f120a-110">\vdots\\\\</span></span>
<span data-ttu-id="f120a-111">v_n \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="f120a-111">v_n \end{bmatrix}$$</span></span>

<span data-ttu-id="f120a-112">向量 $v 的标准 $ 定义为 $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $。</span><span class="sxs-lookup"><span data-stu-id="f120a-112">The norm of a vector $v$ is defined as $\sqrt{\sum\_i |v\_i|^2}$.</span></span> <span data-ttu-id="f120a-113">如果向量的标准为 $1，则将其视为单位规范（或者，也称为[*单位矢量*](https://en.wikipedia.org/wiki/Unit_vector)） $ 。</span><span class="sxs-lookup"><span data-stu-id="f120a-113">A vector is said to be of unit norm (or alternatively it is called a [*unit vector*](https://en.wikipedia.org/wiki/Unit_vector)) if its norm is $1$.</span></span> <span data-ttu-id="f120a-114">向量 $v 的[*adjoint*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ 表示 $v ^ \dagger $ ，并定义为以下行向量，其中 $ \* $ 表示共轭复数，</span><span class="sxs-lookup"><span data-stu-id="f120a-114">The [*adjoint of a vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v$ is denoted $v^\dagger$ and is defined to be the following row vector where $\*$ denotes the complex conjugate,</span></span>

<span data-ttu-id="f120a-115">$ $ \begin{ bmatrix } v_1 \\ \\ \vdots \\ \\ v_n \end{ bmatrix } ^ \dagger = \begin{ bmatrix } v_1 ^ \* & \cdots & v_n ^ \* \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="f120a-115">$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix}^\dagger = \begin{bmatrix}v_1^\* & \cdots & v_n^\* \end{bmatrix}$$</span></span>

<span data-ttu-id="f120a-116">将两个矢量相乘的最常见方法是通过[*内部产品*](https://en.wikipedia.org/wiki/Inner_product_space)（也称为点积）。</span><span class="sxs-lookup"><span data-stu-id="f120a-116">The most common way to multiply two vectors together is through the [*inner product*](https://en.wikipedia.org/wiki/Inner_product_space), also known as a dot product.</span></span>  <span data-ttu-id="f120a-117">内部产品提供了一个向量的投影到另一个向量，这在描述如何将一个向量表达为其他更简单的向量的总和方面非常有用。</span><span class="sxs-lookup"><span data-stu-id="f120a-117">The inner product gives the projection of one vector onto another and is invaluable in describing how to express one vector as a sum of other simpler vectors.</span></span>  <span data-ttu-id="f120a-118">$U 和 $v 之间的内部积 $ $ ，表示 $ \left \langle u，v \right \rangle $ 定义为</span><span class="sxs-lookup"><span data-stu-id="f120a-118">The inner product between $u$ and $v$, denoted $\left\langle u, v\right\rangle$ is defined as</span></span>

<span data-ttu-id="f120a-119">$ $ \langle u，v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } v_1 + \cdots + u \_ n ^ { \* } v \_ n。</span><span class="sxs-lookup"><span data-stu-id="f120a-119">$$ \langle u, v\rangle = u^\dagger v=u\_1^{\*} v_1 + \cdots + u\_n^{\*} v\_n.</span></span>
$$

<span data-ttu-id="f120a-120">此表示法还允许将矢量 $v 的标准 $ 编写为 $ \sqrt { \langle v \rangle } $。</span><span class="sxs-lookup"><span data-stu-id="f120a-120">This notation also allows the norm of a vector $v$ to be written as $\sqrt{\langle v, v\rangle}$.</span></span>

<span data-ttu-id="f120a-121">我们可以将一个向量与一个数字进行相乘 $ ，$c 以构成一个新向量，其项与 $c 相乘 $ 。</span><span class="sxs-lookup"><span data-stu-id="f120a-121">We can multiply a vector with a number $c$ to form a new vector whose entries are multiplied by $c$.</span></span> <span data-ttu-id="f120a-122">还可以添加两个向量 $u $ 和 $v， $ 以形成新的向量，其项是 $u 和 $v 项的总和 $ $ 。</span><span class="sxs-lookup"><span data-stu-id="f120a-122">We can also add two vectors $u$ and $v$ to form a new vector whose entries are the sum of the entries of $u$ and $v$.</span></span> <span data-ttu-id="f120a-123">这些操作如下所示：</span><span class="sxs-lookup"><span data-stu-id="f120a-123">These operations are depicted below:</span></span>

<span data-ttu-id="f120a-124">$ $ \mathrm{If } ~ u = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-124">$$\mathrm{If}~u =\begin{bmatrix}</span></span>
<span data-ttu-id="f120a-125">u_1\\\\</span><span class="sxs-lookup"><span data-stu-id="f120a-125">u_1\\\\</span></span>
<span data-ttu-id="f120a-126">u_2\\\\</span><span class="sxs-lookup"><span data-stu-id="f120a-126">u_2\\\\</span></span>
<span data-ttu-id="f120a-127">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="f120a-127">\vdots\\\\</span></span>
<span data-ttu-id="f120a-128">u_n \end{ bmatrix } ~ \mathrm{and } ~ v = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-128">u_n \end{bmatrix}~\mathrm{and}~ v =\begin{bmatrix}</span></span>
    <span data-ttu-id="f120a-129">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="f120a-129">v_1\\\\</span></span>
    <span data-ttu-id="f120a-130">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="f120a-130">v_2\\\\</span></span>
    <span data-ttu-id="f120a-131">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="f120a-131">\vdots\\\\</span></span>
    <span data-ttu-id="f120a-132">v_n \end{ bmatrix } ，~ \mathrm{then } ~ au + bv = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-132">v_n \end{bmatrix},~\mathrm{then}~ au+bv =\begin{bmatrix}</span></span>
<span data-ttu-id="f120a-133">au_1 + bv_1\\\\</span><span class="sxs-lookup"><span data-stu-id="f120a-133">au_1+bv_1\\\\</span></span>
<span data-ttu-id="f120a-134">au_2 + bv_2\\\\</span><span class="sxs-lookup"><span data-stu-id="f120a-134">au_2+bv_2\\\\</span></span>
<span data-ttu-id="f120a-135">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="f120a-135">\vdots\\\\</span></span>
<span data-ttu-id="f120a-136">au_n + bv_n \end{ bmatrix } 。</span><span class="sxs-lookup"><span data-stu-id="f120a-136">au_n+bv_n \end{bmatrix}.</span></span>
$$

<span data-ttu-id="f120a-137">大小[*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics))为 $m \times n 的矩阵 $ 是 $ 按 $m 行和 $n 列排列的 $mn 复数的集合，如下 $ $ 所示：</span><span class="sxs-lookup"><span data-stu-id="f120a-137">A [*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) of size $m \times n$ is a collection of $mn$ complex numbers arranged in $m$ rows and $n$ columns as shown below:</span></span>

<span data-ttu-id="f120a-138">$ $M = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-138">$$M = \begin{bmatrix}</span></span>
<span data-ttu-id="f120a-139">M_ {11 } ~ ~ M_ {12 } ~ ~ \cdots ~ ~ M_ {1n } \\ \\ M_ {21 } ~ ~ M_ {22 } ~ ~ \cdots ~ ~ M_ {2n } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="f120a-139">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\ M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="f120a-140">M_ {m1 } ~ ~ M_ {m2 } ~ ~ \cdots ~ ~ M_ {mn } \\ \\ \end{ bmatrix } . $ $</span><span class="sxs-lookup"><span data-stu-id="f120a-140">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}\\\\ \end{bmatrix}.$$</span></span>

<span data-ttu-id="f120a-141">请注意，维度 $n 的矢量 $ 只是大小 $n \times 1 的矩阵 $ 。</span><span class="sxs-lookup"><span data-stu-id="f120a-141">Note that a vector of dimension $n$ is simply a matrix of size $n \times 1$.</span></span> <span data-ttu-id="f120a-142">与矢量一样，我们可以将矩阵与数字 $c 相乘， $ 以获取一个新矩阵，其中每个条目都与 $c 相乘 $ ，可以添加两个相同大小的矩阵以生成一个新矩阵，该矩阵的条目是两个矩阵各自条目的总和。</span><span class="sxs-lookup"><span data-stu-id="f120a-142">As with vectors, we can multiply a matrix with a number $c$ to obtain a new matrix where every entry is multiplied with $c$, and we can add two matrices of the same size to produce a new matrix whose entries are the sum of the respective entries of the two matrices.</span></span> 

## <a name="matrix-multiplication-and-tensor-products"></a><span data-ttu-id="f120a-143">Matrix 乘法 and Tensor Products</span><span class="sxs-lookup"><span data-stu-id="f120a-143">Matrix Multiplication and Tensor Products</span></span>

<span data-ttu-id="f120a-144">我们还可以将 $ 维度 $m n $M 的两个矩阵 \times $ 与 $ 维度 $n \times p 的 $N 相乘， $ 以获取 $ 维度 $P \times p 的新矩阵 $m， $ 如下所示：</span><span class="sxs-lookup"><span data-stu-id="f120a-144">We can also multiply two matrices $M$ of dimension $m\times n$ and $N$ of dimension $n \times p$ to get a new matrix $P$ of dimension $m \times p$ as follows:</span></span>

<span data-ttu-id="f120a-145">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="f120a-145">\begin{align}</span></span>
<span data-ttu-id="f120a-146">& \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-146">&\begin{bmatrix}</span></span>
    <span data-ttu-id="f120a-147">M_ {11 } ~ ~ M_ {12 } ~ ~ \cdots ~ ~ M_ {1n } \\ \\ M_ {21 } ~ ~ M_ {22 } ~ ~ \cdots ~ ~ M_ {2n } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="f120a-147">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\ M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\ \ddots\\\\</span></span>
    <span data-ttu-id="f120a-148">M_ {m1 } ~ ~ M_ {m2 } ~ ~ \cdots ~ ~ M_ {mn}</span><span class="sxs-lookup"><span data-stu-id="f120a-148">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}</span></span>
<span data-ttu-id="f120a-149">端面bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-149">\end{bmatrix}</span></span>
<span data-ttu-id="f120a-150">准备bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-150">\begin{bmatrix}</span></span>
<span data-ttu-id="f120a-151">N_ {11 } ~ ~ N_ {12 } ~ ~ \cdots ~ ~ N_ {1 p } \\ \\ N_ {21 } ~ ~ N_ {22 } ~ ~ \cdots ~ ~ N_ {2 p } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="f120a-151">N_{11} ~~ N_{12} ~~ \cdots ~~ N_{1p}\\\\ N_{21} ~~ N_{22} ~~ \cdots ~~ N_{2p}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="f120a-152">N_ {n1 } ~ ~ N_ {n2 } ~ ~ \cdots ~ ~ N_ {np}</span><span class="sxs-lookup"><span data-stu-id="f120a-152">N_{n1} ~~ N_{n2} ~~ \cdots ~~ N_{np}</span></span>
<span data-ttu-id="f120a-153">\end{ bmatrix } = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-153">\end{bmatrix}=\begin{bmatrix}</span></span>
<span data-ttu-id="f120a-154">P_ {11 } ~ ~ P_ {12 } ~ ~ \cdots ~ ~ P_ {1 p } \\ \\ P_ {21 } ~ ~ P_ {22 } ~ ~ \cdots ~ ~ P_ {2 p } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="f120a-154">P_{11} ~~ P_{12} ~~ \cdots ~~ P_{1p}\\\\ P_{21} ~~ P_{22} ~~ \cdots ~~ P_{2p}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="f120a-155">P_ {m1 } ~ ~ P_ {m2 } ~ ~ \cdots ~ ~ P_ {mp}</span><span class="sxs-lookup"><span data-stu-id="f120a-155">P_{m1} ~~ P_{m2} ~~ \cdots ~~ P_{mp}</span></span>
<span data-ttu-id="f120a-156">端面bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-156">\end{bmatrix}</span></span>
<span data-ttu-id="f120a-157">\end{align}</span><span class="sxs-lookup"><span data-stu-id="f120a-157">\end{align}</span></span>

<span data-ttu-id="f120a-158">其中 $P 的条目 $ $P _ {ik } = \ sum_j M_ {ij} N_ {jk } $。</span><span class="sxs-lookup"><span data-stu-id="f120a-158">where the entries of $P$ are $P_{ik} = \sum_j M_{ij}N_{jk}$.</span></span> <span data-ttu-id="f120a-159">例如，$P _ {11 $ 的条目 } 是 $N 第一列的 $M 的第一行的内部乘积 $ $ 。</span><span class="sxs-lookup"><span data-stu-id="f120a-159">For example, the entry $P_{11}$ is the inner product of the first row of $M$ with the first column of $N$.</span></span> <span data-ttu-id="f120a-160">请注意，由于矢量只是矩阵的一种特殊情况，因此此定义延伸到矩阵向量乘法。</span><span class="sxs-lookup"><span data-stu-id="f120a-160">Note that since a vector is simply a special case of a matrix, this definition extends to matrix-vector multiplication.</span></span> 

<span data-ttu-id="f120a-161">我们考虑的所有矩阵均为方形矩阵，其中的行数和列数相等，或向量仅对应于 $1 $ 列。</span><span class="sxs-lookup"><span data-stu-id="f120a-161">All the matrices we consider will either be square matrices, where the number of rows and columns are equal, or vectors, which corresponds to only $1$ column.</span></span> <span data-ttu-id="f120a-162">一个特殊的正方形矩阵为[*标识矩阵*](https://en.wikipedia.org/wiki/Identity_matrix)，表示 $ \boldone $ ，它的所有对角线元素都等于 $1， $ 其余元素等于 $0 $ ：</span><span class="sxs-lookup"><span data-stu-id="f120a-162">One special square matrix is the [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix), denoted $\boldone$, which has all its diagonal elements equal to $1$ and the remaining elements equal to $0$:</span></span>

<span data-ttu-id="f120a-163">$ $ \boldone = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-163">$$\boldone=\begin{bmatrix}</span></span>
<span data-ttu-id="f120a-164">1 ~ ~ 0 ~ ~ \cdots ~ ~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="f120a-164">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="f120a-165">0 ~ ~ 1 ~ ~ \cdots ~ ~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="f120a-165">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="f120a-166">~ ~ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="f120a-166">~~ \ddots\\\\</span></span>
<span data-ttu-id="f120a-167">0 ~ ~ 0 ~ ~ \cdots ~ ~ 1 \end{ bmatrix } . $ $</span><span class="sxs-lookup"><span data-stu-id="f120a-167">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix}.$$</span></span>

<span data-ttu-id="f120a-168">对于正方形矩阵 $A $ ， $ 如果 $AB = BA = \boldone，则表示矩阵 $B[*反转*](https://en.wikipedia.org/wiki/Invertible_matrix) $ 。</span><span class="sxs-lookup"><span data-stu-id="f120a-168">For a square matrix $A$, we say a matrix $B$ is its [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) if $AB = BA = \boldone$.</span></span> <span data-ttu-id="f120a-169">矩阵的逆矩阵不需要存在，但如果它存在，则它是唯一的，并将其表示 $A ^ {-1 } $。</span><span class="sxs-lookup"><span data-stu-id="f120a-169">The inverse of a matrix need not exist, but when it exists it is unique and we denote it $A^{-1}$.</span></span> 

<span data-ttu-id="f120a-170">对于任何矩阵 $M $ ，$M 的 adjoint 或共轭转置 $ 为一个矩阵 $N， $ 以便 $N _ {ij } = M_ {ji } ^ \* $。</span><span class="sxs-lookup"><span data-stu-id="f120a-170">For any matrix $M$, the adjoint or conjugate transpose of $M$ is a matrix $N$ such that $N_{ij} = M_{ji}^\*$.</span></span> <span data-ttu-id="f120a-171">$M 的 adjoint $ 通常 $M ^ \dagger 表示 $ 。</span><span class="sxs-lookup"><span data-stu-id="f120a-171">The adjoint of $M$ is usually denoted $M^\dagger$.</span></span> <span data-ttu-id="f120a-172">$如果 $UU ^ \dagger = u [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) ^ \dagger U = \boldone $ 或等效项 $U ^ {-1 } = u ^ \dagger，则表示矩阵 $U 为单一矩阵 $ 。</span><span class="sxs-lookup"><span data-stu-id="f120a-172">We say a matrix $U$ is [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) if $UU^\dagger = U^\dagger U = \boldone$ or equivalently, $U^{-1} = U^\dagger$.</span></span>  <span data-ttu-id="f120a-173">单一矩阵的最重要的属性可能是它们保留向量的标准。</span><span class="sxs-lookup"><span data-stu-id="f120a-173">Perhaps the most important property of unitary matrices is that they preserve the norm of a vector.</span></span>  <span data-ttu-id="f120a-174">出现这种情况的原因是</span><span class="sxs-lookup"><span data-stu-id="f120a-174">This happens because</span></span> 

<span data-ttu-id="f120a-175">$ $ \langle v，v \rangle = v ^ \dagger v = v ^ \dagger U ^ {-1 } U v = v ^ \Dagger u ^ \Dagger U v = \Langle U v，U v \rangle . $ $</span><span class="sxs-lookup"><span data-stu-id="f120a-175">$$\langle v,v \rangle=v^\dagger v = v^\dagger U^{-1} U v = v^\dagger U^\dagger U v = \langle U v, U v\rangle.$$</span></span>  

<span data-ttu-id="f120a-176">$如果 $M = M ^ \dagger，则将矩阵 $M 称为[*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) $ 。</span><span class="sxs-lookup"><span data-stu-id="f120a-176">A matrix $M$ is said to be [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) if $M=M^\dagger$.</span></span>

<span data-ttu-id="f120a-177">最后，两个矩阵的[*tensor 产品*](https://en.wikipedia.org/wiki/Tensor_product)（或 Kronecker 产品） $M 大小为 $ $m \times n $ ，$N $ 大小 $p \times q $ 为大小更大的矩阵 $P \otimes $ \times nq $ ，并 $ 按如下所示从 $mp 和 $M 获取 $ ：</span><span class="sxs-lookup"><span data-stu-id="f120a-177">Finally, the [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (or Kronecker product) of two matrices $M$ of size $m\times n$ and $N$ of size $p \times q$ is a larger matrix $P=M\otimes N$ of size $mp \times nq$, and is obtained from $M$ and $N$ as follows:</span></span>

<span data-ttu-id="f120a-178">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="f120a-178">\begin{align}</span></span>
    <span data-ttu-id="f120a-179">M \otimes N &= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-179">M \otimes N &= \begin{bmatrix}</span></span>
        <span data-ttu-id="f120a-180">M_ {11 } ~ ~ \cdots ~ ~ M_ {1n } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="f120a-180">M_{11} ~~ \cdots ~~ M_{1n} \\\\ \ddots\\\\</span></span>
        <span data-ttu-id="f120a-181">M_ {m1 } ~ ~ \cdots ~ ~ M_ {mn}</span><span class="sxs-lookup"><span data-stu-id="f120a-181">M_{m1}  ~~ \cdots ~~ M_{mn}</span></span>
    <span data-ttu-id="f120a-182">端面bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-182">\end{bmatrix}</span></span>
    <span data-ttu-id="f120a-183">\otimes \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-183">\otimes \begin{bmatrix}</span></span>
        <span data-ttu-id="f120a-184">N_ {11 } ~ ~ \cdots ~ ~ N_ {1q } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="f120a-184">N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\</span></span>
        <span data-ttu-id="f120a-185">N_ {p1 } ~ ~ \cdots ~ ~ N_ {pq}</span><span class="sxs-lookup"><span data-stu-id="f120a-185">N_{p1} ~~ \cdots ~~ N_{pq}</span></span>
    <span data-ttu-id="f120a-186">\end{ bmatrix } \\ \\ &= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-186">\end{bmatrix}\\\\ &= \begin{bmatrix}</span></span>
        <span data-ttu-id="f120a-187">M_ {11 } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1q } \\ \\ \ddots \\\\ N_ {p1 } ~ ~ \cdots ~ ~ N_ {pq } \end{ bmatrix } ~ ~ \cdots ~ ~ M_ {1n } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ } \\ \\ \\\\ } 1q ~ ~ N_ {\ddots } \cdots bmatrix } \\ \\ pq\\\\</span><span class="sxs-lookup"><span data-stu-id="f120a-187">M_{11} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~ M_{1n} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}\\\\ \ddots\\\\</span></span>
        <span data-ttu-id="f120a-188">M_ {m1 } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1q } \\ \\ \ddots \\\\ N_ {p1 } ~ ~ \cdots ~ ~ N_ {pq } \end{ bmatrix } ~ ~ \cdots ~ ~ M_ {mn } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ } \\ \\ \\\\ } 1q ~ N_ {\ddots } \cdotsbmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-188">M_{m1} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~ M_{mn} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}</span></span>
    <span data-ttu-id="f120a-189">\end{ bmatrix } 。</span><span class="sxs-lookup"><span data-stu-id="f120a-189">\end{bmatrix}.</span></span>
<span data-ttu-id="f120a-190">\end{align}</span><span class="sxs-lookup"><span data-stu-id="f120a-190">\end{align}</span></span>

<span data-ttu-id="f120a-191">下面的示例对此进行了更好的演示：</span><span class="sxs-lookup"><span data-stu-id="f120a-191">This is better demonstrated with some examples:</span></span>

<span data-ttu-id="f120a-192">$ $ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-192">$$ \begin{bmatrix}</span></span>
        <span data-ttu-id="f120a-193">a \\ \\ b \end{ bmatrix } \otimes \begin{ bmatrix } c \\ \\ d \\ \\ e \end{ bmatrix } = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-193">a \\\\ b  \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} = \begin{bmatrix}</span></span>
        <span data-ttu-id="f120a-194">\begin{ bmatrix } c \\ \\ d \\ \\ e \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-194">a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}</span></span>
        <span data-ttu-id="f120a-195">\\\\[1.5 em] b \begin{ bmatrix } c \\ \\ d \\ \\ e \end {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-195">\\\\[1.5em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span></span>
    <span data-ttu-id="f120a-196">端面bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-196">\end{bmatrix}</span></span>
    <span data-ttu-id="f120a-197">= \begin{ bmatrix } a c a \\ \\ d \\ \\ a e \\ \\ b c \\ \\ b d \\ \\ 是 \end {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-197">= \begin{bmatrix} a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end{bmatrix}</span></span>
$$

<span data-ttu-id="f120a-198">和</span><span class="sxs-lookup"><span data-stu-id="f120a-198">and</span></span>

<span data-ttu-id="f120a-199">$ $ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-199">$$ \begin{bmatrix}</span></span>
        <span data-ttu-id="f120a-200">a b \\ \\ c d \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-200">a\ b \\\\ c\ d \end{bmatrix}</span></span>
    <span data-ttu-id="f120a-201">\otimes \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-201">\otimes \begin{bmatrix}</span></span>
        <span data-ttu-id="f120a-202">e \ f \\ \\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-202">e\ f\\\\g\ h \end{bmatrix}</span></span>
     <span data-ttu-id="f120a-203">= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-203">= \begin{bmatrix}</span></span>
    <span data-ttu-id="f120a-204">\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-204">a\begin{bmatrix}</span></span>
    <span data-ttu-id="f120a-205">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-205">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="f120a-206">b \begin {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-206">b\begin{bmatrix}</span></span>
    <span data-ttu-id="f120a-207">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-207">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="f120a-208">\\\\[1em] c \begin {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-208">\\\\[1em] c\begin{bmatrix}</span></span>
    <span data-ttu-id="f120a-209">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-209">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="f120a-210">d \begin {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-210">d\begin{bmatrix}</span></span>
    <span data-ttu-id="f120a-211">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-211">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="f120a-212">端面bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-212">\end{bmatrix}</span></span>
    <span data-ttu-id="f120a-213">= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f120a-213">= \begin{bmatrix}</span></span>
    <span data-ttu-id="f120a-214">ae \ af \ \ bf \\ \\ ag \ ah \ bg \ bh \\ \\ ce \ cf \ df \\ \\ cg \ ch \ dg \ dh \ \end{ bmatrix } 。</span><span class="sxs-lookup"><span data-stu-id="f120a-214">ae\ af\ be\ bf \\\\ ag\ ah\ bg\ bh \\\\ ce\ cf\ de\ df \\\\ cg\ ch\ dg\ dh \end{bmatrix}.</span></span>
$$

<span data-ttu-id="f120a-215">围绕 tensor 产品的最终有用的符号约定是：对于任何向量 $v $ 或矩阵 $M $ ，$v ^ {\otimes n } $ 或 $M ^ {\otimes n } $ 对于 $n $ -折页重复的 tensor 产品而言是一种简单的方法。</span><span class="sxs-lookup"><span data-stu-id="f120a-215">A final useful notational convention surrounding tensor products is that, for any vector $v$ or matrix $M$, $v^{\otimes n}$ or $M^{\otimes n}$ is short hand for an $n$-fold repeated tensor product.</span></span>  <span data-ttu-id="f120a-216">例如：</span><span class="sxs-lookup"><span data-stu-id="f120a-216">For example:</span></span>

<span data-ttu-id="f120a-217">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="f120a-217">\begin{align}</span></span>
<span data-ttu-id="f120a-218">& \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } ，\qquad \begin { bmatrix } 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 0 \\ \\ \end{ bmatrix } ，\qquad \begin { bmatrix } 1 \\ \\ -1 \end{ bmatrix } ^ {\otimes 2 } = \begin{1-1 1 bmatrix } \\ \\ \\ \\ \\ \\ \end{ bmatrix } ， \\ \\ & \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ，\qquad \begin { bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 0 &0&0&1 0 &0 \\&\\ 1 \\ \\ \\\\ \end bmatrix }&0 &&0 {。</span><span class="sxs-lookup"><span data-stu-id="f120a-218">&\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ -1 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ -1 \\\\-1 \\\\1 \end{bmatrix}, \\\\ &\begin{bmatrix}  0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 1}= \begin{bmatrix}    0& 1 \\\\ 1& 0  \end{bmatrix},  \qquad\begin{bmatrix} 0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 2}= \begin{bmatrix} 0 &0&0&1 \\\\ 0 &0&1&0 \\\\ 0 &1&0&0\\\\ 1 &0&0&0\end{bmatrix}.</span></span>
<span data-ttu-id="f120a-219">\end{align}</span><span class="sxs-lookup"><span data-stu-id="f120a-219">\end{align}</span></span>
