---
title: 高级矩阵概念
description: 了解本征向量、本征值和 matrix 指数，这是用于描述和模拟量程算法的基本工具。
author: QuantumWriter
uid: microsoft.quantum.concepts.matrix-advanced
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
ms.openlocfilehash: 8d3c646715f13c454e51b9295cbfdabf6a236ffc
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630152"
---
# <a name="advanced-matrix-concepts"></a><span data-ttu-id="b5372-103">高级矩阵概念</span><span class="sxs-lookup"><span data-stu-id="b5372-103">Advanced Matrix Concepts</span></span> #

<span data-ttu-id="b5372-104">现在，我们将矩阵操作扩展到[*本征值、本征向量*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors)和[*指数*](https://en.wikipedia.org/wiki/Matrix_exponential)，这构成了我们需要描述和实现量程算法的一组基本工具。</span><span class="sxs-lookup"><span data-stu-id="b5372-104">We now extend our manipulation of Matrices to [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) and [*Exponentials*](https://en.wikipedia.org/wiki/Matrix_exponential) which form a fundamental set of tools we need to describe and implement quantum algorithms.</span></span>

## <a name="eigenvalues-and-eigenvectors"></a><span data-ttu-id="b5372-105">本征值和本征向量</span><span class="sxs-lookup"><span data-stu-id="b5372-105">Eigenvalues and Eigenvectors</span></span> ##

<span data-ttu-id="b5372-106">让 $M $ 成为正方形矩阵，$v 是 $ 不是全零向量（即，其所有条目都等于 $0）的矢量。 $</span><span class="sxs-lookup"><span data-stu-id="b5372-106">Let $M$ be a square matrix and $v$ be a vector that is not the all zeros vector (i.e., the vector with all entries equal to $0$).</span></span>

<span data-ttu-id="b5372-107">$ [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) $ 如果 $Mv = cv $ 为某些数字 $c，则我们说 $v 是 $M 的 eigenvector $ 。</span><span class="sxs-lookup"><span data-stu-id="b5372-107">We say $v$ is an [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) of  $M$ if $Mv = cv$ for some number $c$.</span></span> <span data-ttu-id="b5372-108">我们说 $c $ 是对应于 eigenvector $v 的[*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) $ 。</span><span class="sxs-lookup"><span data-stu-id="b5372-108">We say $c$ is the [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) corresponding to the eigenvector $v$.</span></span> <span data-ttu-id="b5372-109">通常，矩阵 $M $ 可以将矢量转换为任何其他向量，但 eigenvector 是特殊的，因为它会保持不变，但会乘以数字。</span><span class="sxs-lookup"><span data-stu-id="b5372-109">In general a matrix $M$ may transform a vector into any other vector, but an eigenvector is special because it is left unchanged except for being multiplied by a number.</span></span> <span data-ttu-id="b5372-110">请注意，如果 $v $ 是 eigenvalue $c 的 eigenvector $ ，则 $av $ 也是具有相同 eigenvalue 的 eigenvector （适用于任何非零 $a $ ）。</span><span class="sxs-lookup"><span data-stu-id="b5372-110">Note that if $v$ is an eigenvector with eigenvalue $c$, then $av$ is also an eigenvector (for any nonzero $a$) with the same eigenvalue.</span></span>

<span data-ttu-id="b5372-111">例如，对于恒等矩阵，每个向量 $v $ 都是 eigenvalue $1 的 eigenvector $ 。</span><span class="sxs-lookup"><span data-stu-id="b5372-111">For example, for the identity matrix, every vector $v$ is an eigenvector with eigenvalue $1$.</span></span>

<span data-ttu-id="b5372-112">作为另一个示例，请考虑使用[*对角矩阵*](https://en.wikipedia.org/wiki/Diagonal_matrix)$D， $ 其对角线上只包含非零条目：</span><span class="sxs-lookup"><span data-stu-id="b5372-112">As another example, consider a [*diagonal matrix*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D$ which only has nonzero entries on the diagonal:</span></span>

<span data-ttu-id="b5372-113">$ $ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="b5372-113">$$ \begin{bmatrix}</span></span>
<span data-ttu-id="b5372-114">d_1 & 0 & 0 \\ \\ 0 & d_2 & 0 \\ \\ 0 & 0 & d_3 \end{ bmatrix } 。</span><span class="sxs-lookup"><span data-stu-id="b5372-114">d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="b5372-115">矢量</span><span class="sxs-lookup"><span data-stu-id="b5372-115">The vectors</span></span>

<span data-ttu-id="b5372-116">$ $ \begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 \end{ bmatrix } ，\begin{ bmatrix } 0 \\ \\ 1 \\ \\ 0 \end { bmatrix } and \begin{ bmatrix } 0 \\ \\ 0 \\ \\ 1 \end {bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="b5372-116">$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}, \begin{bmatrix}0 \\\\ 1 \\\\ 0\end{bmatrix} and \begin{bmatrix}0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span></span>

<span data-ttu-id="b5372-117">是此矩阵的本征向量，分别为本征值 $d _1 $ 、$d _2 $ 和 $d _3 $ 。</span><span class="sxs-lookup"><span data-stu-id="b5372-117">are eigenvectors of this matrix with eigenvalues  $d_1$, $d_2$, and $d_3$, respectively.</span></span> <span data-ttu-id="b5372-118">如果 $d _1 $ 、$d _2 $ 和 $d _3 $ 为非重复数字，则这些矢量（及其序列图）是矩阵 $D 的唯一本征向量 $ 。</span><span class="sxs-lookup"><span data-stu-id="b5372-118">If $d_1$, $d_2$, and $d_3$ are distinct numbers, then these vectors (and their multiples) are the only eigenvectors of the matrix $D$.</span></span> <span data-ttu-id="b5372-119">通常，对于对角矩阵，可以轻松地将本征值和本征向量读取。</span><span class="sxs-lookup"><span data-stu-id="b5372-119">In general, for a diagonal matrix it is easy to read off the eigenvalues and eigenvectors.</span></span> <span data-ttu-id="b5372-120">本征值是显示在对角线上的所有数字，其各自的本征向量为单位矢量，其中一项等于 $1 $ ，剩余项等于 $0 $ 。</span><span class="sxs-lookup"><span data-stu-id="b5372-120">The eigenvalues are all the numbers appearing on the diagonal, and their respective eigenvectors are the unit vectors with one entry equal to $1$ and the remaining entries equal to $0$.</span></span>

<span data-ttu-id="b5372-121">请注意，在上面的示例中，$D 的本征向量 $ 构成了 $3 $ 维矢量的基础。</span><span class="sxs-lookup"><span data-stu-id="b5372-121">Note in the above example that the eigenvectors of $D$ form a basis for $3$-dimensional vectors.</span></span> <span data-ttu-id="b5372-122">基础是一组矢量，以便可以将任何矢量编写为它们的线性组合。</span><span class="sxs-lookup"><span data-stu-id="b5372-122">A basis is a set of vectors such that any vector can be written as a linear combination of them.</span></span> <span data-ttu-id="b5372-123">更明确、$v _1 $ 、$v _2 $ 和 $v _3 $ 在任何向量 $v $ 都可以编写为 $v = a_1 v_1 + a_2 v_2 + a_3 v_3 $a $ _1 $ 、$a _2 $ 和 $a _3 $ ，</span><span class="sxs-lookup"><span data-stu-id="b5372-123">More explicitly, $v_1$, $v_2$, and $v_3$ form a basis if any vector $v$ can be written as $v=a_1 v_1 + a_2 v_2 + a_3 v_3$ for some numbers $a_1$, $a_2$, and $a_3$.</span></span>

<span data-ttu-id="b5372-124">回忆一下，Hermitian 矩阵（也称为 adjoint）是一个复杂的正方形矩阵，它等于其自身的共轭复数，而单一矩阵是一个复杂的正方形矩阵，其反转等于其复数共轭。</span><span class="sxs-lookup"><span data-stu-id="b5372-124">Recall that a Hermitian matrix (also called self-adjoint) is a complex square matrix equal to its own complex conjugate, while a unitary matrix is a complex square matrix whose inverse is equal to its complex conjugate.</span></span>
<span data-ttu-id="b5372-125">对于本质上只是在量程计算中遇到的唯一矩阵的 Hermitian 和单一矩阵，一般结果称为[*spectral 定理*](https://en.wikipedia.org/wiki/Spectral_theorem)，这会断言以下内容：对于任何 Hermitian 或单一矩阵 $M，都 $ 存在一个单一 $U， $ $M = U ^ \dagger D u $ 用于某个对角矩阵 $D $ 。</span><span class="sxs-lookup"><span data-stu-id="b5372-125">For Hermitian and unitary matrices, which are essentially the only matrices encountered in quantum computing, there is a general result known as the [*spectral theorem*](https://en.wikipedia.org/wiki/Spectral_theorem), which asserts the following: For any Hermitian or unitary matrix $M$, there exists a unitary $U$ such that $M=U^\dagger D U$ for some diagonal matrix $D$.</span></span> <span data-ttu-id="b5372-126">此外，$D 的对角线条目 $ 将是 $M 的本征值 $ 。</span><span class="sxs-lookup"><span data-stu-id="b5372-126">Furthermore, the diagonal entries of $D$ will be the eigenvalues of $M$.</span></span>

<span data-ttu-id="b5372-127">我们已经知道如何计算对角矩阵的本征值和本征向量 $D $ 。</span><span class="sxs-lookup"><span data-stu-id="b5372-127">We already know how to compute the eigenvalues and eigenvectors of a diagonal matrix $D$.</span></span> <span data-ttu-id="b5372-128">使用此定理，我们知道，如果 $v $ 是具有 eigenvalue $c 的 $D 的 eigenvector $ $ （即 $Dv = cv $ ），则 $U ^ \dagger v $ 将是 eigenvector $M 的 eigenvalue 的 $ $ 。</span><span class="sxs-lookup"><span data-stu-id="b5372-128">Using this theorem we know that if $v$ is an eigenvector of $D$ with eigenvalue $c$, i.e., $Dv = cv$, then $U^\dagger v$ will be an eigenvector of $M$ with eigenvalue $c$.</span></span> <span data-ttu-id="b5372-129">这是因为</span><span class="sxs-lookup"><span data-stu-id="b5372-129">This is because</span></span>

<span data-ttu-id="b5372-130">$ $M （U ^ \dagger v） = U ^ \dagger D U （U ^ \dagger v） = U ^ \dagger D （U U ^ \dagger） v = U ^ \dagger D v = c U ^ \dagger v. $ $</span><span class="sxs-lookup"><span data-stu-id="b5372-130">$$M(U^\dagger v) = U^\dagger D U  (U^\dagger v) =U^\dagger D (U  U^\dagger) v = U^\dagger D v = c U^\dagger v.$$</span></span>

## <a name="matrix-exponentials"></a><span data-ttu-id="b5372-131">Matrix 指数</span><span class="sxs-lookup"><span data-stu-id="b5372-131">Matrix Exponentials</span></span>
<span data-ttu-id="b5372-132">[*矩阵指数*](https://en.wikipedia.org/wiki/Matrix_exponential)还可以精确地定义为指数函数。</span><span class="sxs-lookup"><span data-stu-id="b5372-132">A [*matrix exponential*](https://en.wikipedia.org/wiki/Matrix_exponential) can also be defined in exact analogy to the exponential function.</span></span>  <span data-ttu-id="b5372-133">矩阵 $A 的矩阵指数 $ 可表示为</span><span class="sxs-lookup"><span data-stu-id="b5372-133">The matrix exponential of a matrix $A$ can be expressed as</span></span>

<span data-ttu-id="b5372-134">$ $ e ^ A = \boldone + A + \frac{A ^ 2 } {2！}+ \frac{A ^ 3 } {3！}+ \cdots $ $</span><span class="sxs-lookup"><span data-stu-id="b5372-134">$$ e^A=\boldone + A + \frac{A^2}{2!}+\frac{A^3}{3!}+\cdots $$</span></span>

<span data-ttu-id="b5372-135">这一点很重要，因为在 Hermitian matrix $B 的窗体 $e ^ {iB $ 形式的单一矩阵中描述了量子机械时间演变 } $ 。</span><span class="sxs-lookup"><span data-stu-id="b5372-135">This is important because quantum mechanical time evolution is described by a unitary matrix of the form $e^{iB}$ for Hermitian matrix $B$.</span></span>  <span data-ttu-id="b5372-136">出于此原因，执行 matrix 指数是量程计算的基本组成部分，因此，此类 Q # 提供了用于描述这些操作的内部例程。</span><span class="sxs-lookup"><span data-stu-id="b5372-136">For this reason, performing matrix exponentials is a fundamental part of quantum computing and as such Q# offers intrinsic routines for describing these operations.</span></span>
<span data-ttu-id="b5372-137">有很多方法可用于计算传统计算机上的矩阵指数，一般为数值逼近，这类指数为充满 with 担风险。</span><span class="sxs-lookup"><span data-stu-id="b5372-137">There are many ways in practice to compute a matrix exponential on a classical computer, and in general numerically approximating such an exponential is fraught with peril.</span></span>  <span data-ttu-id="b5372-138">请参阅[*Cleve Moler 和 Charles Van 贷款。"用于计算矩阵指数的可疑方法。"SIAM 评审20.4 （1978）： 801-836*](https://doi.org/10.1137/S00361445024180) ，详细了解涉及的挑战。</span><span class="sxs-lookup"><span data-stu-id="b5372-138">See [*Cleve Moler and Charles Van Loan. "Nineteen dubious ways to compute the exponential of a matrix." SIAM review 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) for more information about the challenges involved.</span></span>

<span data-ttu-id="b5372-139">了解如何计算矩阵指数的最简单方法是通过该矩阵的本征值和本征向量。</span><span class="sxs-lookup"><span data-stu-id="b5372-139">The easiest way to understand how to compute the exponential of a matrix is through the eigenvalues and eigenvectors of that matrix.</span></span>  <span data-ttu-id="b5372-140">具体而言，以上所述的 spectral 定理说明对于每个 Hermitian 或单一矩阵 $A $ 存在一个单一矩阵 $U $ 和一个对角矩阵 $D $ ，$A = U ^ \dagger D U $ 。 由于 unitarity 的属性，我们已 $A ^ 2 = U ^ \dagger D ^ 2 U $ ，同样适用于任何 power $p $ $A ^ p = U ^ \dagger D ^ p u $ 。 如果将此替换为我们获得的运算符指数的运算符定义：</span><span class="sxs-lookup"><span data-stu-id="b5372-140">Specifically, the spectral theorem discussed above says that for every Hermitian or unitary matrix $A$ there exists a unitary matrix $U$ and a diagonal matrix $D$ such that $A=U^\dagger D U$.  Because of the properties of unitarity we have that $A^2 = U^\dagger D^2 U$ and similarly for any power $p$ $A^p = U^\dagger D^p U$.  If we substitute this into the operator definition of the operator exponential we obtain:</span></span>

<span data-ttu-id="b5372-141">$ $ e ^ A = U ^ \dagger \left （\boldone + D + \frac{D ^ 2 } {2！}+ \cdots \right） U = u ^ \dagger \begin{ bmatrix } \exp （D_ {11 } ） & 0 & \cdots &0 \\\\ 0 & \exp （D_ {22 } ） & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0&0 & \cdots & \exp （D_ {NN } ） \end{ bmatrix } U. $ $</span><span class="sxs-lookup"><span data-stu-id="b5372-141">$$ e^A= U^\dagger \left(\boldone +D +\frac{D^2}{2!}+\cdots \right)U= U^\dagger \begin{bmatrix}\exp(D_{11}) & 0 &\cdots &0\\\\ 0 & \exp(D_{22})&\cdots& 0\\\\ \vdots &\vdots &\ddots &\vdots\\\\ 0&0&\cdots&\exp(D_{NN}) \end{bmatrix} U. $$</span></span>

<span data-ttu-id="b5372-142">换言之，如果您转换为 $A 矩阵的 eigenbasis，则 $ 计算矩阵指数等效于计算矩阵本征值的普通指数。</span><span class="sxs-lookup"><span data-stu-id="b5372-142">In other words, if you transform to the eigenbasis of the matrix $A$ then computing the matrix exponential is equivalent to computing the ordinary exponential of the eigenvalues of the matrix.</span></span>  <span data-ttu-id="b5372-143">由于量程计算中的许多操作都涉及到执行矩阵指数，因此，转换为矩阵的 eigenbasis 以简化执行运算符指数的这一技巧会经常出现，并且是本指南后面部分中讨论的 Trotter – Suzuki 样式的量程模拟方法的基础。</span><span class="sxs-lookup"><span data-stu-id="b5372-143">As many operations in quantum computing involve performing matrix exponentials, this trick of transforming into the eigenbasis of a matrix to simplify performing the operator exponential appears frequently and is the basis behind many quantum algorithms such as Trotter–Suzuki-style quantum simulation methods discussed later in this guide.</span></span>

<span data-ttu-id="b5372-144">另一个有用的属性是 $ ，如果 $B 为单一和 Hermitian，即 $B = b ^ {-1 } = b ^ \dagger， $ 则 $B ^ 2 = \boldone $ 。</span><span class="sxs-lookup"><span data-stu-id="b5372-144">Another useful property is if $B$ is both unitary and Hermitian, i.e., $B=B^{-1}=B^\dagger$ then $B^2=\boldone$.</span></span> <span data-ttu-id="b5372-145">通过将此规则应用于矩阵指数的以上扩展，并通过将 $ \boldone $ 和 $B 词组合在 $ 一起，可以看到该标识 $x 的任何真实值 $</span><span class="sxs-lookup"><span data-stu-id="b5372-145">By applying this rule to the above expansion of the matrix exponential and by grouping the $\boldone$ and the $B$ terms together, it can be see that for any real value $x$ the identity</span></span>

<span data-ttu-id="b5372-146">$ $e ^ {iBx } = \boldone \cos （x） + iB\sin （x） $ $</span><span class="sxs-lookup"><span data-stu-id="b5372-146">$$e^{iBx}=\boldone \cos(x)+ iB\sin(x)$$</span></span>


<span data-ttu-id="b5372-147">保留.</span><span class="sxs-lookup"><span data-stu-id="b5372-147">holds.</span></span> <span data-ttu-id="b5372-148">这一技巧特别有用，因为它允许有关操作矩阵指数的原因，即使 $B 的维度的大小 $ 呈指数大，在 $B 既是单一还是 Hermitian 的情况下，也是如此 $ 。</span><span class="sxs-lookup"><span data-stu-id="b5372-148">This trick is especially useful because it allows to reason about the actions matrix exponentials have, even if the dimension of $B$ is exponentially large, for the special case when $B$ is both unitary and Hermitian.</span></span>
