---
title: 量子计算机有何用途？
description: 了解量子计算的影响，从新颖的量子算法到在经典计算机上运行的量子启发算法。
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: article
uid: microsoft.quantum.overview.computers
ms.openlocfilehash: d4be970c635ca090e8dcb1b58d5c840eebd4d110
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443828"
---
# <a name="what-can-a-quantum-computer-do"></a><span data-ttu-id="ae56b-103">量子计算机有何用途？</span><span class="sxs-lookup"><span data-stu-id="ae56b-103">What can a quantum computer do?</span></span>

<span data-ttu-id="ae56b-104">使用量子计算机能完成经典计算机无法完成的哪些操作？</span><span class="sxs-lookup"><span data-stu-id="ae56b-104">What we can do with a quantum computer that can't be done with a classical one?</span></span>

<span data-ttu-id="ae56b-105">解决世界上一些最具挑战性的问题，在这种情况下，使用当前计算机寻找一个解决方案将会耗费数十亿年，但量子计算机可以在几天、几小时甚至几分钟就完成。</span><span class="sxs-lookup"><span data-stu-id="ae56b-105">To solve some of the world's most challenging problems, where finding a solution would take current computers billions of years, a quantum computer could do so in days, hours, or even minutes.</span></span> <span data-ttu-id="ae56b-106">研究人员通过量子计算可以开发新的催化剂和材料，提高医学水平，加速人工智能的进步，并回答有关世界起源的基本问题。</span><span class="sxs-lookup"><span data-stu-id="ae56b-106">Quantum computing will enable researchers to develop new catalysts and materials, improve medicines, accelerate advances in artificial intelligence, and answer fundamental questions about the origins of our universe.</span></span>

## <a name="quantum-simulation"></a><span data-ttu-id="ae56b-107">量子模拟</span><span class="sxs-lookup"><span data-stu-id="ae56b-107">Quantum simulation</span></span>

<span data-ttu-id="ae56b-108">使用量子程序对量子系统本身进行建模具有巨大的潜力，其解锁的见解会导致跨行业创新。</span><span class="sxs-lookup"><span data-stu-id="ae56b-108">Using quantum programs to model quantum systems themselves has vast potential for unlocking insights leading to innovations across many industries.</span></span> <span data-ttu-id="ae56b-109">光合作用、超导体和复杂分子是量子系统的示例，它们可以使用量子程序进行模拟。</span><span class="sxs-lookup"><span data-stu-id="ae56b-109">Photosynthesis, superconductors, and complex molecules are examples of quantum systems that can be simulated using quantum programs.</span></span>

<span data-ttu-id="ae56b-110">模拟根据量子力学定律运行的微观系统的计算成本高昂。</span><span class="sxs-lookup"><span data-stu-id="ae56b-110">Simulating microscopic systems that behave according to the laws of quantum mechanics is computationally expensive.</span></span> <span data-ttu-id="ae56b-111">我们需要考虑所有可能叠加的状态，并且状态数随系统的大小呈指数增长。</span><span class="sxs-lookup"><span data-stu-id="ae56b-111">We need to take into account all the possible states that can be in superposition and the number of states grows exponentially with the size of the system.</span></span> <span data-ttu-id="ae56b-112">在量子计算机中，我们不需要为系统的所有状态建模。</span><span class="sxs-lookup"><span data-stu-id="ae56b-112">In a quantum computer, we don’t need to model all of the states of the system.</span></span> <span data-ttu-id="ae56b-113">相反，我们会在计算机本身的量子位中嵌入要模拟的系统的量子状态，并使用一组特定的量子门来运行模拟。</span><span class="sxs-lookup"><span data-stu-id="ae56b-113">Instead, we embed the quantum state of the system that we want to simulate in the qubits of the computer itself, and run the simulation with a specific set of quantum gates.</span></span> <span data-ttu-id="ae56b-114">换句话说，我们使用量子计算机来模拟量子系统。</span><span class="sxs-lookup"><span data-stu-id="ae56b-114">In other words, we use a quantum computer to simulate a quantum system.</span></span>

<span data-ttu-id="ae56b-115">化学分子是量子系统，因此可通过这种方式进行分析。</span><span class="sxs-lookup"><span data-stu-id="ae56b-115">Chemical molecules are quantum systems and therefore can be analyzed in this way.</span></span> <span data-ttu-id="ae56b-116">“固氮酶”就是这样一种特殊的化学物质，通过更好地了解其属性，可以减少当前肥料的能源消耗和温室气体排放  。</span><span class="sxs-lookup"><span data-stu-id="ae56b-116">One such specific chemical is the _nitrogenase_ enzyme, which, with a better understanding of its properties, could have the potential to reduce the energy consumption and greenhouse gas emission of current fertilizers.</span></span>

## <a name="cryptography"></a><span data-ttu-id="ae56b-117">加密</span><span class="sxs-lookup"><span data-stu-id="ae56b-117">Cryptography</span></span>

<span data-ttu-id="ae56b-118">也许量子计算机最著名的应用是在加密领域，Peter Shor 在 1994 年证明了一台可缩放的量子计算机可以破解所有广泛使用的加密技术。</span><span class="sxs-lookup"><span data-stu-id="ae56b-118">Perhaps the most famous application of quantum computers is in cryptography, where Peter Shor showed in 1994 that a scalable quantum computer can break every widely used encryption technique.</span></span>  <span data-ttu-id="ae56b-119">经典加密依赖于这样一种信念：很难对大数字进行运算（例如将大数字因式分解为两个质数）。</span><span class="sxs-lookup"><span data-stu-id="ae56b-119">Classical cryptography relies on the intractability of operations on large numbers, such as factorization of large numbers into two prime numbers.</span></span>  <span data-ttu-id="ae56b-120">从理论上讲，量子计算可以使这种运算变得很简单（使用 Shor 算法）。</span><span class="sxs-lookup"><span data-stu-id="ae56b-120">Quantum computing makes these operations theoretically tractable (via Shor's algorithm).</span></span> <span data-ttu-id="ae56b-121">虽然在当前的量子硬件规模下无法实现此算法，但它促成了抗量子算法的开发，可确保满足未来的数据安全要求，包括用于加密和加密密钥分发的新颖量子算法。</span><span class="sxs-lookup"><span data-stu-id="ae56b-121">Whilst implementation of this algorithm is not physically possible with the current scale of quantum hardware, it has spawned development of quantum resistant algorithms to future-proof data security, including novel quantum algorithms for encryption and cryptographic key distribution.</span></span>  <span data-ttu-id="ae56b-122">Microsoft 在后量子加密领域有世界领先的团队，在开发抗量子算法方面有足够的安全措施。</span><span class="sxs-lookup"><span data-stu-id="ae56b-122">Here at Microsoft, we have the world's leading team in post-quantum cryptography and security developing quantum-resistant algorithms.</span></span> 

## <a name="optimization"></a><span data-ttu-id="ae56b-123">优化</span><span class="sxs-lookup"><span data-stu-id="ae56b-123">Optimization</span></span>

<span data-ttu-id="ae56b-124">优化是指在高维空间进行大型搜索，以便获取真正优秀的解决方案，尽量降低给定成本函数得出的成本。</span><span class="sxs-lookup"><span data-stu-id="ae56b-124">Optimization is the task of performing a large search over a high-dimensional space for a really good solution that minimizes a given cost function.</span></span>   <span data-ttu-id="ae56b-125">在量子计算机上，我们可以加快优化算法的速度，找出使用其他方法无法找出的解决方案。</span><span class="sxs-lookup"><span data-stu-id="ae56b-125">On a quantum computer, we can speed up optimization algorithms, enabling finding solutions that otherwise were not possible.</span></span> <span data-ttu-id="ae56b-126">应用包括：运输和物流、医疗保健、诊断以及材料科学。</span><span class="sxs-lookup"><span data-stu-id="ae56b-126">Applications range from transporation and logistics, healthcare, diagnositics and material science.</span></span> <span data-ttu-id="ae56b-127">可能会在提升效率方面对这些行业造成深远影响。</span><span class="sxs-lookup"><span data-stu-id="ae56b-127">There can be a profound impact on how these industries can become more efficient.</span></span> 

<span data-ttu-id="ae56b-128">通过量子计算进行优化，我们就可以围绕运输和物流进行创新，所用方式是使用当今的经典系统无法实现的。</span><span class="sxs-lookup"><span data-stu-id="ae56b-128">Optimization with quantum computing allows us to innovate around transportation and logistics in a way that is not possible with today’s classical systems.</span></span> <span data-ttu-id="ae56b-129">优化交通流量可以减少拥堵。</span><span class="sxs-lookup"><span data-stu-id="ae56b-129">Optimizing traffic flow can reduce congestion.</span></span>  <span data-ttu-id="ae56b-130">除了规划路线，还可以进行登机门分配、包裹递送、作业计划，等等。</span><span class="sxs-lookup"><span data-stu-id="ae56b-130">In addition to route planning, there is airplane gate assignment, package delivery, job scheduling and more.</span></span>  <span data-ttu-id="ae56b-131">随着材料科学的突破，将会有新型能源、更大容量的电池、更轻且更强的材料。</span><span class="sxs-lookup"><span data-stu-id="ae56b-131">With breakthroughs in materials science, there will be new forms of energy, batteries with greater capacity, lighter and stronger materials.</span></span> 

## <a name="machine-learning"></a><span data-ttu-id="ae56b-132">机器学习</span><span class="sxs-lookup"><span data-stu-id="ae56b-132">Machine learning</span></span>

<span data-ttu-id="ae56b-133">经典计算的许多数字计算主要包含解线性方程组。</span><span class="sxs-lookup"><span data-stu-id="ae56b-133">A great number of numerical calculations on classical computing consist mainly in solving linear systems of equations.</span></span> <span data-ttu-id="ae56b-134">在机器学习领域中尤其如此，其中大部分计算成本都用于计算巨大矩阵的逆矩阵。</span><span class="sxs-lookup"><span data-stu-id="ae56b-134">This is especially true in the field of machine learning where most of the computation cost goes into calculating the inverse of huge matrices.</span></span>

<span data-ttu-id="ae56b-135">幸运的是，有一种量子算法可让我们快速完成方程组的求解，这种求解速度比经典计算快指数倍。</span><span class="sxs-lookup"><span data-stu-id="ae56b-135">Fortunately, there exists a quantum algorithm that allows us to approximately solve the system exponentially faster than a classical computer.</span></span> <span data-ttu-id="ae56b-136">这显著加快了需要解线性方程组的每个问题的解决速度。</span><span class="sxs-lookup"><span data-stu-id="ae56b-136">This opens the door to great speedups in every problem that needs the solution to linear systems of equations.</span></span>

<span data-ttu-id="ae56b-137">解决这些领域的问题将有助于应对能源危机、气候变化、粮食短缺以及精准医疗的问题。</span><span class="sxs-lookup"><span data-stu-id="ae56b-137">Solutions to problems in these areas will help address the energy crisis, climate change, food scarcity, and personal and precise medical diagnosis.</span></span>

## <a name="quantum-inspired-computing"></a><span data-ttu-id="ae56b-138">量子启发计算</span><span class="sxs-lookup"><span data-stu-id="ae56b-138">Quantum-inspired computing</span></span>

<span data-ttu-id="ae56b-139">量子启发算法通过经典软件实现，但使用量子原则来提高速度和准确性。</span><span class="sxs-lookup"><span data-stu-id="ae56b-139">Quantum-inspired algorithms are implemented with classical software, but use quantum principles for increased speed and accuracy.</span></span>

<span data-ttu-id="ae56b-140">量子启发算法已应用于医学研究。</span><span class="sxs-lookup"><span data-stu-id="ae56b-140">Quantum-inspired algorithms are being applied to medical research.</span></span> <span data-ttu-id="ae56b-141">例如，用于提高磁共振成象 (MRI) 扫描的准确性。</span><span class="sxs-lookup"><span data-stu-id="ae56b-141">For example, to improve the accuracy of Magnetic Resonance Imaging (MRI) scans.</span></span> <span data-ttu-id="ae56b-142">量子启发计算用于优化 MRI 机器的配置，以鉴别具体疾病。</span><span class="sxs-lookup"><span data-stu-id="ae56b-142">Quantum-inspired computing is being used to optimize the configuration of the MRI machines for identification of specific diseases.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ae56b-143">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ae56b-143">Next steps</span></span>

* [<span data-ttu-id="ae56b-144">为什么应该学习量子计算？</span><span class="sxs-lookup"><span data-stu-id="ae56b-144">Why should I learn quantum computing?</span></span>](xref:microsoft.quantum.overview.why)
* [<span data-ttu-id="ae56b-145">Microsoft Quantum 开发工具包入门</span><span class="sxs-lookup"><span data-stu-id="ae56b-145">Get started with the Microsoft Quantum Development Kit</span></span>](xref:microsoft.quantum.welcome)
