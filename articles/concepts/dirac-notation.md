---
title: 狄拉克表示法
description: 了解如何使用 Dirac 表示法来表示量程状态并模拟量程操作。
author: QuantumWriter
uid: microsoft.quantum.concepts.dirac
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- $
- $
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
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: f9dddfa25e9fd1e3d8aaf92b2e3b17c96ed8b72a
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269500"
---
# <a name="dirac-notation"></a><span data-ttu-id="123a7-103">Dirac 表示法</span><span class="sxs-lookup"><span data-stu-id="123a7-103">Dirac Notation</span></span>

<span data-ttu-id="123a7-104">虽然列矢量表示法在线性代数中无处不在，但在处理多个 qubits 时，量程计算通常会很繁琐。</span><span class="sxs-lookup"><span data-stu-id="123a7-104">While column vector notation is ubiquitous in linear algebra, it is often cumbersome in quantum computing especially when dealing with multiple qubits.</span></span>  <span data-ttu-id="123a7-105">例如，如果将 $ \psi 定义为 $ 矢量，则不会明确清楚 $ \psi $ 是行向量还是列向量。</span><span class="sxs-lookup"><span data-stu-id="123a7-105">For example, when we define $\psi$ to be a vector it is not explicitly clear whether $\psi$ is a row or a column vector.</span></span>  <span data-ttu-id="123a7-106">因此，如果 $ \phi $ 和 $ \psi $ 是向量，则即使定义了 $ \phi \psi，也同样不清楚， $ 因为 $ \phi $ 和 $ \psi 的形状 $ 在上下文中可能不清楚。</span><span class="sxs-lookup"><span data-stu-id="123a7-106">Thus if $\phi$ and $\psi$ are vectors then it is equally unclear if $\phi \psi$ is even defined because the shapes of $\phi$ and $\psi$ may be unclear in the context.</span></span>  <span data-ttu-id="123a7-107">除了矢量形状的歧义外，使用前面引入的线性代数表示法来表示更简单的矢量会非常麻烦。</span><span class="sxs-lookup"><span data-stu-id="123a7-107">Beyond the ambiguity about the shapes of vectors, expressing even simple vectors using the linear algebraic notation introduced earlier can be very cumbersome.</span></span> <span data-ttu-id="123a7-108">例如，如果我们想要说明 $n $ qubit 状态，其中每个 qubit 都采用值 $0， $ 则我们会将状态正式表示为</span><span class="sxs-lookup"><span data-stu-id="123a7-108">For example, if we wish to describe an $n$-qubit state where each qubit takes the value $0$ then we would formally express the state as</span></span> 

<span data-ttu-id="123a7-109">$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \cdots \otimes \begin { bmatrix } 1 \\ \\ 0 \end{ bmatrix } 。</span><span class="sxs-lookup"><span data-stu-id="123a7-109">$$\begin{bmatrix}1 \\\\  0 \end{bmatrix}\otimes \cdots \otimes\begin{bmatrix}1 \\\\  0 \end{bmatrix}.</span></span> $$  

<span data-ttu-id="123a7-110">当然，评估此 tensor 的产品是不切实际的，因为矢量位于呈指数量大的空间，因此此表示法实际上是可使用上一个表示法提供的状态的最佳说明。</span><span class="sxs-lookup"><span data-stu-id="123a7-110">Of course evaluating this tensor product is impractical because the vector lies in an exponentially large space and so this notation is in fact the best description of the state that can be given using the previous notation.</span></span>  

<span data-ttu-id="123a7-111">[*Dirac 表示法*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation)解决了这些问题的方法是，通过提供一种新语言来满足量程机制的精确需求。</span><span class="sxs-lookup"><span data-stu-id="123a7-111">[*Dirac notation*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) solves these issues by presenting a new language to fit the precise needs of quantum mechanics.</span></span>  <span data-ttu-id="123a7-112">出于此原因，我们建议读者不要查看本部分中的示例，作为如何描述量程状态的严格处方，而是鼓励读者查看这些示例，这是可用于简洁表达量子创意的建议。</span><span class="sxs-lookup"><span data-stu-id="123a7-112">For this reason, we recommend the reader not view the examples in this section as a rigid prescription of how to describe quantum states, but rather encourage the reader to view these as suggestions that can be used to concisely express quantum ideas.</span></span>

<span data-ttu-id="123a7-113">Dirac 表示法中有两种类型的向量：*寄存器*向量和*票证*向量，因此命名为，因为当将它们组合在一起构成*braket*或内部产品。</span><span class="sxs-lookup"><span data-stu-id="123a7-113">There are two types of vectors in Dirac notation: the *bra* vector and the *ket* vector, so named because when put together they form a *braket* or inner product.</span></span>  <span data-ttu-id="123a7-114">如果 $ \psi $ 是一个列向量，则可以使用 Dirac 表示法将其编写为 $ \ket { \psi } $，其中，$ \ket { \cdot } $ 表示它是一个单位列向量，即*票证*向量。</span><span class="sxs-lookup"><span data-stu-id="123a7-114">If $\psi$ is a column vector then we can write it in Dirac notation as $\ket{\psi}$, where the $\ket{\cdot}$ denotes that it is a unit column vector, i.e., a *ket* vector.</span></span>  <span data-ttu-id="123a7-115">同样，行向量 $ \psi ^ \dagger $ 表示为 $ \bra { \psi } $。</span><span class="sxs-lookup"><span data-stu-id="123a7-115">Similarly, the row vector $\psi^\dagger$ is expressed as $\bra{\psi}$.</span></span> <span data-ttu-id="123a7-116">换句话说， $ 通过对 $ \psi 的换位的元素应用按输入的复杂语态，可以获得 $ \psi ^ \dagger $ 。</span><span class="sxs-lookup"><span data-stu-id="123a7-116">In other words, $\psi^\dagger$ is obtained by applying entry-wise complex conjugation to the elements of the transpose of $\psi$.</span></span> <span data-ttu-id="123a7-117">寄存器-票证表示法直接表示 $ \braket { \psi | \psi } $ 是其自身的矢量 $ \psi 的内部积，即 $ 按定义 $1 $ 。</span><span class="sxs-lookup"><span data-stu-id="123a7-117">The bra-ket notation directly implies that $\braket{\psi|\psi}$ is the inner product of vector $\psi$ with itself, which is by definition $1$.</span></span>  

<span data-ttu-id="123a7-118">更常见的情况是，如果 $ \psi $ 和 $ \phi $ 是量程状态向量，则其内部产品是 $ \braket { \phi | \psi } $，这表示将状态 $ \ket \psi $ 的度量度量的概率是 $ \ket \phi { } { } $ is $ | \braket { \phi | } | ^ 2 $ 。</span><span class="sxs-lookup"><span data-stu-id="123a7-118">More generally, if $\psi$ and $\phi$ are quantum state vectors their inner product is $\braket{\phi|\psi}$ which implies that the probability of measuring the state $\ket{\psi}$ to be $\ket{\phi}$ is $|\braket{\phi|\psi}|^2$.</span></span>  

<span data-ttu-id="123a7-119">以下约定用于描述为零和一个（qubit 计算基础状态）的值进行编码的量程状态：</span><span class="sxs-lookup"><span data-stu-id="123a7-119">The following convention is used to describe the quantum states that encode the values of zero and one (the single-qubit computational basis states):</span></span>

<span data-ttu-id="123a7-120">$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \ket{0 } ，\qquad \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } = \ket{1 } 。</span><span class="sxs-lookup"><span data-stu-id="123a7-120">$$ \begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \ket{0},\qquad \begin{bmatrix} 0 \\\\  1 \end{bmatrix} = \ket{1}.</span></span>
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a><span data-ttu-id="123a7-121">示例：表示具有 Dirac 表示法的 Hadamard 操作</span><span class="sxs-lookup"><span data-stu-id="123a7-121">Example: representing the Hadamard operation with Dirac notation</span></span>

<span data-ttu-id="123a7-122">以下表示法通常用于描述通过将 Hadamard 入口应用到 $ \ket{0 } $ 和 $ \ket{1 } $ （对应于 Bloch 球体上 $ + x $ 和 $-x 方向的单位矢量）而产生的状态 $ ：</span><span class="sxs-lookup"><span data-stu-id="123a7-122">The following notation is often used to describe the states that result from applying the Hadamard gate to $\ket{0}$ and $\ket{1}$ (which correspond to the unit vectors in the $+x$ and $-x$ directions on the Bloch sphere):</span></span>

<span data-ttu-id="123a7-123">$ $ \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 \\ \\ 1 \end{ bmatrix } = H \ket {0 } = \ket { +}，\qquad \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 \\ \\ -1 \end{ bmatrix } = H \ket {1 } = \ket { -}。</span><span class="sxs-lookup"><span data-stu-id="123a7-123">$$ \frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  1 \end{bmatrix}=H\ket{0} = \ket{+},\qquad \frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  -1 \end{bmatrix} =H\ket{1} = \ket{-} .</span></span>
$$

<span data-ttu-id="123a7-124">还可以使用 Dirac 表示法将这些状态扩展为 $ \ket{0 } $ 和 $ \ket{1 } $：</span><span class="sxs-lookup"><span data-stu-id="123a7-124">These states can also be expanded using Dirac notation as sums of $\ket{0}$ and $\ket{1}$:</span></span>

<span data-ttu-id="123a7-125">$ $ \ket { +} = \frac{1 } {\sqrt{2 } } （\ket{0 } + \ket{1 } ），\qquad \ket { -} = \frac{1 } {\sqrt{2 } } （\ket{0 } -\ket{1 } ）。</span><span class="sxs-lookup"><span data-stu-id="123a7-125">$$ \ket{+} = \frac{1}{\sqrt{2}}(\ket{0} + \ket{1}),\qquad \ket{-} = \frac{1}{\sqrt{2}}(\ket{0} - \ket{1}).</span></span>
$$

### <a name="computational-basis-vectors"></a><span data-ttu-id="123a7-126">计算基础向量</span><span class="sxs-lookup"><span data-stu-id="123a7-126">Computational basis vectors</span></span>
<span data-ttu-id="123a7-127">这说明了这些状态通常称为*计算基础*：每个量程状态始终可以表示为计算基础向量的总和，此类 sum 可以使用 Dirac 表示法来表示。</span><span class="sxs-lookup"><span data-stu-id="123a7-127">This demonstrates why these states are often called a *computational basis*: every quantum state can always be expressed as sums of computational basis vectors and such sums are easily expressed using Dirac notation.</span></span>  <span data-ttu-id="123a7-128">反之也是如此，因为状态 $ \ket { +} $ 和 $ \ket { -} $ 也构成了量程状态的基础。</span><span class="sxs-lookup"><span data-stu-id="123a7-128">The converse is also true in that the states $\ket{+}$ and $\ket{-}$ also form a basis for quantum states.</span></span>  <span data-ttu-id="123a7-129">你可以看到这样的事实：</span><span class="sxs-lookup"><span data-stu-id="123a7-129">You can see this from the fact that</span></span>

<span data-ttu-id="123a7-130">$ $ \ket{0 } = \frac{1 } {\sqrt{2 } } （\ket { +} + \ket { -}），\qquad \ket{1 } = \frac{1 } {\sqrt{2 } } （\ket { +}-\ket { -}）。</span><span class="sxs-lookup"><span data-stu-id="123a7-130">$$ \ket{0} = \frac{1}{\sqrt{2}}(\ket{+} + \ket{-}),\qquad \ket{1} = \frac{1}{\sqrt{2}}(\ket{+} - \ket{-}).</span></span>
$$

<span data-ttu-id="123a7-131">作为 Dirac 表示法的示例，请考虑 braket $ \braket{0 | 1 } $，它是 $0 和 $1 之间的内部产品 $ $ 。</span><span class="sxs-lookup"><span data-stu-id="123a7-131">As an example of Dirac notation, consider the braket $\braket{0 | 1}$, which is the inner product between $0$ and $1$.</span></span>  <span data-ttu-id="123a7-132">它可以编写为</span><span class="sxs-lookup"><span data-stu-id="123a7-132">It can be written as</span></span> 

<span data-ttu-id="123a7-133">$ $ \braket{0 | 1 } = \begin{ bmatrix } 1 & 0 \end{ bmatrix } \begin{ bmatrix } 0 \\\\ 1 \end{bmatrix} = 0. $ $</span><span class="sxs-lookup"><span data-stu-id="123a7-133">$$\braket{0 | 1}=\begin{bmatrix} 1 & 0 \end{bmatrix}\begin{bmatrix}0\\\\ 1\end{bmatrix}=0.$$</span></span>

<span data-ttu-id="123a7-134">这表明 $ \ket{0 } $ 和 $ \ket{1 } $ 是正交向量，这意味着 $ \braket{0 | 1 } = \braket{1 | 0 } = 0 $ 。</span><span class="sxs-lookup"><span data-stu-id="123a7-134">This says that $\ket{0}$ and $\ket{1}$ are orthogonal vectors, meaning that $\braket{0 | 1} = \braket{1 | 0} =0$.</span></span>  <span data-ttu-id="123a7-135">还按定义 $ \braket{0 | 0 } = \braket{1 | 1 } = 1 $ ，这意味着两个计算基础向量也可以被称为*orthonormal*。</span><span class="sxs-lookup"><span data-stu-id="123a7-135">Also by definition $\braket{0 | 0} = \braket{1 | 1}=1$, which means that the two computational basis vectors can also be called *orthonormal*.</span></span>
<span data-ttu-id="123a7-136">在下面的示例中，这些 orthonormal 属性将非常有用。</span><span class="sxs-lookup"><span data-stu-id="123a7-136">These orthonormal properties will be useful in the following example.</span></span> <span data-ttu-id="123a7-137">如果我们有状态 $ \ket { \psi } = {\frac{3 } {5 } } \ket{1 } + {\frac{4 } {5 } } \ket{0 $， } 则因为 $ \braket{1 | 0 } = 0 $ ，所以衡量 $1 的概率 $</span><span class="sxs-lookup"><span data-stu-id="123a7-137">If we have a state $\ket{\psi} = {\frac{3}{5}} \ket{1} + {\frac{4}{5}} \ket{0}$ then because $\braket{1 | 0} =0$ the probability of measuring $1$  is</span></span>  

<span data-ttu-id="123a7-138">$ $ \big | \braket{1 | \psi } \big | ^ 2 = \left | \frac{3 } {5 } \braket{1 | 1 } + \frac{4 } {5 } \braket{1 | 0 } \right | ^ 2 = \frac{9 } {25 } . $ $</span><span class="sxs-lookup"><span data-stu-id="123a7-138">$$\big|\braket{1 | \psi}\big|^2= \left|\frac{3}{5}\braket{1 | 1} +\frac{4}{5}\braket{1 | 0}\right|^2=\frac{9}{25}.$$</span></span> 

### <a name="tensor-product-notation"></a><span data-ttu-id="123a7-139">Tensor 产品表示法</span><span class="sxs-lookup"><span data-stu-id="123a7-139">Tensor product notation</span></span>
<span data-ttu-id="123a7-140">Dirac 表示法还包括其中的隐式 tensor 产品结构。</span><span class="sxs-lookup"><span data-stu-id="123a7-140">Dirac notation also includes an implicit tensor product structure within it.</span></span>  <span data-ttu-id="123a7-141">这一点很重要，因为在量程计算中，两个不相关的量程寄存器描述的状态向量是两个状态向量的 tensor 产品。</span><span class="sxs-lookup"><span data-stu-id="123a7-141">This is important because in quantum computing, the state vector described by two uncorrelated quantum registers is the tensor products of the two state vectors.</span></span>  <span data-ttu-id="123a7-142">如果您想要解释量程计算，则很重要的是，如果您想要说明量程计算，则非常重要的是 tensor 产品结构或缺少</span><span class="sxs-lookup"><span data-stu-id="123a7-142">Concisely describing the tensor product structure, or lack thereof, is vital if you want to explain a quantum computation.</span></span>  <span data-ttu-id="123a7-143">Tensor product 结构意味着我们可以将 $ 任意两个量程状态向量 $ \phi 和 $ \psi 的 $ \psi \otimes \phi 编写为 $ $ $ \ket { \psi \ket \phi } { } $，有时会显式编写为 $ \ket \psi \otimes \ket $ { } { } ，但约定 $ 不需要在两个向量之间编写 $ \phi。</span><span class="sxs-lookup"><span data-stu-id="123a7-143">The tensor product structure implies that we can write $\psi \otimes \phi$ for any two quantum state vectors $\phi$ and $\psi$ as $\ket{\psi} \ket{\phi}$, sometimes explicitly written as $\ket{\psi} \otimes \ket{\phi}$, however by convention writing $\otimes$ in between the vectors is unnecessary.</span></span>  <span data-ttu-id="123a7-144">例如，将两个 qubits 初始化为零状态的状态由指定</span><span class="sxs-lookup"><span data-stu-id="123a7-144">For example, the state with two qubits initialized to the zero state is given by</span></span>

<span data-ttu-id="123a7-145">$ $ \begin{ bmatrix } 1 \\ \\ 0 0 \\ \\ \\ \\ 0 \end{ bmatrix } = \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \ket{0 } \otimes \ket{0 } = \ket{0 } \ket{0 } 。</span><span class="sxs-lookup"><span data-stu-id="123a7-145">$$ \begin{bmatrix} 1 \\\\  0 \\\\  0 \\\\  0 \end{bmatrix}= \begin{bmatrix} 1 \\\\  0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \ket{0} \otimes \ket{0}= \ket{0} \ket{0}.</span></span>
$$

<span data-ttu-id="123a7-146">同样，integer $p 的状态 $ \ket{p } $ $ 表示以二进制表示法编码 $p 整数表示形式的量程状态 $ 。</span><span class="sxs-lookup"><span data-stu-id="123a7-146">Similarly,  the state $\ket{p}$ for integer $p$ represents a quantum state that encodes in binary representation the integer $p$.</span></span>  <span data-ttu-id="123a7-147">例如，如果想要 $ 使用无符号二进制编码来表示数字 $5，我们可以将其视为</span><span class="sxs-lookup"><span data-stu-id="123a7-147">For example, if we wish to express the number $5$ using an unsigned binary encoding we could equally express it as</span></span>

<span data-ttu-id="123a7-148">$ $ \ket{1 } \ket{0 } \ket{1 } = \ket{101 } = \ket{5 } 。</span><span class="sxs-lookup"><span data-stu-id="123a7-148">$$ \ket{1}\ket{0}\ket{1} = \ket{101} = \ket{5}.</span></span>
$$

<span data-ttu-id="123a7-149">在此表示法中 } ，$ \ket{0 $ 不需要引用单一 qubit 状态，而是使用*qubit register*存储二进制编码 $0 $ 。</span><span class="sxs-lookup"><span data-stu-id="123a7-149">Within this notation $\ket{0}$ need not refer to a single-qubit state but rather a *qubit register* storing a binary encoding of $0$.</span></span>  <span data-ttu-id="123a7-150">这两个表示法之间的差异通常来自上下文。</span><span class="sxs-lookup"><span data-stu-id="123a7-150">The differences between these two notations is usually clear from the context.</span></span>  <span data-ttu-id="123a7-151">此约定可用于简化第一个示例，该示例可通过以下任何一种方式编写：</span><span class="sxs-lookup"><span data-stu-id="123a7-151">This convention is useful for simplifying the first example which can be written in any of the following ways:</span></span>

<span data-ttu-id="123a7-152">$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \cdots \otimes \begin { bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \ket{0 } \otimes \cdots \otimes \ket{0 } = | 0 \cdots 0 \rangle = \ket{0 } ^ {\otimes n } = \ket{0 } 。</span><span class="sxs-lookup"><span data-stu-id="123a7-152">$$ \begin{bmatrix}1 \\\\  0 \end{bmatrix}\otimes \cdots \otimes\begin{bmatrix}1 \\\\  0 \end{bmatrix} = \ket{0} \otimes \cdots \otimes \ket{0}= |0\cdots 0\rangle = \ket{0}^{\otimes n} = \ket{0}.</span></span>
$$

### <a name="example-describing-superposition-with-dirac-notation"></a><span data-ttu-id="123a7-153">示例：用 Dirac 表示法描述 superposition</span><span class="sxs-lookup"><span data-stu-id="123a7-153">Example: Describing superposition with Dirac notation</span></span>
<span data-ttu-id="123a7-154">作为另一个示例，说明如何使用 Dirac 表示法来描述量程状态，请考虑以下等效方式：写入一个量程状态，该状态是每个可能的长度字符串的相等 superposition $n$</span><span class="sxs-lookup"><span data-stu-id="123a7-154">As another example of how you can use Dirac notation to describe a quantum state, consider the following equivalent ways of writing a quantum state that is an equal superposition over every possible bit string of length $n$</span></span>

<span data-ttu-id="123a7-155">$ $ H ^ {\otimes n } \ket{0 } = \frac{1 } {2 ^ {n/2 } } \ sum_ {j = 0 } ^ {2 ^ n-1 } \ket{j } = \ket { +} ^ {\otimes n } 。</span><span class="sxs-lookup"><span data-stu-id="123a7-155">$$ H^{\otimes n} \ket{0} = \frac{1}{2^{n/2}} \sum_{j=0}^{2^n-1} \ket{j} = \ket{+}^{\otimes n}.</span></span>
$$

<span data-ttu-id="123a7-156">在此，你可能会想知道，为什么总和从 $0 $ 到 $ 2 ^ {n } -1 $ 的 $n $ 位。</span><span class="sxs-lookup"><span data-stu-id="123a7-156">Here you may wonder why the sum goes from $0$ to $2^{n}-1$ for $n$ bits.</span></span>  <span data-ttu-id="123a7-157">首先请注意，有 $ 2 ^ {n } $ 个不同的配置，$n $ bits 可以采用这种配置。</span><span class="sxs-lookup"><span data-stu-id="123a7-157">First note that there are $2^{n}$ different configurations that $n$ bits can take.</span></span>  <span data-ttu-id="123a7-158">您可以看到，这是因为有一个位可以采用 $2 $ 个值，但两个位可能需要 $4 个 $ 值等。</span><span class="sxs-lookup"><span data-stu-id="123a7-158">You can see this by noting that one bit can take $2$ values but two bits can take $4$ values and so forth.</span></span> <span data-ttu-id="123a7-159">通常，这意味着有 $ 2 ^ n 个不同的 $ 可能位字符串，但以其中任何一个编码的最大值为 $1 \cdots 1 = 2 ^ n-1 $ ，因此它是 sum 的上限。</span><span class="sxs-lookup"><span data-stu-id="123a7-159">In general, this means that there are $2^n$ different possible bit strings but the largest value encoded in any of them $1\cdots 1=2^n-1$ and hence it is the upper limit for the sum.</span></span>
<span data-ttu-id="123a7-160">例如，在此示例中，我们没有使用 $ \ket { +} ^ {\otimes n } = \ket { +} $ （与 $ \ket{0 } ^ {\otimes n } = \ket{0 $）， } 因为此符号约定通常是为计算基础状态而保留的，每个 qubit 都初始化为零。</span><span class="sxs-lookup"><span data-stu-id="123a7-160">As a side note, in this example we did not use $\ket{+}^{\otimes n}=\ket{+}$ in analogy to $\ket{0}^{\otimes n} = \ket{0}$ because this notational convention is usually reserved for the computational basis state with every qubit initialized to zero.</span></span>  <span data-ttu-id="123a7-161">虽然这种约定在这种情况下非常合理，但不会在量程计算宣传资料中使用。</span><span class="sxs-lookup"><span data-stu-id="123a7-161">While such a convention would be sensible in this case, it is not employed in the quantum computing literature.</span></span>

### <a name="expressing-linearity-with-dirac-notation"></a><span data-ttu-id="123a7-162">用 Dirac 表示法表示线性</span><span class="sxs-lookup"><span data-stu-id="123a7-162">Expressing linearity with Dirac notation</span></span>
<span data-ttu-id="123a7-163">Dirac 表示法的另一个不错的功能是线性的。</span><span class="sxs-lookup"><span data-stu-id="123a7-163">Another nice feature of Dirac notation is the fact that it is linear.</span></span>  <span data-ttu-id="123a7-164">如果我们想要为任何四个量程状态向量编写，</span><span class="sxs-lookup"><span data-stu-id="123a7-164">If we wish to write for any four quantum state vectors,</span></span> 

<span data-ttu-id="123a7-165">$ $ （\alpha \ket { \psi } + \beta \ket { \phi } ） \otimes （\gamma \ket { \chi } + \delta \ket { \omega } ） = \alpha \gamma \ket { \psi } \ket { \chi } + \alpha \ket \psi \ket \omega \beta \phi \ket \chi \delta { } { } \gamma \ket { } { \beta } + \phi \delta \ket { \ket } \omega { } . $ $</span><span class="sxs-lookup"><span data-stu-id="123a7-165">$$(\alpha \ket{\psi} +\beta\ket{\phi})\otimes (\gamma \ket{\chi} + \delta \ket{\omega})= \alpha\gamma \ket{\psi}\ket{\chi} + \alpha\delta \ket{\psi}\ket{\omega}+\beta\gamma\ket{\phi}\ket{\chi}+\beta\delta\ket{\phi}\ket{\omega}.$$</span></span>

<span data-ttu-id="123a7-166">也就是说，可以在 Dirac 表示法中分发 tensor 产品表示法，使在州向量间的 tensor 产品最终看起来就像普通的乘法。</span><span class="sxs-lookup"><span data-stu-id="123a7-166">That is to say, you can distribute the tensor product notation in Dirac notation so that taking tensor products between state vectors ends up looking just like ordinary multiplication.</span></span>

<span data-ttu-id="123a7-167">寄存器向量遵循类似的约定来票证矢量。</span><span class="sxs-lookup"><span data-stu-id="123a7-167">Bra vectors follow a similar convention to ket vectors.</span></span>  <span data-ttu-id="123a7-168">例如，vector $ \bra { \psi } \bra { \phi } $ 等效于状态向量 $ \psi ^ \dagger \otimes \phi ^ \dagger = （\psi \otimes \phi） ^ \dagger $ 。</span><span class="sxs-lookup"><span data-stu-id="123a7-168">For example, the vector $\bra{\psi}\bra{\phi}$ is equivalent to the state vector $\psi^\dagger \otimes \phi^\dagger=(\psi\otimes \phi)^\dagger$.</span></span> <span data-ttu-id="123a7-169">如果票证 vector $ \ket { \psi } $ 是 $ \alpha \ket{0 } + \beta \ket{1 $，则 } 该矢量的寄存器矢量版本是 $ \bra { \psi } = \ket { \psi } ^ \dagger = （\bra{0 } \alpha ^ \* + \bra{1 } \beta ^ \*） $。</span><span class="sxs-lookup"><span data-stu-id="123a7-169">If the ket vector $\ket{\psi}$ is $\alpha \ket{0} + \beta \ket{1}$ then the bra vector version of the vector is $\bra{\psi}=\ket{\psi}^\dagger = (\bra{0}\alpha^\* +\bra{1}\beta^\*)$.</span></span>

<span data-ttu-id="123a7-170">例如，假设我们想要使用量程程序计算状态 $ \ket { \psi } = \frac{3 } {5 } \ket{1 } + \frac{4 } {5 \ket{0 $ 的概率， } 以便 } 将状态测量为 $ \ket { +} $ 或 $ \ket { -} $。</span><span class="sxs-lookup"><span data-stu-id="123a7-170">As an example, imagine that we wish to calculate the probability of measuring the state $\ket{\psi} = \frac{3}{5} \ket{1} + \frac{4}{5} \ket{0}$ using a quantum program for measuring states to be either $\ket{+}$ or $\ket{-}$.</span></span> <span data-ttu-id="123a7-171">然后，设备将输出状态为 $ \ket { -} $ 的概率是</span><span class="sxs-lookup"><span data-stu-id="123a7-171">Then the probability that the device would output that the state is $\ket{-}$ is</span></span> 

<span data-ttu-id="123a7-172">$ $ | \braket | { \psi } | ^ 2 = \left | \frac{1 } {\sqrt{2 } } （\bra{0 } -\bra{1 } ）（\frac{3 } {5 } \ket{1 } + \frac{4 } {5 } \ket{0 } ） \right | ^ 2 = \left | -\frac{3 } {5 \sqrt {2 } } + \frac{4 } {5 \sqrt {2 } } \right | ^ 2 = \frac{1 } {50 } . $ $</span><span class="sxs-lookup"><span data-stu-id="123a7-172">$$|\braket{- | \psi}|^2= \left|\frac{1}{\sqrt{2}}(\bra{0} - \bra{1})(\frac{3}{5} \ket{1} + \frac{4}{5} \ket{0}) \right|^2=\left|-\frac{3}{5\sqrt{2}} + \frac{4}{5\sqrt{2}}\right|^2=\frac{1}{50}.$$</span></span>

<span data-ttu-id="123a7-173">负号在概率计算中出现的事实是量程干扰的表现形式，这是量程计算与传统计算相比的优点之一。</span><span class="sxs-lookup"><span data-stu-id="123a7-173">The fact that the negative sign appears in the calculation of the probability is a manifestation of quantum interference, which is one of the mechanisms by which quantum computing gains advantages over classical computing.</span></span>

## <a name="ketbra-or-outer-product"></a><span data-ttu-id="123a7-174">ketbra 或外部产品</span><span class="sxs-lookup"><span data-stu-id="123a7-174">ketbra or outer product</span></span>
<span data-ttu-id="123a7-175">Dirac 表示法中值得讨论的最后一项是*ketbra*或 outer 积。</span><span class="sxs-lookup"><span data-stu-id="123a7-175">The final item worth discussing in Dirac notation is the *ketbra* or outer product.</span></span>  <span data-ttu-id="123a7-176">外部产品在 Dirac 表示法中表示为 $ \ket { \psi } \bra { \phi } $，有时称为 ketbras，因为 bras 和 kets 的顺序与 brakets 的顺序相反。</span><span class="sxs-lookup"><span data-stu-id="123a7-176">The outer product is represented within Dirac notations as $\ket{\psi} \bra{\phi}$, and sometimes called ketbras because the bras and kets occur in the opposite order as brakets.</span></span>  <span data-ttu-id="123a7-177">{ } { } $ 对于量程状态向量 $ \psi $ 和 $ \phi， $ 外部产品通过矩阵相乘定义为 "\ket \psi \bra \phi = \dagger \psi ^ \phi"。</span><span class="sxs-lookup"><span data-stu-id="123a7-177">The outer product is defined via matrix multiplication as $\ket{\psi} \bra{\phi} = \psi \phi^\dagger$ for quantum state vectors $\psi$ and $\phi$.</span></span>  <span data-ttu-id="123a7-178">最简单且最常见的是此表示法的示例是</span><span class="sxs-lookup"><span data-stu-id="123a7-178">The simplest, and arguably most common example of this notation, is</span></span>

<span data-ttu-id="123a7-179">$ $ \ket{0 } \bra{0 } = \begin{ bmatrix } 1 \\\\ 0 \end{ bmatrix } \begin{ bmatrix } 1&0 \end{ bmatrix } = \begin{ bmatrix } 1 &0 \\\\ 0 &0 \end{bmatrix} \qquad \ket{1 } \bra{1 } = \begin{ bmatrix } 0 \\\\ 1 \end{ bmatrix } \begin{ bmatrix } 0&1 \end{ bmatrix } = \begin{ bmatrix } 0 &0 \\\\ 0 &1 \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="123a7-179">$$ \ket{0} \bra{0} = \begin{bmatrix}1\\\\ 0 \end{bmatrix}\begin{bmatrix}1&0 \end{bmatrix}= \begin{bmatrix}1 &0\\\\ 0 &0\end{bmatrix} \qquad \ket{1} \bra{1} = \begin{bmatrix}0\\\\ 1 \end{bmatrix}\begin{bmatrix}0&1 \end{bmatrix}= \begin{bmatrix}0 &0\\\\ 0 &1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="123a7-180">Ketbras 通常称为投影机，因为它们将量程状态投影到一个固定值。</span><span class="sxs-lookup"><span data-stu-id="123a7-180">Ketbras are often called projectors because they project a quantum state onto a fixed value.</span></span>  <span data-ttu-id="123a7-181">由于这些操作并不是单一操作（甚至不会保留矢量的标准），因此，量程计算机不能准确地应用投影仪。</span><span class="sxs-lookup"><span data-stu-id="123a7-181">Since these operations are not unitary (and do not even preserve the norm of a vector), it should come as no surprise that a quantum computer cannot deterministically apply a projector.</span></span>  <span data-ttu-id="123a7-182">但是，投影仪可以通过一项漂亮的工作来描述度量值对量程状态的操作。</span><span class="sxs-lookup"><span data-stu-id="123a7-182">However projectors do a beautiful job of describing the action that measurement has on a quantum state.</span></span>  <span data-ttu-id="123a7-183">例如，如果我们将状态 $ \ket \psi $ 度量为 $0，则 { } 结果转换为该 $ 测量结果的状态体验是</span><span class="sxs-lookup"><span data-stu-id="123a7-183">For example, if we measure a state $\ket{\psi}$ to be $0$ then the resulting transformation that the state experiences as a result of the measurement is</span></span>

  <span data-ttu-id="123a7-184">$ $ \ket { \psi } \rightarrow \frac { （\ket{0 } \bra{0 } ） \ket { \psi } } {| \braket{0 | \psi } |}= \ket{0 } ，$ $</span><span class="sxs-lookup"><span data-stu-id="123a7-184">$$\ket{\psi} \rightarrow \frac{(\ket{0} \bra{0})\ket{\psi}}{|\braket{0 | \psi}|}= \ket{0},$$</span></span>

<span data-ttu-id="123a7-185">如果要测量状态并将其查找为 $ \ket{0 $，则需要一个 } 。</span><span class="sxs-lookup"><span data-stu-id="123a7-185">as one expects if you were to measure the state and find it to be $\ket{0}$.</span></span>  <span data-ttu-id="123a7-186">重申一重申，此类投影机无法应用于量程计算机上的状态。</span><span class="sxs-lookup"><span data-stu-id="123a7-186">To reiterate, such projectors cannot be applied on a state in a quantum computer deterministically.</span></span>  <span data-ttu-id="123a7-187">相反，它们可以最大程度地应用，结果为 $ \ket{0 } $ 会出现一些固定的概率。</span><span class="sxs-lookup"><span data-stu-id="123a7-187">Instead, they can at best be applied randomly with the result $\ket{0}$ appearing with some fixed probability.</span></span>  <span data-ttu-id="123a7-188">此类测量结果的概率可以作为 "量程" 投影仪的预期值写入状态</span><span class="sxs-lookup"><span data-stu-id="123a7-188">The probability of such a measurement succeeding can be written as the expectation value of the quantum projector in the state</span></span>

<span data-ttu-id="123a7-189">$ $ \bra { \psi } （\ket{0 } \bra{0 } ） \ket { \psi } = | \braket { \psi | 0 } | ^ 2，$ $</span><span class="sxs-lookup"><span data-stu-id="123a7-189">$$ \bra{\psi} (\ket{0} \bra{0})\ket{\psi} = |\braket{\psi | 0}|^2, $$</span></span>

<span data-ttu-id="123a7-190">这说明了投影仪只是为了表达度量过程的一种新方法。</span><span class="sxs-lookup"><span data-stu-id="123a7-190">which illustrates that projectors simply give a new way of expressing the measurement process.</span></span>

<span data-ttu-id="123a7-191">如果我们考虑将 qubit 状态的第一个 qubit 测量为 $1， $ 则还可以使用投影仪和 Dirac 表示法来更方便地描述此过程：</span><span class="sxs-lookup"><span data-stu-id="123a7-191">If instead we consider measuring the first qubit of a multi-qubit state to be $1$ then we can also describe this process conveniently using projectors and Dirac notation:</span></span>

<span data-ttu-id="123a7-192">$ $ P （\text{first qubit = 1 } ） = \bra { \psi } \left （\ket{1 } \bra{1 } \otimes \boldone ^ {\otimes n-1 } \right） \ket { \psi } 。</span><span class="sxs-lookup"><span data-stu-id="123a7-192">$$ P(\text{first qubit = 1})= \bra{\psi}\left(\ket{1}\bra{1}\otimes \boldone^{\otimes n-1}\right) \ket{\psi}.</span></span>
$$

<span data-ttu-id="123a7-193">这里，可以方便地用 Dirac 表示法编写标识矩阵</span><span class="sxs-lookup"><span data-stu-id="123a7-193">Here the identity matrix can be conveniently written in Dirac notation as</span></span>

<span data-ttu-id="123a7-194">$ $ \boldone = \ket{0 } \bra{0 } + \ket{1 } \bra{1 } = \begin{ bmatrix } 1&0 \\\\ 0&1 \end{ bmatrix } 。</span><span class="sxs-lookup"><span data-stu-id="123a7-194">$$ \boldone = \ket{0} \bra{0}+\ket{1} \bra{1}= \begin{bmatrix}1&0\\\\ 0&1 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="123a7-195">如果有两个 qubits，投影仪可以扩展为</span><span class="sxs-lookup"><span data-stu-id="123a7-195">For the case where there are two-qubits the projector can be expanded as</span></span> 

<span data-ttu-id="123a7-196">$ $ \ket{1 } \bra{1 } \otimes \id = \ket{1 } \bra{1 } \otimes （\ket{0 } \bra{0 } + \ket{1 } \bra{1 } ） = \ket{10 } \bra{10 } + \ket{11 } \bra{11 } 。</span><span class="sxs-lookup"><span data-stu-id="123a7-196">$$ \ket{1} \bra{1} \otimes \id = \ket{1}\bra{1} \otimes (\ket{0} \bra{0}+\ket{1} \bra{1})= \ket{10}\bra{10} + \ket{11}\bra{11}.</span></span>
$$

<span data-ttu-id="123a7-197">接下来，我们可以看到，这与使用列矢量表示法的 multiqubit 状态的 likelihoods 的讨论一致：</span><span class="sxs-lookup"><span data-stu-id="123a7-197">We can then see that this is consistent with the discussion about measurement likelihoods for multiqubit states using column-vector notation:</span></span>

<span data-ttu-id="123a7-198">$ $ P （\text{first qubit = 1 } ） = \psi ^ \dagger （e \_ {10} e \_ {10 } ^ \dagger + e \_ {11} e \_ {11 } ^ \dagger） \psi = | e \_ {10 } ^ \dagger \psi | ^ 2 + | e { \_ 11 } ^ \dagger \psi | ^ 2，$ $</span><span class="sxs-lookup"><span data-stu-id="123a7-198">$$ P(\text{first qubit = 1})= \psi^\dagger (e\_{10}e\_{10}^\dagger + e\_{11}e\_{11}^\dagger)\psi = |e\_{10}^\dagger \psi|^2 + |e\_{11}^\dagger \psi|^2, $$</span></span>

<span data-ttu-id="123a7-199">它与多 qubit 度量讨论相匹配。</span><span class="sxs-lookup"><span data-stu-id="123a7-199">which matches the multi-qubit measurement discussion.</span></span>  <span data-ttu-id="123a7-200">不过，将此结果通用化为多 qubit 用例，使用 Dirac 表示法比使用列矢量表示法更简单，并且完全等同于先前处理。</span><span class="sxs-lookup"><span data-stu-id="123a7-200">The generalization of this result to the multi-qubit case, however, is slightly more straightforward to express using Dirac notation than column-vector notation, and is entirely equivalent to the previous treatment.</span></span>

## <a name="density-operators"></a><span data-ttu-id="123a7-201">密度运算符</span><span class="sxs-lookup"><span data-stu-id="123a7-201">Density operators</span></span>

<span data-ttu-id="123a7-202">使用 Dirac 表示法表示的另一个有用的运算符是*密度运算符*，有时也称为*状态运算符*。</span><span class="sxs-lookup"><span data-stu-id="123a7-202">Another useful operator to express using Dirac notation is a *density operator*, sometimes also known as a *state operator*.</span></span>
<span data-ttu-id="123a7-203">量程状态向量的密度运算符采用 $ \rho = \ket { \psi } \bra { \psi } $ 格式。</span><span class="sxs-lookup"><span data-stu-id="123a7-203">A density operator for a quantum state vector takes the form $\rho = \ket{\psi} \bra{\psi}$.</span></span>
<span data-ttu-id="123a7-204">将状态表示为矩阵而不是向量的这一概念通常非常方便，因为它提供了一种表示概率计算的便利方法，还允许同时描述统计不确定性以及同一形式内的量程不确定性。</span><span class="sxs-lookup"><span data-stu-id="123a7-204">This concept of representing the state as a matrix, rather than a vector, is often convenient because it gives a convenient way of representing probability calculations, and also allows one to describe both statistical uncertainty as well as quantum uncertainty within the same formalism.</span></span>
<span data-ttu-id="123a7-205">一般的量程状态运算符（而不是向量）在量程计算的某些方面无处不在，但并不需要了解字段的基础知识。</span><span class="sxs-lookup"><span data-stu-id="123a7-205">General quantum state operators, rather than vectors, are ubiquitous in some areas of quantum computing but are not necessary to understand the basics of the field.</span></span>
<span data-ttu-id="123a7-206">对于感兴趣的读者，建议阅读中提供的参考书籍之一[以获取详细信息](xref:microsoft.quantum.more-information)。</span><span class="sxs-lookup"><span data-stu-id="123a7-206">For the interested reader, we recommend reading one of the reference books provided in [For more information](xref:microsoft.quantum.more-information).</span></span>

## <a name="q-gate-sequences-equivalent-to-quantum-states"></a><span data-ttu-id="123a7-207">Q # 入口序列等效于量程状态</span><span class="sxs-lookup"><span data-stu-id="123a7-207">Q# gate sequences equivalent to quantum states</span></span>
<span data-ttu-id="123a7-208">最后一点值得一提的是量程表示法和 Q # 编程语言：在本文档的开始中，我们提到量程状态是量程计算中信息的基础对象。</span><span class="sxs-lookup"><span data-stu-id="123a7-208">A final point worth raising about quantum notation and the Q# programming language: at the onset of this document we mentioned that the quantum state is the fundamental object of information in quantum computing.</span></span>  <span data-ttu-id="123a7-209">但这可能会令人感到吃惊，因为在 Q # 中没有量子状态的概念。</span><span class="sxs-lookup"><span data-stu-id="123a7-209">It may then come as a surprise that in Q# there is no notion of a quantum state.</span></span>  <span data-ttu-id="123a7-210">相反，所有状态仅由用于准备它们的操作描述。</span><span class="sxs-lookup"><span data-stu-id="123a7-210">Instead, all states are described only by the operations used to prepare them.</span></span>  <span data-ttu-id="123a7-211">上面的示例是对此的一个很好的说明。</span><span class="sxs-lookup"><span data-stu-id="123a7-211">The previous example is an excellent illustration of this.</span></span>  <span data-ttu-id="123a7-212">我们可以将结果表示为 $H ^ {\otimes n \ket{0 $，而不是在寄存器中的每个量程位字符串上都表示统一的 superposition } } 。</span><span class="sxs-lookup"><span data-stu-id="123a7-212">Rather than expressing a uniform superposition over every quantum bit string in a register, we can represent the result as $H^{\otimes n} \ket{0}$.</span></span>  <span data-ttu-id="123a7-213">这种状态的更短的简短说明不仅可以经典原因，而且还可以简明地定义要在软件堆栈中传播以实现算法所需的操作。</span><span class="sxs-lookup"><span data-stu-id="123a7-213">This exponentially shorter description of the state not only has the advantage that we can classically reason about it, but it also concisely defines the operations needed to be propagated through the software stack to implement the algorithm.</span></span>  <span data-ttu-id="123a7-214">出于此原因，Q # 旨在发出入口序列而不是量程状态;但理论上，这两个透视是等效的。</span><span class="sxs-lookup"><span data-stu-id="123a7-214">For this reason, Q# is designed to emit gate sequences rather than quantum states; however, at a theoretical level the two perspectives are equivalent.</span></span>
