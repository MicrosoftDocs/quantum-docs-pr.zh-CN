---
title: 量程线路 |Microsoft Docs
description: 量程线路
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 7c2afa58fd70d893529cf794ae07df480466aaec
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2019
ms.locfileid: "73210625"
---
# <a name="quantum-circuits"></a><span data-ttu-id="0cd54-103">量程线路</span><span class="sxs-lookup"><span data-stu-id="0cd54-103">Quantum Circuits</span></span>
<span data-ttu-id="0cd54-104">请考虑一下单一转换 $ \text{CNOT-CONTAINS} _{01}（H\otimes 1） $。</span><span class="sxs-lookup"><span data-stu-id="0cd54-104">Consider for a moment the unitary transformation $\text{ CNOT}_{01}(H\otimes 1)$.</span></span>
<span data-ttu-id="0cd54-105">此入口序列对量程计算至关重要，因为它创建最大化放大二 qubit 状态：</span><span class="sxs-lookup"><span data-stu-id="0cd54-105">This gate sequence is of fundamental significance to quantum computing because it creates a maximally entangled two-qubit state:</span></span>

<span data-ttu-id="0cd54-106">$ $ \mathrm{CNOT}_{01}（H\otimes 1） \ket{00} = \frac{1}{\sqrt{2}} \left （\ket{00} + \ket{11} \right），$ $</span><span class="sxs-lookup"><span data-stu-id="0cd54-106">$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right),$$</span></span>

<span data-ttu-id="0cd54-107">具有这种或更大复杂性的操作在量程算法和量程错误更正中无处不在，因此它应该会很好地降低，其中有一种简单的方法可以将其可视化称为 "*量程*"。</span><span class="sxs-lookup"><span data-stu-id="0cd54-107">Operations with this or greater complexity are ubiquitous in quantum algorithms and quantum error correction, so it should come as a great relief that there is a simple method for their visualization called a *quantum circuit diagram*.</span></span>
<span data-ttu-id="0cd54-108">准备此最大化放大量程状态的线路关系图为：</span><span class="sxs-lookup"><span data-stu-id="0cd54-108">The circuit diagram for preparing this maximally entangled quantum state is:</span></span>

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/Concepts1.png)

## <a name="quantum-circuit-diagram-conventions"></a><span data-ttu-id="0cd54-109">量程线路约定</span><span class="sxs-lookup"><span data-stu-id="0cd54-109">Quantum circuit diagram conventions</span></span>
<span data-ttu-id="0cd54-110">当你了解表示量子线路的约定后，这种适用于量程操作的视觉语言比写下其等效矩阵更容易理解。</span><span class="sxs-lookup"><span data-stu-id="0cd54-110">This visual language for quantum operations can be more readily digestible than writing down its equivalent matrix once you understand the conventions for expressing a quantum circuit.</span></span>
<span data-ttu-id="0cd54-111">我们将在下面查看这些约定。</span><span class="sxs-lookup"><span data-stu-id="0cd54-111">We review these conventions below.</span></span>

<span data-ttu-id="0cd54-112">在电路图中，每个实线都描述了 qubit 或更常见的 qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="0cd54-112">In a circuit diagram, each solid line depicts a qubit or more generally a qubit register.</span></span>
<span data-ttu-id="0cd54-113">按照约定，顶行是 qubit register $0 $，余数按顺序标记。</span><span class="sxs-lookup"><span data-stu-id="0cd54-113">By convention, the top line is qubit register $0$ and the remainder are labeled sequentially.</span></span> <span data-ttu-id="0cd54-114">上面的示例线路描述为在两个 qubits （或由一个 qubit 组成的等效两个寄存器）上操作。</span><span class="sxs-lookup"><span data-stu-id="0cd54-114">The above example circuit is depicted as acting on two qubits (or equivalently two registers consisting of one qubit).</span></span>
<span data-ttu-id="0cd54-115">在一个或多个 qubit 寄存器上操作的入口表示为一个框。</span><span class="sxs-lookup"><span data-stu-id="0cd54-115">Gates acting on one or more qubit registers are denoted as a box.</span></span>
<span data-ttu-id="0cd54-116">例如，符号</span><span class="sxs-lookup"><span data-stu-id="0cd54-116">For example, the symbol</span></span>

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_2.png)

<span data-ttu-id="0cd54-117">是对 qubit 寄存器使用的[Hadamard](xref:microsoft.quantum.primitive.h)入口。</span><span class="sxs-lookup"><span data-stu-id="0cd54-117">is the [Hadamard](xref:microsoft.quantum.primitive.h) gate acting on a single-qubit register.</span></span>

<span data-ttu-id="0cd54-118">量程入口按时间顺序排列，并将最左侧的入口排列为第一个应用到 qubits 的入口。</span><span class="sxs-lookup"><span data-stu-id="0cd54-118">Quantum gates are ordered in chronological order with the left-most gate as the gate first applied to the qubits.</span></span>
<span data-ttu-id="0cd54-119">换而言之，如果将电缆画为包含量程状态，则电缆会从左到右从图中的每个入口开始显示量程状态。</span><span class="sxs-lookup"><span data-stu-id="0cd54-119">In other words, if you picture the wires as holding the quantum state, the wires bring the quantum state through each of the gates in the diagram from left to right.</span></span>
<span data-ttu-id="0cd54-120">这就是说</span><span class="sxs-lookup"><span data-stu-id="0cd54-120">That is to say</span></span> 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_3.png)

<span data-ttu-id="0cd54-121">是单一矩阵 $CBA $。</span><span class="sxs-lookup"><span data-stu-id="0cd54-121">is the unitary matrix $CBA$.</span></span>
<span data-ttu-id="0cd54-122">矩阵相乘服从相反的约定：首先应用最右侧的矩阵。</span><span class="sxs-lookup"><span data-stu-id="0cd54-122">Matrix multiplication obeys the opposite convention: the right-most matrix is applied first.</span></span> <span data-ttu-id="0cd54-123">但在量程电路关系图中，首先应用最左侧的入口。</span><span class="sxs-lookup"><span data-stu-id="0cd54-123">In quantum circuit diagrams, however, the left-most gate is applied first.</span></span>
<span data-ttu-id="0cd54-124">这种差异可能会导致混淆，因此请务必注意线性代数表示法和量子电路关系图之间的明显差异。</span><span class="sxs-lookup"><span data-stu-id="0cd54-124">This difference can at times lead to confusion, so it is important to note this significant difference between the linear algebraic notation and quantum circuit diagrams.</span></span>

## <a name="inputs-and-outputs-of-quantum-circuits"></a><span data-ttu-id="0cd54-125">量程线路的输入和输出</span><span class="sxs-lookup"><span data-stu-id="0cd54-125">Inputs and outputs of quantum circuits</span></span>
<span data-ttu-id="0cd54-126">前面给出的所有示例都与从量子入口传出的线路数（qubits）输入完全相同。</span><span class="sxs-lookup"><span data-stu-id="0cd54-126">All previous examples given have had precisely the same number of wires (qubits) input to a quantum gate as the number of wires out from the quantum gate.</span></span>
<span data-ttu-id="0cd54-127">这种情况可能会在一开始就显得合理，一般情况下，量程线路可能比输入更多或更少的输出。</span><span class="sxs-lookup"><span data-stu-id="0cd54-127">It may at first seem reasonable that quantum circuits could have more, or fewer, outputs than inputs in general.</span></span>
<span data-ttu-id="0cd54-128">但是，这是不可能的，因为所有的量程操作（节省度量值）都是单一的，因此是可逆的。</span><span class="sxs-lookup"><span data-stu-id="0cd54-128">This is impossible, however, because all quantum operations, save measurement, are unitary and hence reversible.</span></span>
<span data-ttu-id="0cd54-129">如果它们没有与输入相同的输出数，则它们不是可逆的，因而不是一个冲突。</span><span class="sxs-lookup"><span data-stu-id="0cd54-129">If they did not have the same number of outputs as inputs they would not be reversible and hence not unitary, which is a contradiction.</span></span>
<span data-ttu-id="0cd54-130">出于此原因，在线路图中绘制的任何一个框必须与输入它的线路完全相同。</span><span class="sxs-lookup"><span data-stu-id="0cd54-130">For this reason any box drawn in a circuit diagram must have precisely the same number of wires entering it as exiting it.</span></span>

<span data-ttu-id="0cd54-131">多 qubit 线路关系图遵循类似的约定来 qubit。</span><span class="sxs-lookup"><span data-stu-id="0cd54-131">Multi-qubit circuit diagrams follow similar conventions to single-qubit ones.</span></span>
<span data-ttu-id="0cd54-132">作为一个示例，我们可以定义一个双 qubit 的单一操作 $B $ to the $ （H S\otimes X） $，并将该线路称为等效于</span><span class="sxs-lookup"><span data-stu-id="0cd54-132">As a clarifying example, we can define a two-qubit unitary operation $B$ to be $(H S\otimes X)$ and express the circuit equivalently as</span></span>

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_4.png)

<span data-ttu-id="0cd54-133">我们还可以查看 $B $，以在单个 qubit 注册上执行操作，而不 2 1 是 qubit 寄存器上的操作，具体取决于使用该线路的上下文。</span><span class="sxs-lookup"><span data-stu-id="0cd54-133">We can also view $B$ as having an action on a single two-qubit register rather than two one-qubit registers depending on the context in which the circuit is used.</span></span> <span data-ttu-id="0cd54-134">此类抽象线路的最有用的属性可能是，它们允许在较高级别对复杂的量程算法进行描述，而不必将它们编译为基本入口。</span><span class="sxs-lookup"><span data-stu-id="0cd54-134">Perhaps the most useful property of such abstract circuit diagrams is that they allow complicated quantum algorithms to be described at a high level without having to compile them down to fundamental gates.</span></span>
<span data-ttu-id="0cd54-135">这意味着，你可以获取有关大型量程算法的数据流的直觉，而无需了解算法中每个子例程的工作方式的所有详细信息。</span><span class="sxs-lookup"><span data-stu-id="0cd54-135">This means that you can get an intuition about the data flow for a large quantum algorithm without needing to understand all the details of how each of the subroutines within the algorithm work.</span></span>

## <a name="controlled-gates"></a><span data-ttu-id="0cd54-136">受控入口</span><span class="sxs-lookup"><span data-stu-id="0cd54-136">Controlled gates</span></span>
<span data-ttu-id="0cd54-137">内置于 qubit 量程线路关系图的另一种构造是控件。</span><span class="sxs-lookup"><span data-stu-id="0cd54-137">The other construct that is built into multi-qubit quantum circuit diagrams is control.</span></span>
<span data-ttu-id="0cd54-138">量程单向控制入口的操作（表示 $ \Lambda （G） $，其中单个 qubit 的值控制 $G $ 的应用）可以通过查看以下产品状态输入 $ \Lambda （\alpha \ket{0} + \beta \ket 的示例来理解{1}） \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket {\ psi} $。</span><span class="sxs-lookup"><span data-stu-id="0cd54-138">The action of a quantum singly controlled gate, denoted $\Lambda(G)$, where a single qubit's value controls the application of $G$, can be understood by looking at the following example of a product state input $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket{\psi}$.</span></span>
<span data-ttu-id="0cd54-139">也就是说，当且仅当控件 qubit 采用值 $1 $ 时，受控的入口才会将 $G $ 应用于包含 $ \psi $ 的寄存器。</span><span class="sxs-lookup"><span data-stu-id="0cd54-139">That is to say, the controlled gate applies $G$ to the register containing $\psi$ if and only if the control qubit takes the value $1$.</span></span>
<span data-ttu-id="0cd54-140">通常，我们会将这些受控操作介绍为</span><span class="sxs-lookup"><span data-stu-id="0cd54-140">In general, we describe such controlled operations in circuit diagrams as</span></span>

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_5.png)

<span data-ttu-id="0cd54-141">此时，黑色圆圈表示控制门的量程位，垂直线路表示在控件 qubit 采用值 $1 $ 时应用的单一。</span><span class="sxs-lookup"><span data-stu-id="0cd54-141">Here the black circle denotes the quantum bit on which the gate is controlled and a vertical wire denotes the unitary that is applied when the control qubit takes the value $1$.</span></span>
<span data-ttu-id="0cd54-142">对于 $G = X $ 和 $G = Z $ 的特殊情况，我们引入了以下表示法来描述控制的入口版本（请注意，受控-X 门是[$CNOT $ 门](xref:microsoft.quantum.primitive.cnot)）：</span><span class="sxs-lookup"><span data-stu-id="0cd54-142">For the special cases where $G=X$ and $G=Z$ we introduce the following notation to describe the controlled version of the gates (note that the controlled-X gate is the [$CNOT$ gate](xref:microsoft.quantum.primitive.cnot)):</span></span>

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_6.png)

<span data-ttu-id="0cd54-143">Q # 提供自动生成控制版本的操作的方法，此操作使程序员不必为这些操作编写代码。</span><span class="sxs-lookup"><span data-stu-id="0cd54-143">Q# provides methods to automatically generate the controlled version of an operation, which saves the programmer from having to hand code these operations.</span></span> <span data-ttu-id="0cd54-144">下面显示了一个示例：</span><span class="sxs-lookup"><span data-stu-id="0cd54-144">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a><span data-ttu-id="0cd54-145">度量运算符</span><span class="sxs-lookup"><span data-stu-id="0cd54-145">Measurement operator</span></span>
<span data-ttu-id="0cd54-146">在 "电路图" 中显示的剩余操作是度量值。</span><span class="sxs-lookup"><span data-stu-id="0cd54-146">The remaining operation to visualize in circuit diagrams is measurement.</span></span>
<span data-ttu-id="0cd54-147">度量采用 qubit 注册，对其进行度量，并将结果输出为传统信息。</span><span class="sxs-lookup"><span data-stu-id="0cd54-147">Measurement takes a qubit register, measures it, and outputs the result as classical information.</span></span>
<span data-ttu-id="0cd54-148">度量运算由计量符号表示，并始终将 qubit 寄存器（由实线表示）作为输入，并输出古典信息（用双线表示）。</span><span class="sxs-lookup"><span data-stu-id="0cd54-148">A measurement operation is denoted by a meter symbol and always takes as input a qubit register (denoted by a solid line) and outputs classical information (denoted by a double line).</span></span>
<span data-ttu-id="0cd54-149">具体而言，此类 subcircuit 如下所示：</span><span class="sxs-lookup"><span data-stu-id="0cd54-149">Specifically, such a subcircuit looks like:</span></span>

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="0cd54-150">![度量线路](~/media/concepts_7.png)</span><span class="sxs-lookup"><span data-stu-id="0cd54-150">![Measurement circuit](~/media/concepts_7.png)</span></span>

<span data-ttu-id="0cd54-151">Q # 为此目的实现了[度量运算符](xref:microsoft.quantum.primitive.measure)。</span><span class="sxs-lookup"><span data-stu-id="0cd54-151">Q# implements a [Measure operator](xref:microsoft.quantum.primitive.measure) for this purpose.</span></span>
<span data-ttu-id="0cd54-152">有关详细信息，请参阅[有关度量值的部分](xref:microsoft.quantum.libraries.standard.prelude#measurements)。</span><span class="sxs-lookup"><span data-stu-id="0cd54-152">See the [section on measurements](xref:microsoft.quantum.libraries.standard.prelude#measurements) for more information.</span></span>

<span data-ttu-id="0cd54-153">同样，subcircuit</span><span class="sxs-lookup"><span data-stu-id="0cd54-153">Similarly, the subcircuit</span></span>

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_8.png)

<span data-ttu-id="0cd54-154">提供一个经典控制的入口，其中 $G $ 在传统控制位上应用为值 $1 $。</span><span class="sxs-lookup"><span data-stu-id="0cd54-154">gives a classically controlled gate, where $G$ is applied conditioned on the classical control bit being value $1$.</span></span>

## <a name="teleportation-circuit-diagram"></a><span data-ttu-id="0cd54-155">Teleportation 线路图</span><span class="sxs-lookup"><span data-stu-id="0cd54-155">Teleportation circuit diagram</span></span>
<span data-ttu-id="0cd54-156">[量程 teleportation](xref:microsoft.quantum.techniques.puttingittogether)可能是用于阐释这些组件的最佳量程算法。</span><span class="sxs-lookup"><span data-stu-id="0cd54-156">[Quantum teleportation](xref:microsoft.quantum.techniques.puttingittogether) is perhaps the best quantum algorithm for illustrating these components.</span></span>
<span data-ttu-id="0cd54-157">量程 teleportation 是一种方法，用于在量程计算机（甚至是在量程网络中的远程量程计算机之间）通过使用牵连和计量来移动数据。</span><span class="sxs-lookup"><span data-stu-id="0cd54-157">Quantum teleportation is a method for moving data within a quantum computer (or even between distant quantum computers in a quantum network) through the use of entanglement and measurement.</span></span>
<span data-ttu-id="0cd54-158">有趣的是，实际上可以将给定 qubit 中的值表示为从一个 qubit 移动到另一个，而无需了解 qubit 的值！</span><span class="sxs-lookup"><span data-stu-id="0cd54-158">Interestingly, it is actually capable of moving a quantum state, say the value in a given qubit, from one qubit to another, without even knowing what the qubit's value is!</span></span>
<span data-ttu-id="0cd54-159">这是协议根据量程机制的法律工作所必需的。</span><span class="sxs-lookup"><span data-stu-id="0cd54-159">This is necessary for the protocol to work according to the laws of quantum mechanics.</span></span>
<span data-ttu-id="0cd54-160">下面给出了量子 teleportation 线路;我们还提供了一条带批注的线路，用于说明如何读取量程线路。</span><span class="sxs-lookup"><span data-stu-id="0cd54-160">The quantum teleportation circuit is given below; we also provide an annotated version of the circuit to illustrate how to read the quantum circuit.</span></span>

<!--- ![](.\media\tp2.svg){ width=50% } --->
![](~/media/concepts_tp2.png)
