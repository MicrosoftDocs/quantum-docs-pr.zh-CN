---
title: 如何使用 Q# 学习量子计算？
description: ''
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: article
uid: microsoft.quantum.overview.learn
ms.openlocfilehash: 53682ae8ab9cb31fa0de68832cb3574aa4e30216
ms.sourcegitcommit: edcf15044d7bdf4f8b21fb8f6af4bde475eb13a0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2019
ms.locfileid: "73529959"
---
# <a name="how-to-learn-quantum-computing"></a><span data-ttu-id="31fbe-102">如何学习量子计算？</span><span class="sxs-lookup"><span data-stu-id="31fbe-102">How to learn quantum computing?</span></span>

<span data-ttu-id="31fbe-103">获取有关学习量子计算和编写第一个程序的指导。</span><span class="sxs-lookup"><span data-stu-id="31fbe-103">Get guidance for learning about quantum computing and writing your first programs.</span></span> <span data-ttu-id="31fbe-104">本指南不全面，但却是一个不错的开端。</span><span class="sxs-lookup"><span data-stu-id="31fbe-104">This guide isn't exhaustive, but rather a good place to start.</span></span>

## <a name="getting-started-overview"></a><span data-ttu-id="31fbe-105">入门概述</span><span class="sxs-lookup"><span data-stu-id="31fbe-105">Getting Started overview</span></span>

<span data-ttu-id="31fbe-106">[Microsoft Quantum 开发工具包入门](xref:microsoft.quantum.welcome)概述了使用 Q# 进行的量子计算，其中的教程介绍了编写第一个 Q# 程序的方法、入门指南，并介绍了如何通过 Q# 量子库来开发量子程序。</span><span class="sxs-lookup"><span data-stu-id="31fbe-106">[Get started with the Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome) provides a high-level overview of quantum computing with Q#, including tutorials for writing your first Q# program, getting started guides and introduction to the Q# quantum libraries for developing quantum programs.</span></span>

## <a name="learning-the-basics-what-do-you-need-to-know"></a><span data-ttu-id="31fbe-107">学习基础知识：需要知道的事情</span><span class="sxs-lookup"><span data-stu-id="31fbe-107">Learning the basics: what do you need to know?</span></span>

<span data-ttu-id="31fbe-108">你无需知道量子物理学便可学习 Q# 和量子计算，或开始编写量子应用程序。</span><span class="sxs-lookup"><span data-stu-id="31fbe-108">You don’t need to know quantum physics to learn about Q# and quantum computing or start writing quantum applications.</span></span>

<span data-ttu-id="31fbe-109">这些概念将帮助你了解开始量子程序编码所需的基础知识。</span><span class="sxs-lookup"><span data-stu-id="31fbe-109">These concepts will give you a good introduction to the fundamental knowledge you need to start coding quantum programs.</span></span>  

* <span data-ttu-id="31fbe-110">[基本量子力学](xref:microsoft.quantum.concepts.intro)：正如我们刚才所说，你无需知道量子物理学便可以开始编码（这是真的！）。</span><span class="sxs-lookup"><span data-stu-id="31fbe-110">[Basic quantum mechanics](xref:microsoft.quantum.concepts.intro): We just said that you don’t need to know quantum physics to start coding (and it’s true!).</span></span> <span data-ttu-id="31fbe-111">但一些基本的量子力学概念及其数学表示法有助于了解量子程序。</span><span class="sxs-lookup"><span data-stu-id="31fbe-111">But some basic concepts of quantum mechanics and its mathematical notation will be helpful to understand quantum programming.</span></span>

* <span data-ttu-id="31fbe-112">**线性代数（向量和矩阵）** ：在量子计算中，量子状态由向量表示，而量子运算则是应用于这些向量的线性转换。</span><span class="sxs-lookup"><span data-stu-id="31fbe-112">**Linear algebra (vectors and matrices)**: In quantum computing, quantum states are represented by vectors, with quantum operations being linear transformations applied to these vectors.</span></span>  <span data-ttu-id="31fbe-113">这是[有关线性代数的 Jupyter 笔记本教程](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra)。</span><span class="sxs-lookup"><span data-stu-id="31fbe-113">Here is a [Jupyter notebook tutorial on Linear Algebra](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra).</span></span>  <span data-ttu-id="31fbe-114">也可在有关[矢量和矩阵](xref:microsoft.quantum.concepts.vectors)的概念指南中详细了解线性代数。</span><span class="sxs-lookup"><span data-stu-id="31fbe-114">You can also read more about linear algebra in our concept guide about [vectors and matrices](xref:microsoft.quantum.concepts.vectors).</span></span>

* <span data-ttu-id="31fbe-115">**复杂算术**：量子状态向量的系数为复数。</span><span class="sxs-lookup"><span data-stu-id="31fbe-115">**Complex arithmetic**: The coefficients of quantum state vectors are complex numbers.</span></span> <span data-ttu-id="31fbe-116">即使没有它们，你也可以理解某些基本的量子计算概念，但如果想要深入了解，则需要将它们合并到量子工具包中。</span><span class="sxs-lookup"><span data-stu-id="31fbe-116">You can understand some basic quantum computing concepts without them, but you won't get far before you need to incorporate them into your quantum toolkit.</span></span>  <span data-ttu-id="31fbe-117">这是[有关复杂算术的 Jupyter 笔记本教程](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic)，介绍了处理量子计算所需的一些数学背景。</span><span class="sxs-lookup"><span data-stu-id="31fbe-117">Here is a [Jupyter notebook tutorial on complex arithmetic](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic) that explains some of the mathematical background required to work with quantum computing.</span></span> 

<span data-ttu-id="31fbe-118">掌握基础知识后，便可以学习如何编写量子程序了。</span><span class="sxs-lookup"><span data-stu-id="31fbe-118">Now that you have the basics, you're ready to start learning how to write quantum programs.</span></span>  <span data-ttu-id="31fbe-119">可通过多种方式来继续操作：</span><span class="sxs-lookup"><span data-stu-id="31fbe-119">There are many ways to proceed:</span></span>

## <a name="do-the-quantum-katas"></a><span data-ttu-id="31fbe-120">完成 Quantum Katas</span><span class="sxs-lookup"><span data-stu-id="31fbe-120">Do the Quantum Katas</span></span>

<span data-ttu-id="31fbe-121">[Quantum Katas](xref:microsoft.quantum.overview.katas) 是自定进度的开放源代码教程系列，旨在同时教授量子计算的元素和 Q# 编程。</span><span class="sxs-lookup"><span data-stu-id="31fbe-121">The [Quantum Katas](xref:microsoft.quantum.overview.katas) are our open source series of self-paced tutorials aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span>  <span data-ttu-id="31fbe-122">每个 kata 都参考了更多的学习资料，你可以通过这些资料学习成功完成 kata 所需的量子计算概念。</span><span class="sxs-lookup"><span data-stu-id="31fbe-122">Each kata references additional learning materials you can use to learn the quantum computing concepts needed to successfully complete the katas.</span></span>  

## <a name="dive-into-the-theory"></a><span data-ttu-id="31fbe-123">深入探讨理论</span><span class="sxs-lookup"><span data-stu-id="31fbe-123">Dive into the theory</span></span>

<span data-ttu-id="31fbe-124">你可能想要深入了解量子力学和量子计算的理论。</span><span class="sxs-lookup"><span data-stu-id="31fbe-124">Maybe you want to take a deeper look into the theory of quantum mechanics and quantum computing.</span></span> <span data-ttu-id="31fbe-125">以下是一系列有用的资料：</span><span class="sxs-lookup"><span data-stu-id="31fbe-125">Here you have a list of useful material:</span></span>

* <span data-ttu-id="31fbe-126">请从我们的[量子计算概念](xref:microsoft.quantum.concepts.intro)指南开始，其中概述了量子计算的基本概念。</span><span class="sxs-lookup"><span data-stu-id="31fbe-126">Start with our guide to [quantum computing concepts](xref:microsoft.quantum.concepts.intro), a compilation of basic concepts for quantum computing.</span></span>
* <span data-ttu-id="31fbe-127">《学习如何使用 Python 和 Q# 执行量子计算》（Sarah C. Kaiser 和 Christopher E. Granade）为几乎不具有量子力学经验但有一些编程背景的人提供了精彩的介绍  。</span><span class="sxs-lookup"><span data-stu-id="31fbe-127">_Learn Quantum Computing with Python and Q#_ (Sarah C. Kaiser and Christopher E. Granade) provides an excellent introduction for people who have little to no experience with quantum mechanics, but some programming background.</span></span>
* <span data-ttu-id="31fbe-128">《量子计算和量子信息》（Michael A. Nielsen、Isaac L. Chuang）中的内容在量子计算领域引用最多，被奉为圭臬  。</span><span class="sxs-lookup"><span data-stu-id="31fbe-128">_Quantum Computation and Quantum Information_ (Michael A. Nielsen, Isaac L. Chuang) is the most cited text in the field of quantum computation and is regarded as the standard text on the subject.</span></span> <span data-ttu-id="31fbe-129">本书假设你拥有最少的量子力学和计算机科学经验。</span><span class="sxs-lookup"><span data-stu-id="31fbe-129">The book assumes minimal prior experience with quantum mechanics and computer science.</span></span> <span data-ttu-id="31fbe-130">对于想要细致了解该主题以及正在寻找相关资料以了解高级概念的读者来说，本书是一个不错的选择。</span><span class="sxs-lookup"><span data-stu-id="31fbe-130">It is an excellent choice for readers who want a rigorous introduction to the topic as well as readers who are looking for references for advanced concepts.</span></span>
* <span data-ttu-id="31fbe-131">MIT OpenCourseWare 有一个优秀的[联机课程](https://www.youtube.com/watch?v=lZ3bPUKo5zc&list=PLUl4u3cNGP61-9PEhRognw5vryrSEVLPr)，由 Allan Adams 讲授量子力学的基本知识。</span><span class="sxs-lookup"><span data-stu-id="31fbe-131">MIT OpenCourseWare has an excellent [online course](https://www.youtube.com/watch?v=lZ3bPUKo5zc&list=PLUl4u3cNGP61-9PEhRognw5vryrSEVLPr) imparted by Allan Adams for learning the basics of quantum mechanics.</span></span> <span data-ttu-id="31fbe-132">非常适合想要更好地了解基础物理学的开发者。</span><span class="sxs-lookup"><span data-stu-id="31fbe-132">Perfect for developers who want a better understanding of the underlying physics.</span></span>

## <a name="join-the-quantum-community"></a><span data-ttu-id="31fbe-133">加入量子社区</span><span class="sxs-lookup"><span data-stu-id="31fbe-133">Join the quantum community</span></span>

<span data-ttu-id="31fbe-134">你不是一个人在孤军奋战，有一大群业余爱好者和专家都愿意为你提供帮助。</span><span class="sxs-lookup"><span data-stu-id="31fbe-134">You don’t have to learn this alone, there is a large community of amateurs and experts alike who are willing to help you.</span></span> <span data-ttu-id="31fbe-135">不要害怕提问！</span><span class="sxs-lookup"><span data-stu-id="31fbe-135">Don’t be afraid to ask!</span></span>

* <span data-ttu-id="31fbe-136">如果你对 Q# 或量子计算有任何疑问，请随时查看量子计算 StackExchange 网站。</span><span class="sxs-lookup"><span data-stu-id="31fbe-136">If you have any questions about Q# or quantum computing don’t hesitate and take a look at the Quantum Computing StackExchange site.</span></span> <span data-ttu-id="31fbe-137">如果找不到自己特定问题的答案，可以提出一个新问题。</span><span class="sxs-lookup"><span data-stu-id="31fbe-137">If you don’t find your specific question, you can always ask a new one.</span></span> 
* <span data-ttu-id="31fbe-138">请参阅 [Q# 博客](https://devblogs.microsoft.com/qsharp/)和 [Microsoft Quantum 博客](https://cloudblogs.microsoft.com/quantum/)，随时了解有关 Q# 的最新新闻和资源。</span><span class="sxs-lookup"><span data-stu-id="31fbe-138">Check out [Q# blog](https://devblogs.microsoft.com/qsharp/) and [Microsoft Quantum Blog](https://cloudblogs.microsoft.com/quantum/) to stay up-to-date with the latest news and resources about Q#.</span></span>
* <span data-ttu-id="31fbe-139">请查看 [Q# 社区](https://qsharp.community/)和[出色 Q#](https://project-awesome.org/ebraminio/awesome-qsharp)，查找更多资源和资料。</span><span class="sxs-lookup"><span data-stu-id="31fbe-139">Check [Q# Community](https://qsharp.community/) and [Awesome Q#](https://project-awesome.org/ebraminio/awesome-qsharp) to look for more resources and material.</span></span>

 <span data-ttu-id="31fbe-140">若要教授有关量子计算的课程，可访问 [Microsoft Quantum Network](https://info.microsoft.com/LearnMoreAboutMicrosoftQuantumNetwork.html)（Microsoft 量子网络），以便获取课程帮助。</span><span class="sxs-lookup"><span data-stu-id="31fbe-140">If you’re looking to teach a course on quantum computing, the [Microsoft Quantum Network](https://info.microsoft.com/LearnMoreAboutMicrosoftQuantumNetwork.html) can help provide curriculum assistance.</span></span>  

