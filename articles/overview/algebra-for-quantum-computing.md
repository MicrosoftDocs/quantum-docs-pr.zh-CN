---
title: 用于量子计算的线性代数
description: 了解需要哪些基础的线性代数概念才能理解量子计算
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.algebra
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8b06eba9cadce84aca6f87e4451026ca2ffc794f
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867635"
---
# <a name="linear-algebra-for-quantum-computing"></a><span data-ttu-id="25048-103">用于量子计算的线性代数</span><span class="sxs-lookup"><span data-stu-id="25048-103">Linear algebra for quantum computing</span></span>

<span data-ttu-id="25048-104">线性代数是量子计算的语言。</span><span class="sxs-lookup"><span data-stu-id="25048-104">Linear algebra is the language of quantum computing.</span></span> <span data-ttu-id="25048-105">虽然你无需了解它即可实现或编写量子程序，但线性代数已被广泛用于描述量子比特的状态、量子操作以及预测量子计算机将执行哪些操作来响应一系列说明。</span><span class="sxs-lookup"><span data-stu-id="25048-105">Although you don’t need to know it to implement or write quantum programs, it is widely used to describe qubit states, quantum operations, and to predict what a quantum computer will do in response to a sequence of instructions.</span></span>

<span data-ttu-id="25048-106">就像熟悉[量子物理学的基本概念](xref:microsoft.quantum.overview.understanding)可以帮助你了解量子计算一样，了解一些线性代数基础知识也可以帮助你了解量子算法的工作原理。</span><span class="sxs-lookup"><span data-stu-id="25048-106">Just like being familiar with the [basic concepts of quantum physics](xref:microsoft.quantum.overview.understanding) can help you understand quantum computing, knowing some basic linear algebra can help you understand how quantum algorithms work.</span></span> <span data-ttu-id="25048-107">至少需要熟悉向量和矩阵乘法 。</span><span class="sxs-lookup"><span data-stu-id="25048-107">At the least, you’ll want to be familiar with **vectors** and **matrix multiplication**.</span></span> <span data-ttu-id="25048-108">如需重温这些代数概念的知识，请参阅下面这些介绍基础知识的教程：</span><span class="sxs-lookup"><span data-stu-id="25048-108">If you need to refresh your knowledge of these algebra concepts, here are some tutorials that cover the basics:</span></span>

- [<span data-ttu-id="25048-109">关于线性代数的 Jupyter 笔记本教程</span><span class="sxs-lookup"><span data-stu-id="25048-109">Jupyter notebook tutorial on linear algebra</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra)
- [<span data-ttu-id="25048-110">关于复数算术的 Jupyter 笔记本教程</span><span class="sxs-lookup"><span data-stu-id="25048-110">Jupyter notebook tutorial on complex arithmetic</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic)
- [<span data-ttu-id="25048-111">用于量子计算的线性代数</span><span class="sxs-lookup"><span data-stu-id="25048-111">Linear Algebra for Quantum Computation</span></span>](https://cds.cern.ch/record/1522001/files/978-1-4614-6336-8_BookBackMatter.pdf)
- [<span data-ttu-id="25048-112">线性代数的基础知识</span><span class="sxs-lookup"><span data-stu-id="25048-112">Fundamentals of Linear Algebra</span></span>](https://www.math.ubc.ca/~carrell/NB.pdf)
- [<span data-ttu-id="25048-113">量子计算入门</span><span class="sxs-lookup"><span data-stu-id="25048-113">Quantum Computation Primer</span></span>](https://www.codeproject.com/Articles/5155638/Quantum-Computation-Primer-Part-1#exploring-quantum-superposition)

## <a name="vectors-and-matrices-in-quantum-computing"></a><span data-ttu-id="25048-114">量子计算中的向量和矩阵</span><span class="sxs-lookup"><span data-stu-id="25048-114">Vectors and matrices in quantum computing</span></span>

<span data-ttu-id="25048-115">在主题[了解量子计算](xref:microsoft.quantum.overview.understanding)中，你了解到量子比特的状态可以为 1 或 0，或者其中一个或这两者的各种叠加态。</span><span class="sxs-lookup"><span data-stu-id="25048-115">In the topic [Understanding quantum computing](xref:microsoft.quantum.overview.understanding), you saw that a qubit can be in a state of 1 or 0 or a superposition or both.</span></span> <span data-ttu-id="25048-116">使用线性代数，可将量子比特的状态描述为向量，并由单列矩阵 $\begin{bmatrix} a \\\\  b \end{bmatrix}$ 表示。</span><span class="sxs-lookup"><span data-stu-id="25048-116">Using linear algebra, the state of a qubit is described as a vector and is represented by a single column **matrix** $\begin{bmatrix} a \\\\  b \end{bmatrix}$.</span></span> <span data-ttu-id="25048-117">它也称为量子状态向量，并且必须满足 $|a|^2 + |b|^2 = 1$ 的要求。</span><span class="sxs-lookup"><span data-stu-id="25048-117">It is also known as a **quantum state vector** and must meet the requirement that $|a|^2 + |b|^2 = 1$.</span></span>  

<span data-ttu-id="25048-118">矩阵的元素表示量子比特坍缩方式的概率，其中 $|a|^2$ 是坍缩为零的概率，而 $|b|^2$ 是坍缩为 1 的概率。</span><span class="sxs-lookup"><span data-stu-id="25048-118">The elements of the matrix represent the probability of the qubit collapsing one way or the other, with $|a|^2$ being the probability of collapsing to zero, and $|b|^2$ being the probability of collapsing to one.</span></span> <span data-ttu-id="25048-119">以下矩阵均表示有效的量子状态向量：</span><span class="sxs-lookup"><span data-stu-id="25048-119">The following matrices all represent valid quantum state vectors:</span></span>

<span data-ttu-id="25048-120">$$\begin{bmatrix} 1 \\\\  0 \end{bmatrix}, \begin{bmatrix} 0 \\\\  1 \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{1}{\sqrt{2}} \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{-1}{\sqrt{2}} \end{bmatrix}, \text{ and }\begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{i}{\sqrt{2}} \end{bmatrix}.$$</span><span class="sxs-lookup"><span data-stu-id="25048-120">$$\begin{bmatrix} 1 \\\\  0 \end{bmatrix}, \begin{bmatrix} 0 \\\\  1 \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{1}{\sqrt{2}} \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{-1}{\sqrt{2}} \end{bmatrix}, \text{ and }\begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{i}{\sqrt{2}} \end{bmatrix}.$$</span></span>

<span data-ttu-id="25048-121">在[量子计算机和量子模拟器](xref:microsoft.quantum.overview.simulators)中，你还了解到用于修改量子比特状态的量子操作。</span><span class="sxs-lookup"><span data-stu-id="25048-121">In [Quantum computers and quantum simulators](xref:microsoft.quantum.overview.simulators) you also saw that quantum operations are used to modify the state of a qubit.</span></span>  <span data-ttu-id="25048-122">量子操作也可以由矩阵表示。</span><span class="sxs-lookup"><span data-stu-id="25048-122">Quantum operations can also be represented by a matrix.</span></span> <span data-ttu-id="25048-123">将量子操作应用于量子比特时，代表它们的两个矩阵将相乘，得到的答案表示执行该操作后量子比特的新状态。</span><span class="sxs-lookup"><span data-stu-id="25048-123">When a quantum operation is applied to a qubit, the two matrices that represent them are multiplied and the resulting answer represents the new state of the qubit after the operation.</span></span>  

<span data-ttu-id="25048-124">下面是用矩阵乘法表示的两个常见的量子操作。</span><span class="sxs-lookup"><span data-stu-id="25048-124">Here are two common quantum operations represented with matrix multiplication.</span></span>


<span data-ttu-id="25048-125">[`X` 操作](xref:microsoft.quantum.intrinsic.x)由 Pauli 矩阵 $X$ 表示，</span><span class="sxs-lookup"><span data-stu-id="25048-125">The [`X` operation](xref:microsoft.quantum.intrinsic.x) is represented by the Pauli matrix $X$,</span></span>

<span data-ttu-id="25048-126">$$X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix},$$</span><span class="sxs-lookup"><span data-stu-id="25048-126">$$X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix},$$</span></span>
    
<span data-ttu-id="25048-127">用于将量子比特的状态从 0 翻转到 1（反之亦然），例如</span><span class="sxs-lookup"><span data-stu-id="25048-127">and is used to flip the state of a qubit from 0 to 1 (or vice-versa), for example</span></span>

<span data-ttu-id="25048-128">$$\begin{bmatrix}0 &1\\\\ 1 &0\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \begin{bmatrix} 0 \\\\  1 \end{bmatrix}.$$</span><span class="sxs-lookup"><span data-stu-id="25048-128">$$\begin{bmatrix}0 &1\\\\ 1 &0\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \begin{bmatrix} 0 \\\\  1 \end{bmatrix}.$$</span></span>

<span data-ttu-id="25048-129">[“H”操作](xref:microsoft.quantum.intrinsic.h)由 Hadamard 变换 $H$ 表示，</span><span class="sxs-lookup"><span data-stu-id="25048-129">The ['H' operation](xref:microsoft.quantum.intrinsic.h) is represented by the Hadamard transformation $H$,</span></span>

<span data-ttu-id="25048-130">$$H = \dfrac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix},$$</span><span class="sxs-lookup"><span data-stu-id="25048-130">$$H = \dfrac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix},$$</span></span>

 <span data-ttu-id="25048-131">并将量子比特置于叠加状态，在这种状态下它甚至有可能以任一方式坍缩，如下所示</span><span class="sxs-lookup"><span data-stu-id="25048-131">and puts a qubit into a superposition state where it has an even probability of collapsing either way, as shown here</span></span>

<span data-ttu-id="25048-132">$$\frac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix}=\frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  1 \end{bmatrix}=\left(\frac{1}{\sqrt{2}}\right)^2=\frac{1}{2}.$$</span><span class="sxs-lookup"><span data-stu-id="25048-132">$$\frac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix}=\frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  1 \end{bmatrix}=\left(\frac{1}{\sqrt{2}}\right)^2=\frac{1}{2}.$$</span></span>

<span data-ttu-id="25048-133">代表量子操作的矩阵有一个要求 - 该矩阵必须是酉矩阵。</span><span class="sxs-lookup"><span data-stu-id="25048-133">A matrix that represents a quantum operation has one requirement – it must be a **unitary** matrix.</span></span> <span data-ttu-id="25048-134">只要矩阵的逆等于矩阵的共轭转置，就是酉矩阵 。</span><span class="sxs-lookup"><span data-stu-id="25048-134">A matrix is unitary if the **inverse** of the matrix is equal to the **conjugate transpose** of the matrix.</span></span>

## <a name="representing-two-qubit-states"></a><span data-ttu-id="25048-135">表示两个量子比特的状态</span><span class="sxs-lookup"><span data-stu-id="25048-135">Representing two-qubit states</span></span>

<span data-ttu-id="25048-136">在上面的示例中，使用单列矩阵 $\begin{bmatrix} a \\\\  b \end{bmatrix}$ 描述一个量子比特的状态，并通过将两个矩阵相乘来对其应用操作。</span><span class="sxs-lookup"><span data-stu-id="25048-136">In the examples above, the state of one qubit was described using a single column matrix $\begin{bmatrix} a \\\\  b \end{bmatrix}$, and applying an operation to it was described by multiplying the two matrices.</span></span> <span data-ttu-id="25048-137">但如果量子计算机使用多个量子比特，那么如何描述两个量子比特的组合状态呢？</span><span class="sxs-lookup"><span data-stu-id="25048-137">However, quantum computers use more than one qubit, so how do you describe the combined state of two qubits?</span></span> 

<span data-ttu-id="25048-138">请记住，每个量子比特都是一个向量空间，因此不能只将其相乘。</span><span class="sxs-lookup"><span data-stu-id="25048-138">Remember that each qubit is a vector space, so they can't just be multiplied.</span></span> <span data-ttu-id="25048-139">而是使用张量积，这是一个相关操作，可以从各个向量空间创建新的向量空间，并用 $\otimes$ 符号表示。</span><span class="sxs-lookup"><span data-stu-id="25048-139">Instead, you use a **tensor product**, which is a related operation that creates a new vector space from individual vector spaces, and is represented by the $\otimes$ symbol.</span></span> <span data-ttu-id="25048-140">例如，计算两个量子比特的状态的张量积 $\begin{bmatrix} a \\\\  b \end{bmatrix}$ and $\begin{bmatrix} c \\\\  d \end{bmatrix}$</span><span class="sxs-lookup"><span data-stu-id="25048-140">For example, the tensor product of two qubit states $\begin{bmatrix} a \\\\  b \end{bmatrix}$ and $\begin{bmatrix} c \\\\  d \end{bmatrix}$ is calculated</span></span>

<span data-ttu-id="25048-141">$$ \begin{bmatrix} a \\\\  b \end{bmatrix} \otimes \begin{bmatrix} c \\\\  d \end{bmatrix} =\begin{bmatrix} a \begin{bmatrix} c \\\\  d \end{bmatrix} \\\\ b \begin{bmatrix}c \\\\  d \end{bmatrix} \end{bmatrix} = \begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="25048-141">$$ \begin{bmatrix} a \\\\  b \end{bmatrix} \otimes \begin{bmatrix} c \\\\  d \end{bmatrix} =\begin{bmatrix} a \begin{bmatrix} c \\\\  d \end{bmatrix} \\\\ b \begin{bmatrix}c \\\\  d \end{bmatrix} \end{bmatrix} = \begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}.</span></span> $$

<span data-ttu-id="25048-142">结果是一个四维矩阵，其中每个元素都代表一个概率。</span><span class="sxs-lookup"><span data-stu-id="25048-142">The result is a four-dimensional matrix, with each element representing a probability.</span></span> <span data-ttu-id="25048-143">例如，$ac$ 是两个量子比特坍缩为 0 和 0 的概率，$ad$ 是坍缩为 0 和 1 的概率，依此类推。</span><span class="sxs-lookup"><span data-stu-id="25048-143">For example, $ac$ is the probability of the two qubits collapsing to 0 and 0, $ad$ is the probability of 0 and 1, and so on.</span></span> 

<span data-ttu-id="25048-144">就像单个量子比特的状态 $\begin{bmatrix} a \\\\  b \end{bmatrix}$ 必须满足要求 $|a|^2 + |b|^2 = 1$ 才能表示量子状态一样，两个量子比特的状态 $\begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}$ 也必须满足要求 $|ac|^2 + |ad|^2 + |bc|^2+ |bd|^2 = 1$。</span><span class="sxs-lookup"><span data-stu-id="25048-144">Just as a single qubit state $\begin{bmatrix} a \\\\  b \end{bmatrix}$ must meet the requirement that $|a|^2 + |b|^2 = 1$ in order to represent a quantum state, a two-qubit state $\begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}$ must meet the requirement that $|ac|^2 + |ad|^2 + |bc|^2+ |bd|^2 = 1$.</span></span>

## <a name="summary"></a><span data-ttu-id="25048-145">总结</span><span class="sxs-lookup"><span data-stu-id="25048-145">Summary</span></span>

<span data-ttu-id="25048-146">线性代数是用于描述量子计算和量子物理学的标准语言。</span><span class="sxs-lookup"><span data-stu-id="25048-146">Linear algebra is the standard language for describing quantum computing and quantum physics.</span></span> <span data-ttu-id="25048-147">虽然 Microsoft Quantum 开发工具包附带的[库](xref:microsoft.quantum.libraries)将有助于你运行高级量子算法，而无需深入研究基础数学，但了解基础知识将有助于你快速入门，并为你提供坚实的基础。</span><span class="sxs-lookup"><span data-stu-id="25048-147">Even though the [libraries](xref:microsoft.quantum.libraries) included with the Microsoft Quantum Development Kit will help you run advanced quantum algorithms without diving into the underlying math, understanding the basics will help you get started quickly and provide a solid foundation to build on.</span></span>

## <a name="next-steps"></a><span data-ttu-id="25048-148">后续步骤</span><span class="sxs-lookup"><span data-stu-id="25048-148">Next steps</span></span>

[<span data-ttu-id="25048-149">安装 QDK</span><span class="sxs-lookup"><span data-stu-id="25048-149">Install the QDK</span></span>](xref:microsoft.quantum.install)
