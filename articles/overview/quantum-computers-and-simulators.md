---
title: 量子计算机和量子模拟器
description: 了解有关量子硬件、量子模拟器以及量子操作工作原理的信息。
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.simulators
ms.openlocfilehash: 04f90e9f88cf17259f96532617ef6f092b56b859
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430741"
---
# <a name="quantum-computers-and-quantum-simulators"></a><span data-ttu-id="b7fa0-103">量子计算机和量子模拟器</span><span class="sxs-lookup"><span data-stu-id="b7fa0-103">Quantum computers and quantum simulators</span></span>

<span data-ttu-id="b7fa0-104">量程计算机仍处于其开发初级阶段。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-104">Quantum computers are still in the infancy of their development.</span></span> <span data-ttu-id="b7fa0-105">硬件和维护成本高昂，大多数系统都位于大学和研究实验室中。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-105">The hardware and maintenance are expensive, and most systems are located in universities and research labs.</span></span> <span data-ttu-id="b7fa0-106">不过，这项技术在不断发展，并对某些系统提供有限的公共访问。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-106">The technology is advancing, though, and limited public access to some systems is available.</span></span>

<span data-ttu-id="b7fa0-107">量子模拟器是在经典计算机上运行的软件程序，可以在预测量子比特将如何对不同操作做出反应的环境中运行和测试量子程序。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-107">Quantum simulators are software programs that run on classical computers and make it possible to run and test quantum programs in an environment that predicts how qubits will react to different operations.</span></span>

## <a name="quantum-hardware"></a><span data-ttu-id="b7fa0-108">量子硬件</span><span class="sxs-lookup"><span data-stu-id="b7fa0-108">Quantum hardware</span></span>

<span data-ttu-id="b7fa0-109">量子计算机分为三个主要部分：容纳量子比特的区域、将信号传输到量子比特的方法以及运行程序和发送指令的经典计算机。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-109">A quantum computer has three primary parts: an area that houses the qubits, a method for transferring signals to the qubits, and a classical computer to run a program and send instructions.</span></span>

- <span data-ttu-id="b7fa0-110">用于量子比特的量子材料易碎且对环境干扰高度敏感。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-110">The quantum material used for qubits is fragile and highly sensitive to environmental interferences.</span></span> <span data-ttu-id="b7fa0-111">对于某些量子比特存储方法，存储量子比特的装置保持在稍高于绝对值零的温度，以最大化其相干性。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-111">For some methods of qubit storage, the unit that houses the qubits is kept at a temperature just above absolute zero to maximize their coherence.</span></span> <span data-ttu-id="b7fa0-112">其他类型的量子比特装置使用真空室来帮助最大程度地减少振动并使量子比特保持稳定。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-112">Other types of qubit housing use a vacuum chamber to help minimize vibrations and stabilize the qubits.</span></span>  
- <span data-ttu-id="b7fa0-113">可以使用多种方法（包括微波、激光和电压）将信号发送到量子比特。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-113">Signals can be sent to the qubits using a variety of methods including microwaves, laser, and voltage.</span></span>

<span data-ttu-id="b7fa0-114">量子计算机在正确操作方面面临着诸多挑战。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-114">Quantum computers face a multitude of challenges to operate correctly.</span></span> <span data-ttu-id="b7fa0-115">量子计算机中的纠错是一项重大问题，扩大规模（增加更多量子比特）将增加错误率。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-115">Error correction in quantum computers is a significant issue, and scaling up (adding more qubits) increases the error rate.</span></span> <span data-ttu-id="b7fa0-116">由于这些限制，量子台式电脑在将来变得越来越遥远，而商业上可行的基于实验室的量子计算机会变得越来越近。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-116">Because of these limitations, a quantum PC for your desktop is far in the future, but a commercially-viable lab-based quantum computer is closer.</span></span>

## <a name="quantum-simulators"></a><span data-ttu-id="b7fa0-117">量子模拟器</span><span class="sxs-lookup"><span data-stu-id="b7fa0-117">Quantum simulators</span></span>

<span data-ttu-id="b7fa0-118">在经典计算机上运行的量子模拟器使你可以在量子系统上模拟量子算法的执行。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-118">Quantum simulators that run on classical computers allow you to simulate the execution of quantum algorithms on a quantum system.</span></span>  <span data-ttu-id="b7fa0-119">Microsoft Quantum 开发工具包 (QDK) 包含一个完整状态向量模拟器以及其他专用量子模拟器。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-119">Microsoft’s Quantum Development Kit (QDK) includes a full-state vector simulator along with other specialized quantum simulators.</span></span>

## <a name="topological-qubit"></a><span data-ttu-id="b7fa0-120">拓扑量子比特</span><span class="sxs-lookup"><span data-stu-id="b7fa0-120">Topological qubit</span></span>

<span data-ttu-id="b7fa0-121">Microsoft 正在开发基于拓扑量子位的量子计算机。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-121">Microsoft is developing a quantum computer based on topological qubits.</span></span> <span data-ttu-id="b7fa0-122">拓扑量子比特受环境变化的影响较小，因此减少了所需的外部纠错的程度。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-122">A topological qubit will be less impacted by changes in its environment, therefore reducing the degree of external error correction required.</span></span>

<span data-ttu-id="b7fa0-123">拓扑量子位具有更高的稳定性，并且不容易受到环境所影响，这意味着它们更容易伸缩，并保持更长的可靠时间。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-123">Topological qubits feature increased stability and resistance to environmental noise, which means they can more readily scale and remain reliable longer.</span></span>

## <a name="microsoft-and-quantum-hardware-partnerships"></a><span data-ttu-id="b7fa0-124">Microsoft 和量子硬件合作伙伴</span><span class="sxs-lookup"><span data-stu-id="b7fa0-124">Microsoft and quantum hardware partnerships</span></span>

<span data-ttu-id="b7fa0-125">Microsoft 正在与量子硬件制造商 IonQ、Honeywell 和 QCI 合作，以使量子计算机将来可供开发人员使用。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-125">Microsoft is partnering with quantum hardware manufacturers IonQ, Honeywell, and QCI to make quantum computers accessible to developers in the future.</span></span> <span data-ttu-id="b7fa0-126">利用 Azure Quantum 平台，开发人员将能够使用 Microsoft Quantum 开发工具包 (QDK) 和 Q# 编写量子程序并远程运行这些程序。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-126">Leveraging the Azure Quantum platform, developers will be able to use Microsoft’s Quantum Development Kit (QDK) and Q# to write quantum programs and run them remotely.</span></span>

## <a name="quantum-computations"></a><span data-ttu-id="b7fa0-127">量子计算</span><span class="sxs-lookup"><span data-stu-id="b7fa0-127">Quantum computations</span></span>

<span data-ttu-id="b7fa0-128">在量子计算机或量子模拟器上执行计算遵循以下基本流程：</span><span class="sxs-lookup"><span data-stu-id="b7fa0-128">Performing computations on a quantum computer or quantum simulator follow a basic process:</span></span>

- <span data-ttu-id="b7fa0-129">访问量子比特</span><span class="sxs-lookup"><span data-stu-id="b7fa0-129">Access the qubits</span></span>
- <span data-ttu-id="b7fa0-130">将量子比特初始化为期望状态</span><span class="sxs-lookup"><span data-stu-id="b7fa0-130">Initialize the qubits to the desired state</span></span>
- <span data-ttu-id="b7fa0-131">执行操作以转换量子比特的状态</span><span class="sxs-lookup"><span data-stu-id="b7fa0-131">Perform operations to transform the states of the qubits</span></span>
- <span data-ttu-id="b7fa0-132">测试量子比特的新状态</span><span class="sxs-lookup"><span data-stu-id="b7fa0-132">Measure the new states of the qubits</span></span>

<span data-ttu-id="b7fa0-133">使用量子操作（有时称为量子门）来完成量子比特的初始化和转换。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-133">Initializing and transforming qubits is done using **quantum operations** (sometimes called quantum gates).</span></span> <span data-ttu-id="b7fa0-134">量子操作类似于经典计算中的逻辑运算，例如 AND、OR、NOT 和 XOR。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-134">Quantum operations are similar to logic operations in classical computing, such as AND, OR, NOT, and XOR.</span></span> <span data-ttu-id="b7fa0-135">基本操作可以是将量子比特的状态从 1 翻转为 0 或纠缠一对量子比特，也可以使用一系列串行操作来影响叠加的量子比特坍缩方式的概率。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-135">An operation can be as basic as flipping a qubit's state from 1 to 0 or entangling a pair of qubits, to using multiple operations in series to affect the probability of a superposed qubit collapsing one way or the other.</span></span>

> [!NOTE] 
> <span data-ttu-id="b7fa0-136">[Q# 库](xref:microsoft.quantum.libraries)提供了内置操作，这些操作定义较低级别的量子操作的复杂组合。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-136">The [Q# libraries](xref:microsoft.quantum.libraries) provide built-in operations that define complex combinations of lower-level quantum operations.</span></span> <span data-ttu-id="b7fa0-137">可以使用库操作来转换量子比特并创建更为复杂的用户定义的操作。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-137">You can use the library operations to transform qubits and to create more complex user-defined operations.</span></span>  

<span data-ttu-id="b7fa0-138">衡量计算结果会告诉我们答案，但是对于某些量子算法，不一定是正确答案。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-138">Measuring the result of the computation tells us an answer, but for some quantum algorithms, not necessarily the correct answer.</span></span> <span data-ttu-id="b7fa0-139">由于某些量子算法的结果基于量子操作配置的概率，因此这些计算会多次运行，以获得概率分布并优化结果的准确性。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-139">Because the result of some quantum algorithms is based on the probability that was configured by the quantum operations, these computations are run multiple times to get a probability distribution and refine the accuracy of the results.</span></span>  <span data-ttu-id="b7fa0-140">确保返回正确答案的操作称为量子验证，这是量子计算中的一项重大挑战。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-140">Assurance that an operation returned a correct answer is known as quantum verification and is a significant challenge in quantum computing.</span></span>

## <a name="summary"></a><span data-ttu-id="b7fa0-141">总结</span><span class="sxs-lookup"><span data-stu-id="b7fa0-141">Summary</span></span>

<span data-ttu-id="b7fa0-142">量子计算的部分概念与经典计算相同，但又增加了一些新的变化。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-142">Quantum computing shares some of the same concepts as classical computing but adds a few new twists.</span></span> <span data-ttu-id="b7fa0-143">下面是一些关键要点：</span><span class="sxs-lookup"><span data-stu-id="b7fa0-143">Here are some key takeaways:</span></span>

- <span data-ttu-id="b7fa0-144">量子硬件昂贵且易被损坏，因此量子模拟器用于编写和测试程序。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-144">Quantum hardware is expensive and fragile to work with, so quantum simulators are used to write and test programs.</span></span>
- <span data-ttu-id="b7fa0-145">经典计算机和量子计算机都使用逻辑运算（或门）来准备计算。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-145">Both classical and quantum computers use logic operations (or gates) to prepare computations.</span></span>
- <span data-ttu-id="b7fa0-146">量子计算返回概率。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-146">Quantum computations return probabilities.</span></span>

<span data-ttu-id="b7fa0-147">量子硬件和技术的进步正在迅速改变这一领域。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-147">Advancements in quantum hardware and techniques is rapidly changing the field.</span></span> <span data-ttu-id="b7fa0-148">这里提供的内容只是[最新动态](https://phys.org/search/?search=quantum+computer&s=0)中的一小部分。</span><span class="sxs-lookup"><span data-stu-id="b7fa0-148">Here are just a few of the [current developments](https://phys.org/search/?search=quantum+computer&s=0).</span></span>

## <a name="next-steps"></a><span data-ttu-id="b7fa0-149">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b7fa0-149">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b7fa0-150">什么是 Q# 编程语言和 QDK？</span><span class="sxs-lookup"><span data-stu-id="b7fa0-150">What is the Q# programming language and QDK?</span></span>](xref:microsoft.quantum.overview.q-sharp)