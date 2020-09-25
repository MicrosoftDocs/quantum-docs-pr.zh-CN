---
title: 量子计算简介
description: 了解量子计算是什么、量子计算机可以做些什么，以及如何学习量子计算。
author: bradben
ms.author: v-benbra
ms.date: 05/05/2020
ms.topic: overview
uid: microsoft.quantum.overview.introduction
no-loc:
- Q#
- $$v
ms.openlocfilehash: c3374e9fae07cc38761e404be7819e7cf699ce2b
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834510"
---
# <a name="introduction-to-quantum-computing-and-the-quantum-development-kit"></a><span data-ttu-id="16dad-103">量子计算和 Quantum 开发工具包简介</span><span class="sxs-lookup"><span data-stu-id="16dad-103">Introduction to quantum computing and the Quantum Development Kit</span></span>

<span data-ttu-id="16dad-104">Microsoft Quantum 开发工具包 (QDK) 是一组开放源代码工具，旨在帮助开发人员学习量子算法和编写量子程序。</span><span class="sxs-lookup"><span data-stu-id="16dad-104">The Microsoft Quantum Development Kit (QDK) is a set of open-source tools designed to help developers learn quantum algorithms and write quantum programs.</span></span> <span data-ttu-id="16dad-105">量子计算有望解决我们这个星球上在以下领域遇到的一些最大的挑战 - 环境、农业、医疗保健、能源、气候、材料科学领域，以及我们尚未遇到的其他领域方面的问题。</span><span class="sxs-lookup"><span data-stu-id="16dad-105">Quantum computing holds the promise to solve some of our planet's biggest challenges - in the areas of environment, agriculture, health, energy, climate, materials science, and others we haven't encountered yet.</span></span>  

<span data-ttu-id="16dad-106">对于其中的一些问题，即使是最强大的计算机也束手无策。</span><span class="sxs-lookup"><span data-stu-id="16dad-106">For some of these problems, even our most powerful computers run into problems.</span></span> <span data-ttu-id="16dad-107">尽管量子技术才刚刚开始影响计算领域，但它的影响将会变得深远，并改变我们对计算的看法。</span><span class="sxs-lookup"><span data-stu-id="16dad-107">While quantum technology is just beginning to impact the computing world, it could be far-reaching and change the way we think about computing.</span></span>

## <a name="what-is-quantum-computing"></a><span data-ttu-id="16dad-108">什么是量子计算？</span><span class="sxs-lookup"><span data-stu-id="16dad-108">What is quantum computing?</span></span>

<span data-ttu-id="16dad-109">在现代用法中，量子一词是指任何物理属性中最小的离散单位，通常是指原子或次原子粒子的属性。</span><span class="sxs-lookup"><span data-stu-id="16dad-109">In modern usage, the word quantum means the smallest possible discrete unit of any physical property, usually referring to properties of atomic or subatomic particles.</span></span> <span data-ttu-id="16dad-110">量子计算机使用实际的量子粒子、人工原子或量子粒子的集合属性作为处理单元，并且是大型、复杂且昂贵的设备。</span><span class="sxs-lookup"><span data-stu-id="16dad-110">Quantum computers use actual quantum particles, artificial atoms, or collective properties of quantum particles as processing units, and are large, complex, and expensive devices.</span></span>

<span data-ttu-id="16dad-111">通过利用量子物理学的独特行为并将其应用于计算，量子计算机利用叠加、纠缠和量子干涉等量子物理学行为，为传统的编程方法引入了新概念。</span><span class="sxs-lookup"><span data-stu-id="16dad-111">Harnessing the unique behavior of quantum physics and applying it to computing, quantum computers introduce new concepts to traditional programming methods, making use of quantum physics behaviors such as superposition, entanglement, and quantum interference.</span></span>

## <a name="what-can-a-quantum-computer-do"></a><span data-ttu-id="16dad-112">量子计算机有何用途？</span><span class="sxs-lookup"><span data-stu-id="16dad-112">What can a quantum computer do?</span></span>

<span data-ttu-id="16dad-113">量子计算机并不是可以更快地执行所有操作的超级计算机，但是量子计算机在某些领域表现得非常出色。</span><span class="sxs-lookup"><span data-stu-id="16dad-113">A quantum computer isn't a supercomputer that can do everything faster, but there are a few areas where quantum computers do exceptionally well.</span></span>

- [<span data-ttu-id="16dad-114">量子模拟</span><span class="sxs-lookup"><span data-stu-id="16dad-114">Quantum simulation</span></span>](xref:microsoft.quantum.overview.introduction#quantum-simulation)
- [<span data-ttu-id="16dad-115">加密</span><span class="sxs-lookup"><span data-stu-id="16dad-115">Cryptography</span></span>](xref:microsoft.quantum.overview.introduction#cryptography-and-shors-algorithm)
- [<span data-ttu-id="16dad-116">搜索</span><span class="sxs-lookup"><span data-stu-id="16dad-116">Search</span></span>](xref:microsoft.quantum.overview.introduction#search-and-grovers-algorithm)
- [<span data-ttu-id="16dad-117">优化</span><span class="sxs-lookup"><span data-stu-id="16dad-117">Optimization</span></span>](xref:microsoft.quantum.overview.introduction#quantum-inspired-computing-and-optimization)
- [<span data-ttu-id="16dad-118">机器学习</span><span class="sxs-lookup"><span data-stu-id="16dad-118">Machine learning</span></span>](xref:microsoft.quantum.overview.introduction#quantum-machine-learning)

## <a name="quantum-simulation"></a><span data-ttu-id="16dad-119">量子模拟</span><span class="sxs-lookup"><span data-stu-id="16dad-119">Quantum simulation</span></span>

<span data-ttu-id="16dad-120">由于量子计算机在计算中使用量子现象，因此非常适合用于对其他量子系统进行建模。</span><span class="sxs-lookup"><span data-stu-id="16dad-120">Since quantum computers use quantum phenomena in computation, they are well suited for modeling other quantum systems.</span></span> <span data-ttu-id="16dad-121">光合作用、超导性和复杂的分子形成都是量子程序可以模拟的量子机制的例子。</span><span class="sxs-lookup"><span data-stu-id="16dad-121">Photosynthesis, superconductivity, and complex molecular formations are examples of quantum mechanisms that quantum programs can simulate.</span></span>

## <a name="cryptography-and-shors-algorithm"></a><span data-ttu-id="16dad-122">密码学和秀尔算法</span><span class="sxs-lookup"><span data-stu-id="16dad-122">Cryptography and Shor’s algorithm</span></span>

<span data-ttu-id="16dad-123">1994 年，彼得·秀尔展示了一种可缩放的量子计算机，该计算机可以破解广泛使用的加密技术，例如 RSA 算法。</span><span class="sxs-lookup"><span data-stu-id="16dad-123">In 1994, Peter Shor showed that a scalable quantum computer could break widely used encryption techniques such as the RSA algorithm.</span></span> <span data-ttu-id="16dad-124">经典密码学依赖于整数分解或离散对数等问题的难处理性，其中许多问题都可以使用量子计算机更有效地得以解决。</span><span class="sxs-lookup"><span data-stu-id="16dad-124">Classical cryptography relies on the intractability of problems such as integer factorization or discrete logarithms, many of which can be solved more efficiently using quantum computers.</span></span>

## <a name="search-and-grovers-algorithm"></a><span data-ttu-id="16dad-125">搜索和 Grover 算法</span><span class="sxs-lookup"><span data-stu-id="16dad-125">Search and Grover’s algorithm</span></span>

<span data-ttu-id="16dad-126">1996 年，Lov Grover 开发了一种量子算法，该算法极大地加速了对非结构化数据搜索的解决方案，与传统算法相比，其搜索步骤更少。</span><span class="sxs-lookup"><span data-stu-id="16dad-126">In 1996, Lov Grover developed a quantum algorithm that dramatically sped up the solution to unstructured data searches, running the search in fewer steps than any classical algorithm could.</span></span>

## <a name="quantum-inspired-computing-and-optimization"></a><span data-ttu-id="16dad-127">受量子启发的计算和优化</span><span class="sxs-lookup"><span data-stu-id="16dad-127">Quantum-inspired computing and optimization</span></span>

<span data-ttu-id="16dad-128">受量子启发的算法使用量子原理来提高速度和准确性，但可在经典计算机系统上实现。</span><span class="sxs-lookup"><span data-stu-id="16dad-128">Quantum-inspired algorithms use quantum principles for increased speed and accuracy but implement on classical computer systems.</span></span> <span data-ttu-id="16dad-129">这种方法使开发人员可以利用当今的新量子技术的强大功能，而无需等待仍是新兴产业的量子硬件。</span><span class="sxs-lookup"><span data-stu-id="16dad-129">This approach allows developers to leverage the power of new quantum techniques today without waiting for quantum hardware, which is still an emerging industry.</span></span>

<span data-ttu-id="16dad-130">优化是在给定问题的预期结果和约束条件的情况下找到问题最佳解决方案的过程。</span><span class="sxs-lookup"><span data-stu-id="16dad-130">Optimization is the process of finding the best solution to a problem, given its desired outcome and constraints.</span></span> <span data-ttu-id="16dad-131">成本、质量或生产时间等因素都会影响工业和科学界做出的关键决策。</span><span class="sxs-lookup"><span data-stu-id="16dad-131">Factors such as cost, quality, or production time all play into critical decisions made by industry and science.</span></span> <span data-ttu-id="16dad-132">目前在经典计算机上运行的受量子启发的优化算法可以找到迄今为止尚无法实现的解决方案。</span><span class="sxs-lookup"><span data-stu-id="16dad-132">Quantum-inspired optimization algorithms running on today's classical computers can find solutions that up to now have not been possible.</span></span> <span data-ttu-id="16dad-133">除了优化交通流量以减少拥堵外，还提供飞机登机门分配、包裹递送、作业计划等。</span><span class="sxs-lookup"><span data-stu-id="16dad-133">In addition to optimizing traffic flow to reduce congestion, there is airplane gate assignment, package delivery, job scheduling and more.</span></span> <span data-ttu-id="16dad-134">随着材料科学的突破，将出现新型能源、更大容量的电池以及更轻便且更耐用的材料。</span><span class="sxs-lookup"><span data-stu-id="16dad-134">With breakthroughs in materials science, there will be new forms of energy, batteries with larger capacity, and lighter and more durable materials.</span></span>

> [!NOTE]
> <span data-ttu-id="16dad-135">详细了解[材料科学](https://cloudblogs.microsoft.com/quantum/2020/01/21/oti-lumionics-accelerating-materials-design-microsoft-azure-quantum/)、[风险管理](https://cloudblogs.microsoft.com/quantum/2019/05/22/microsoft-quantum-collaborates-with-willis-towers-watson-to-transform-risk-management-solutions/)和[医学](https://blogs.microsoft.com/blog/2018/05/18/microsoft-quantum-helps-case-western-reserve-university-advance-mri-research/)领域如何使用 Microsoft 受量子启发的计算。</span><span class="sxs-lookup"><span data-stu-id="16dad-135">Read more about how Microsoft quantum-inspired computing is being used in [materials science](https://cloudblogs.microsoft.com/quantum/2020/01/21/oti-lumionics-accelerating-materials-design-microsoft-azure-quantum/), [risk management](https://cloudblogs.microsoft.com/quantum/2019/05/22/microsoft-quantum-collaborates-with-willis-towers-watson-to-transform-risk-management-solutions/), and [medicine](https://blogs.microsoft.com/blog/2018/05/18/microsoft-quantum-helps-case-western-reserve-university-advance-mri-research/).</span></span>

## <a name="quantum-machine-learning"></a><span data-ttu-id="16dad-136">量子机器学习</span><span class="sxs-lookup"><span data-stu-id="16dad-136">Quantum machine learning</span></span>

<span data-ttu-id="16dad-137">经典计算机上的机器学习正在彻底改变科学和商业领域。</span><span class="sxs-lookup"><span data-stu-id="16dad-137">Machine learning on classical computers is revolutionizing the world of science and business.</span></span> <span data-ttu-id="16dad-138">然而，训练模型带来的高计算成本阻碍了该领域的发展和范围。</span><span class="sxs-lookup"><span data-stu-id="16dad-138">However, the high computational cost of training the models hinders the development and scope of the field.</span></span> <span data-ttu-id="16dad-139">量子机器学习领域探讨了如何设计和实现可使机器学习比传统计算机运行速度更快的量子软件。</span><span class="sxs-lookup"><span data-stu-id="16dad-139">The area of quantum machine learning explores how to devise and implement quantum software that enables machine learning that runs faster than classical computers.</span></span>

<span data-ttu-id="16dad-140">Quantum 开发工具包随附[量子机器学习库](xref:microsoft.quantum.machine-learning.concepts.intro)，使你能够运行混合量子/经典机器学习试验。</span><span class="sxs-lookup"><span data-stu-id="16dad-140">The Quantum Development Kit comes with the [quantum machine learning library](xref:microsoft.quantum.machine-learning.concepts.intro) that gives you the ability to run hybrid quantum/classical machine learning experiments.</span></span> <span data-ttu-id="16dad-141">该库包括示例和教程，并提供了实现新的混合算法，即经典算法（以电路为中心的量子分类器）所需的工具，以解决监督分类问题。</span><span class="sxs-lookup"><span data-stu-id="16dad-141">The library includes samples and tutorials, and provides the necessary tools to implement a new hybrid quantum–classical algorithm, the circuit-centric quantum classifier, to solve supervised classification problems.</span></span>

## <a name="no-locq-and-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="16dad-142">Q# 和 Microsoft Quantum 开发工具包 (QDK)</span><span class="sxs-lookup"><span data-stu-id="16dad-142">Q# and the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="16dad-143">Q# 是用于开发和运行量子算法的 Microsoft 开放源代码编程语言。</span><span class="sxs-lookup"><span data-stu-id="16dad-143">Q# is Microsoft's open-source programming language for developing and running quantum algorithms.</span></span> <span data-ttu-id="16dad-144">它是 [QDK](https://docs.microsoft.com/quantum/)（一种功能完善的 Q# 开发工具包）的一部分，可与标准工具和语言一起使用，以开发可在各种环境（包括内置的状态量子模拟器）中运行的量子应用程序。</span><span class="sxs-lookup"><span data-stu-id="16dad-144">It is part of the [QDK](https://docs.microsoft.com/quantum/), a full-featured development kit for Q# that you can use with standard tools and languages to develop quantum applications that you can run in various environments, including the built-in full-state quantum simulator.</span></span>

<span data-ttu-id="16dad-145">这里提供有 Visual Studio 和 VS Code 的扩展，以及用于 Python 和 Jupyter Notebook 的包。</span><span class="sxs-lookup"><span data-stu-id="16dad-145">There are extensions for Visual Studio and VS Code, and packages for use with Python and Jupyter Notebook.</span></span>

<span data-ttu-id="16dad-146">QDK 包括一个标准库以及专门的化学库、机器学习库和数字库。</span><span class="sxs-lookup"><span data-stu-id="16dad-146">The QDK includes a standard library along with specialized chemistry, machine learning, and numerics libraries.</span></span>

<span data-ttu-id="16dad-147">该文档包括 Q# 语言指南、教程和示例代码来帮助你快速入门，还提供丰富的文章来帮助你更深入地了解量子计算概念。</span><span class="sxs-lookup"><span data-stu-id="16dad-147">The documentation includes a Q# language guide, tutorials, and sample code to get you started quickly, and rich articles to help you dive deeper into quantum computing concepts.</span></span>  

## <a name="microsoft-quantum-hardware-partners"></a><span data-ttu-id="16dad-148">Microsoft 量子硬件合作伙伴</span><span class="sxs-lookup"><span data-stu-id="16dad-148">Microsoft quantum hardware partners</span></span>

<span data-ttu-id="16dad-149">Microsoft 正在与量子硬件公司合作，为开发人员提供对量子硬件的云访问权限。</span><span class="sxs-lookup"><span data-stu-id="16dad-149">Microsoft is partnering with quantum hardware companies to provide developers with cloud access to quantum hardware.</span></span> <span data-ttu-id="16dad-150">通过利用 [Azure Quantum](https://azure.microsoft.com/services/quantum/) 平台和 Q# 语言，开发人员将能够探索量子算法，并在不同类型的量子硬件上运行其量子程序。</span><span class="sxs-lookup"><span data-stu-id="16dad-150">Leveraging the [Azure Quantum](https://azure.microsoft.com/services/quantum/) platform and the Q# language, developers will be able to explore quantum algorithms and run their quantum programs on different types of quantum hardware.</span></span>

<span data-ttu-id="16dad-151">[IonQ](https://ionq.com/news/november-4-2019-microsoft-partnership) 和 [Honeywell](https://www.honeywell.com/en-us/newsroom/news/2019/11/the-future-of-quantum-computing) 都使用捕获的基于离子的处理器并利用在电场中捕获的单个离子，而 [QCI](https://quantumcircuits.com/news-and-publications/quantum-circuits-partners-with-microsoft-on-azure-quantum) 使用超导电路。</span><span class="sxs-lookup"><span data-stu-id="16dad-151">[IonQ](https://ionq.com/news/november-4-2019-microsoft-partnership) and [Honeywell](https://www.honeywell.com/en-us/newsroom/news/2019/11/the-future-of-quantum-computing) both use **trapped ion-based** processors, utilizing individual ions trapped in an electronic field, whereas [QCI](https://quantumcircuits.com/news-and-publications/quantum-circuits-partners-with-microsoft-on-azure-quantum) uses superconducting circuits.</span></span>

## <a name="next-steps"></a><span data-ttu-id="16dad-152">后续步骤</span><span class="sxs-lookup"><span data-stu-id="16dad-152">Next steps</span></span>

<span data-ttu-id="16dad-153">[量子计算的主要概念](xref:microsoft.quantum.overview.understanding)
[快速入门](xref:microsoft.quantum.welcome)</span><span class="sxs-lookup"><span data-stu-id="16dad-153">[Key concepts for quantum computing](xref:microsoft.quantum.overview.understanding)
[Quickstarts](xref:microsoft.quantum.welcome)</span></span>