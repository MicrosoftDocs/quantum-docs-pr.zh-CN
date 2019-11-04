---
title: 'Q # 标准库-数据结构 |Microsoft Docs'
description: 'Q # 标准库-数据结构'
author: QuantumWriter
uid: microsoft.quantum.libraries.data-structures
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: e8b28561f1aba37cb5bf41c6176386d19bfacf06
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184502"
---
# <a name="data-structures-and-modeling"></a><span data-ttu-id="9f4cd-103">数据结构和建模</span><span class="sxs-lookup"><span data-stu-id="9f4cd-103">Data Structures and Modeling</span></span> #

## <a name="classical-data-structures"></a><span data-ttu-id="9f4cd-104">传统数据结构</span><span class="sxs-lookup"><span data-stu-id="9f4cd-104">Classical Data Structures</span></span> ##

<span data-ttu-id="9f4cd-105">除了用于表示量程概念的用户定义类型外，canon 还提供了操作、函数和类型，以便使用在量程系统控制中使用的传统数据。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-105">Along with user-defined types for representing quantum concepts, the canon also provides operations, functions, and types for working with classical data used in the control of quantum systems.</span></span>
<span data-ttu-id="9f4cd-106">例如，<xref:microsoft.quantum.arrays.reversed> 函数使用数组作为输入，并以相反顺序返回相同的数组。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-106">For instance, the <xref:microsoft.quantum.arrays.reversed> function takes an array as input and returns the same array in reverse order.</span></span>
<span data-ttu-id="9f4cd-107">然后，可在类型为 `Qubit[]` 的数组中使用，以避免在整数的量程表示形式之间进行转换时必须应用不必要的 $ \operatorname{SWAP} $ 门。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-107">This can then be used on an array of type `Qubit[]` to avoid having to apply unnecessary $\operatorname{SWAP}$ gates when converting between quantum representations of integers.</span></span>
<span data-ttu-id="9f4cd-108">同样，我们在上一节中看到，窗体 `(Int, Int -> T)` 的类型可用于表示随机访问集合，因此 <xref:microsoft.quantum.arrays.lookupfunction> 函数提供了一种从数组类型构造此类类型的 convienent 方式。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-108">Similarly, we saw in the previous section that types of the form `(Int, Int -> T)` can be useful for representing random access collections, so the <xref:microsoft.quantum.arrays.lookupfunction> function provides a convienent way of constructing such types from array types.</span></span>

### <a name="pairs"></a><span data-ttu-id="9f4cd-109">翻译</span><span class="sxs-lookup"><span data-stu-id="9f4cd-109">Pairs</span></span> ###

<span data-ttu-id="9f4cd-110">Canon 支持对的函数样式表示法，由析构访问元组的补充：</span><span class="sxs-lookup"><span data-stu-id="9f4cd-110">The canon supports functional-style notation for pairs, complementing accessing tuples by deconstruction:</span></span>

```qsharp
let pair = (PauliZ, register); // type (Pauli, Qubit[])
ApplyToEach(H, Snd(pair)); // No need to deconstruct to access the register.
```

### <a name="arrays"></a><span data-ttu-id="9f4cd-111">数组</span><span class="sxs-lookup"><span data-stu-id="9f4cd-111">Arrays</span></span> ###

<span data-ttu-id="9f4cd-112">Canon 提供了若干用于操作数组的函数。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-112">The canon provides several functions for manipulating arrays.</span></span>
<span data-ttu-id="9f4cd-113">这些函数是类型参数化的，因此可以与任何 Q # 类型的数组一起使用。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-113">These functions are type-parameterized, and thus can be used with arrays of any Q# type.</span></span>
<span data-ttu-id="9f4cd-114">例如，<xref:microsoft.quantum.arrays.reversed> 函数返回一个新数组，其元素与输入的顺序相反。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-114">For instance, the <xref:microsoft.quantum.arrays.reversed> function returns a new array whose elements are in reverse order from its input.</span></span>
<span data-ttu-id="9f4cd-115">这可用于更改调用操作时量程寄存器的表示方式：</span><span class="sxs-lookup"><span data-stu-id="9f4cd-115">This can be used to change how a quantum register is represented when calling operations:</span></span>

```qsharp
let leRegister = LittleEndian(register);
// QFT expects a BigEndian, so we can reverse before calling.
QFT(BigEndian(Reversed(leRegister!)));
// This is how the LittleEndianAsBigEndian function is implemented:
QFT(LittleEndianAsBigEndian(leRegister));
```

<span data-ttu-id="9f4cd-116">同样，可以使用 <xref:microsoft.quantum.arrays.subarray> 函数重新排序或获取数组元素的子集：</span><span class="sxs-lookup"><span data-stu-id="9f4cd-116">Similarly, the <xref:microsoft.quantum.arrays.subarray> function can be used to reorder or take subsets of the elements of an array:</span></span>

```qsharp
// Applies H to qubits 2 and 5.
ApplyToEach(H, Subarray([2, 5], register));
```

<span data-ttu-id="9f4cd-117">与流控制结合使用时，数组操作函数（如 <xref:microsoft.quantum.arrays.zip>）可提供一种强大的方法来表示量程程序：</span><span class="sxs-lookup"><span data-stu-id="9f4cd-117">When combined with flow control, array manipulation functions such as <xref:microsoft.quantum.arrays.zip> can provide a powerful way to express quantum programs:</span></span>

```qsharp
// Applies X₃ Y₁ Z₇ to a register of any size.
ApplyToEach(
    ApplyPauli(_, register),
    Map(
        EmbedPauli(_, _, Length(register)),
        Zip([PauliX, PauliY, PauliZ], [3, 1, 7])
    )
);
```

## <a name="oracles"></a><span data-ttu-id="9f4cd-118">Oracles</span><span class="sxs-lookup"><span data-stu-id="9f4cd-118">Oracles</span></span> ##

<span data-ttu-id="9f4cd-119">在[阶段估算](https://en.wikipedia.org/wiki/Quantum_phase_estimation_algorithm)和[振幅放大](https://en.wikipedia.org/wiki/Amplitude_amplification)文献中，oracle 的概念经常显示。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-119">In the [phase estimation](https://en.wikipedia.org/wiki/Quantum_phase_estimation_algorithm) and [amplitude amplification](https://en.wikipedia.org/wiki/Amplitude_amplification) literature the concept of an oracle appears frequently.</span></span>
<span data-ttu-id="9f4cd-120">此处的术语 "oracle" 指的是一组 qubits 的黑盒量程子例程，并以阶段的形式返回答案。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-120">Here the term oracle refers to a blackbox quantum subroutine that acts upon a set of qubits and returns the answer as a phase.</span></span>
<span data-ttu-id="9f4cd-121">通常，可以将此子例程视为接受 oracle 的量程算法的输入，以及其他一些参数，并应用一系列的量程操作，并将对此量程子例程的调用视为一个基本入口。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-121">This subroutine often can be thought of as an input to a quantum algorithm that accepts the oracle, in addition to some other parameters, and applies a series of quantum operations and treating a call to this quantum subroutine as if it were a fundamental gate.</span></span>
<span data-ttu-id="9f4cd-122">很明显，若要实际实现更大的算法，必须提供 oracle 到基本入口的具体分解，但这种情况下无需进行此类分解即可了解调用 oracle 的算法。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-122">Obviously, in order to actually implement the larger algorithm a concrete decomposition of the oracle into fundamental gates must be provided but such a decomposition is not needed in order to understand the algorithm that calls the oracle.</span></span>
<span data-ttu-id="9f4cd-123">在 Q # 中，此抽象通过使用该操作是第一类值来表示的，因此，可以将操作以黑白方式传递到量程算法的实现中。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-123">In Q#, this abstraction is represented by using that operations are first-class values, such that operations can be passed to implementations of quantum algorithms in a black-box manner.</span></span>
<span data-ttu-id="9f4cd-124">此外，用户定义类型用于以类型安全的方式标记不同的 oracle 表示形式，这使得很难意外人们常常会不同种类的黑框操作。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-124">Moreover, user-defined types are used to label the different oracle representations in a type-safe way, making it difficult to accidently conflate different kinds of black box operations.</span></span>

<span data-ttu-id="9f4cd-125">此类 oracles 显示在多个不同的上下文中，其中包括[Grover 的搜索](https://en.wikipedia.org/wiki/Grover%27s_algorithm)和量程模拟算法等著名示例。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-125">Such oracles appear in a number of different contexts, including famous examples such as [Grover's search](https://en.wikipedia.org/wiki/Grover%27s_algorithm) and quantum simulation algorithms.</span></span>
<span data-ttu-id="9f4cd-126">这里，我们将重点介绍两个应用程序所需的 oracles：振幅放大和相位估算。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-126">Here we focus on the oracles needed for just two applications: amplitude amplification and phase estimation.</span></span>
<span data-ttu-id="9f4cd-127">在研究到阶段估算之前，我们将首先讨论幅度放大 oracles。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-127">We will first discuss amplitude amplification oracles before proceding to phase estimation.</span></span>

### <a name="amplitude-amplification-oracles"></a><span data-ttu-id="9f4cd-128">振幅放大 Oracles</span><span class="sxs-lookup"><span data-stu-id="9f4cd-128">Amplitude Amplification Oracles</span></span> ###

<span data-ttu-id="9f4cd-129">振幅放大算法旨在通过应用一系列状态反射来执行初始状态和最终状态之间的旋转。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-129">The amplitude amplification algorithm aims to perform a rotation between an initial state and a final state by applying a sequence of reflections of the state.</span></span>
<span data-ttu-id="9f4cd-130">为了使算法正常工作，需要对这两种状态进行规范。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-130">In order for the algorithm to function, it needs a specification of both of these states.</span></span>
<span data-ttu-id="9f4cd-131">这些规范由两个 oracles 提供。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-131">These specifications are given by two oracles.</span></span>
<span data-ttu-id="9f4cd-132">这些 oracles 的工作原理是将输入分为两个空格： "target" 子空间和 "初始" 子空间。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-132">These oracles work by breaking the inputs into two spaces, a "target" subspace and an "initial" subspace.</span></span>
<span data-ttu-id="9f4cd-133">Oracles 标识了这样的 subspaces，与 Pauli 运算符如何识别两个空格的方式类似，通过将 $ \pm $1 阶段应用于这些空格。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-133">The oracles identify such subspaces, similar to how Pauli operators identify two spaces, by applying a $\pm 1$ phase to these spaces.</span></span>
<span data-ttu-id="9f4cd-134">主要区别在于，在此应用程序中，这些空间不必为半空格。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-134">The main difference is that these spaces need not be half-spaces in this application.</span></span>
<span data-ttu-id="9f4cd-135">另请注意，这两个 subspaces 通常不是互斥的：这两个类型的向量都是两个空格的成员。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-135">Also note that these two subspaces are not usually mutually exclusive: there will be vectors that are members of both spaces.</span></span>
<span data-ttu-id="9f4cd-136">如果不是这样，则幅度放大将不会产生任何影响，因此我们需要初始子空间与目标子空间不为零重叠。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-136">If this were not true then amplitude amplification would have no effect so we need the initial subspace to have non-zero overlap with the target subspace.</span></span>

<span data-ttu-id="9f4cd-137">对于要 $P\_$0 的幅度放大，我们将指出需要的第一台 oracle，并将其定义为具有以下操作。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-137">We will denote the first oracle that we need for amplitude amplification to be $P\_0$, defined to have the following action.</span></span>  <span data-ttu-id="9f4cd-138">对于 "初始" 子空间 $P 中的所有状态 $ \ket{x} $\_0 \ket{x} =-\ket{x} $ 和不在此 \ket{y} 中的所有状态 $ 子空间 $，我们已 $P\_0 \ket{y} = \ket{y} $。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-138">For all states $\ket{x}$ in the "initial" subspace $P\_0 \ket{x} = -\ket{x}$ and for all states $\ket{y}$ that are not in this subspace we have $P\_0 \ket{y} = \ket{y}$.</span></span>
<span data-ttu-id="9f4cd-139">标记目标子空间 $P _1 $ 的 oracle 将采用完全相同的形式。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-139">The oracle that marks the target subspace, $P_1$, takes exactly the same form.</span></span>
<span data-ttu-id="9f4cd-140">对于目标子空间中的所有状态 $ \ket{x} $ （即，对于要输出算法的所有状态），$P _1 \ 票证 {x} =-\ket{x} $。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-140">For all states $\ket{x}$ in the target subspace (i.e., for all states that you'd like the algorithm to output), $P_1\ket{x} = -\ket{x}$.</span></span>
<span data-ttu-id="9f4cd-141">同样，对于不在目标子空间中的所有状态 $ \ket{y} $ $P _1 \ 票证 {y} = \ket{y} $。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-141">Similarly, for all states $\ket{y}$ that are not in the target subspace $P_1\ket{y} = \ket{y}$.</span></span>
<span data-ttu-id="9f4cd-142">然后将这两个反射组合起来以形成一个运算符，该运算符将制定 =-P_0 P_1 $ 的单个步骤 $Q，其中，整体减号只是在受控应用程序中考虑。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-142">These two reflections are then combined to form an operator that enacts a single step of amplitude amplification, $Q = -P_0 P_1$, where the overall minus sign is only important to consider in controlled applications.</span></span>
<span data-ttu-id="9f4cd-143">然后，振幅放大进入初始状态的 $ \ket{\psi} $，然后执行 $ \ket{\psi} \mapsto Q ^ m \ket{\psi} $。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-143">Amplitude amplification then proceeds by taking an initial state, $\ket{\psi}$ that is in the initial subspace and then performs $\ket{\psi} \mapsto Q^m \ket{\psi}$.</span></span>
<span data-ttu-id="9f4cd-144">如果执行此类迭代，则可保证如果一次启动时使用的初始状态与标记的空间重叠 $ \sin ^ 2 （\theta） $，则在 $m $ 迭代后，此重叠将变为 $ \sin ^ 2 （[2m + 1] \theta） $。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-144">Performing such an iteration guarantees that if one starts with an initial state that has overlap $\sin^2(\theta)$ with the marked space then after $m$ iterations this overlap becomes $\sin^2([2m + 1] \theta)$.</span></span>
<span data-ttu-id="9f4cd-145">因此，我们通常希望选择 $m $ 为自由参数，如 $ [2m + 1] \theta = \ pi/2 $;但是，这种严格的选择对于某些形式的振幅放大（如固定点波幅放大）并不重要。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-145">We therefore typically wish to choose $m$ to be a free parameter such that $[2m+1]\theta = \pi/2$; however, such rigid choices are not as important for some forms of amplitude amplification such as fixed point amplitude amplification.</span></span>
<span data-ttu-id="9f4cd-146">使用此过程，我们可以在标记的子空间中准备一个状态，使用几率更少查询标记函数，将状态准备函数限制在严格的设备上。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-146">This process allows us to prepare a state in the marked subspace using quadratically fewer queries to the marking function and the state preparation function than would be possible on a strictly classical device.</span></span>
<span data-ttu-id="9f4cd-147">这就是为什么在量程计算的许多应用程序中，振幅放大是一个重要的构建基块。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-147">This is why amplitude amplification is a significant building block for many applications of quantum computing.</span></span>

<span data-ttu-id="9f4cd-148">若要了解如何使用该算法，提供一个提供 oracles 构造的示例非常有用。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-148">In order to understand how to use the algorithm, it is useful to provide an example that gives a construction of the oracles.</span></span>  <span data-ttu-id="9f4cd-149">请考虑在此设置中执行 Grover 的数据库搜索算法。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-149">Consider performing Grover's algorithm for database searches in this setting.</span></span>
<span data-ttu-id="9f4cd-150">在 Grover 的搜索中，目标是将状态 $ \ket{+} ^ {\otimes n} = H ^ {\otimes n} \ket{0}$ 转换为一个（可能的）多个标记的状态。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-150">In Grover's search the goal is to transform the state $\ket{+}^{\otimes n} = H^{\otimes n} \ket{0}$ into one of (potentially) many marked states.</span></span>
<span data-ttu-id="9f4cd-151">为了进一步简化，只需查看标记状态为 $ \ket{0}$ 的情况。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-151">To further simplify, let's just look at the case where the only marked state is $\ket{0}$.</span></span>
<span data-ttu-id="9f4cd-152">接下来，我们设计了两个 oracles：一个仅使用减号标记初始状态 $ \ket{+} ^ {\otimes n} $，另一个使用减号标记标记状态 $ \ket{0}$。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-152">Then we have design two oracles: one that only marks the initial state $\ket{+}^{\otimes n}$ with a minus sign and another that marks the marked state $\ket{0}$ with a minus sign.</span></span>
<span data-ttu-id="9f4cd-153">通过使用 canon 中的控制流操作，可以使用以下处理操作来实现后一门：</span><span class="sxs-lookup"><span data-stu-id="9f4cd-153">The latter gate can be implemented using the following process operation, by using the control flow operations in the canon:</span></span>

```qsharp
operation ReflectAboutAllZeros(register : Qubit[]) : Unit 
is Adj + Ctl {

    // Apply $X$ gates to every qubit.
    ApplyToEach(X, register);

    // Apply an $n-1$ controlled $Z$-gate to the $n^{\text{th}}$ qubit.
    // This gate will lead to a sign flip if and only if every qubit is
    // $1$, which happens only if each of the qubits were $0$ before step 1.
    Controlled Z(Most(register), Tail(register));

    // Apply $X$ gates to every qubit.
    ApplyToEach(X, register);
}
```

<span data-ttu-id="9f4cd-154">此 oracle 是 <xref:microsoft.quantum.canon.rall1> 操作的一种特殊情况，它允许由任意阶段（而非反射事例 $ \phi = \pi $）旋转。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-154">This oracle is then a special case of the <xref:microsoft.quantum.canon.rall1> operation, which allows for rotating by an arbitrary phase instead of the reflection case $\phi = \pi$.</span></span>
<span data-ttu-id="9f4cd-155">在这种情况下，`RAll1` 类似于 <xref:microsoft.quantum.intrinsic.r1> prelude 操作，因为它会旋转约 $ \ket{11\cdots1} $，而不是 qubit 状态 $ \ket{1}$。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-155">In this case, `RAll1` is similar to the <xref:microsoft.quantum.intrinsic.r1> prelude operation, in that it rotates about $\ket{11\cdots1}$ instead of the single-qubit state $\ket{1}$.</span></span>

<span data-ttu-id="9f4cd-156">标记初始子空间的 oracle 可以按类似方式构造。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-156">The oracle that marks the initial subspace can be constructed similarly.</span></span>
<span data-ttu-id="9f4cd-157">在伪代码中：</span><span class="sxs-lookup"><span data-stu-id="9f4cd-157">In pseudocode:</span></span>

1. <span data-ttu-id="9f4cd-158">将 $H $ 门应用到每个 qubit。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-158">Apply $H$ gates to every qubit.</span></span>
2. <span data-ttu-id="9f4cd-159">将 $X $ 门应用到每个 qubit。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-159">Apply $X$ gates to every qubit.</span></span>
3. <span data-ttu-id="9f4cd-160">将 $n-$1 控制的 $Z $-入口应用到 $n ^ {\text{th}} $ qubit。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-160">Apply an $n-1$ controlled $Z$-gate to the $n^{\text{th}}$ qubit.</span></span>
4. <span data-ttu-id="9f4cd-161">将 $X $ 门应用到每个 qubit。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-161">Apply $X$ gates to every qubit.</span></span>
5. <span data-ttu-id="9f4cd-162">将 $H $ 门应用到每个 qubit。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-162">Apply $H$ gates to every qubit.</span></span>

<span data-ttu-id="9f4cd-163">这次，我们还演示了如何将 <xref:microsoft.quantum.canon.applywith> 与上述 <xref:microsoft.quantum.canon.rall1> 操作结合使用：</span><span class="sxs-lookup"><span data-stu-id="9f4cd-163">This time, we also demonstrate using <xref:microsoft.quantum.canon.applywith> together with the <xref:microsoft.quantum.canon.rall1> operation discussed above:</span></span>

```qsharp
operation ReflectAboutInitial(register : Qubit[]) : Unit
is Adj + Ctl {
    ApplyWithCA(ApplyToEach(H, _), ApplyWith(ApplyToEach(X, _), RAll1(_, PI()), _), register);
}
```

<span data-ttu-id="9f4cd-164">接下来，我们可以将这两个 oracles 组合在一起，以在两个状态之间旋转{0}，并使用与 $ Hadamard ^ n} $ （ie $m \sqrt{2 ^ n} $）成比例的多层 \Propto与大约 $ 2 ^ n $ 层相比，在观察到结果 $0 $ 之前，需要通过准备和测量初始状态，以不明确的方式准备 $ \ket{0}$ 状态。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-164">We can then combine these two oracles together to rotate between the two states and deterministically transform $\ket{+}^{\otimes n}$ to $\ket{0}$ using a number of layers of Hadamard gates that is proportional to $\sqrt{2^n}$ (ie $m\propto \sqrt{2^n}$) versus the roughly $2^n$ layers that would be needed to non-deterministically prepare the $\ket{0}$ state by preparing and measuring the initial state until the outcome $0$ is observed.</span></span>

### <a name="phase-estimation-oracles"></a><span data-ttu-id="9f4cd-165">阶段估算 Oracles</span><span class="sxs-lookup"><span data-stu-id="9f4cd-165">Phase Estimation Oracles</span></span> ###

<span data-ttu-id="9f4cd-166">对于阶段估算，oracles 有些自然。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-166">For phase estimation the oracles are somewhat more natural.</span></span>
<span data-ttu-id="9f4cd-167">阶段估算中的目标是设计一个子例程，该子例程能够从单一矩阵的本征值进行抽样。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-167">The aim in phase estimation is to design a subroutine that is capable of sampling from the eigenvalues of a unitary matrix.</span></span>
<span data-ttu-id="9f4cd-168">此方法在量程模拟中是或缺的，因为对于化学和材料科学中的许多物理问题，这些本征值提供了针对分子的材料和反应 dynamics。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-168">This method is indispensible in quantum simulation because for many physical problems in chemistry and material science these eigenvalues give the ground-state energies of quantum systems which provides us valuable information about the phase diagrams of materials and reaction dynamics for molecules.</span></span>
<span data-ttu-id="9f4cd-169">每个阶段估计风格都需要一个输入。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-169">Every flavor of phase estimation needs an input unitary.</span></span>
<span data-ttu-id="9f4cd-170">这种单一方法通常由两种类型的 oracles 之一来描述。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-170">This unitary is customarily described by one of two types of oracles.</span></span>

> [!TIP]
> <span data-ttu-id="9f4cd-171">示例中介绍了以下两种 oracle 类型。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-171">Both of the oracle types described below are covered in the samples.</span></span>
> <span data-ttu-id="9f4cd-172">若要了解有关连续查询 oracles 的详细信息，请参阅[ **PhaseEstimation**示例](https://github.com/Microsoft/Quantum/tree/master/Samples/src/PhaseEstimation)。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-172">To learn more about continuous query oracles, please see the [**PhaseEstimation** sample](https://github.com/Microsoft/Quantum/tree/master/Samples/src/PhaseEstimation).</span></span>
> <span data-ttu-id="9f4cd-173">若要了解有关离散查询 oracles 的详细信息，请参阅[ **IsingPhaseEstimation**示例](https://github.com/Microsoft/Quantum/tree/master/Samples/src/IsingPhaseEstimation)。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-173">To learn more about discrete query oracles, please see the [**IsingPhaseEstimation** sample](https://github.com/Microsoft/Quantum/tree/master/Samples/src/IsingPhaseEstimation).</span></span>

<span data-ttu-id="9f4cd-174">第一种类型的 oracle 是在 oracle 中调用离散查询，并使用用户定义类型 <xref:microsoft.quantum.oracles.discreteoracle>来表示，只涉及一个单一矩阵。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-174">The first type of oracle, which we call a discrete query oracle and represent with the user-defined type <xref:microsoft.quantum.oracles.discreteoracle>, simply involves a unitary matrix.</span></span>
<span data-ttu-id="9f4cd-175">如果 $U $ 是要估计其本征值的单一项，则 $U $ 的 oracle 只是实现 $U $ 的子程序的一个独立。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-175">If $U$ is the unitary whose eigenvalues we wish to estimate then the oracle for $U$ is simply a stand-in for a subroutine that implements $U$.</span></span>
<span data-ttu-id="9f4cd-176">例如，可以将 $U $ 指定为上述 oracle $Q $ 来估算幅度估算。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-176">For example, one could take $U$ to be the oracle $Q$ defined above for amplitude estimation.</span></span>
<span data-ttu-id="9f4cd-177">此矩阵的本征值可用于估算初始状态与目标状态之间的重叠，$ \sin ^ 2 （\theta） $，使用的样本越少，将需要其他值。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-177">The eigenvalues of this matrix can be used to estimate the overlap between the initial and target states, $\sin^2(\theta)$, using quadratically fewer samples than one would need otherwise.</span></span>
<span data-ttu-id="9f4cd-178">这盈利将使用 Grover oracle $Q $ 作为输入的应用程序阶段估算作为输入的名字对象。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-178">This earns the application of phase estimation using the Grover oracle $Q$ as input the moniker of amplitude estimation.</span></span>
<span data-ttu-id="9f4cd-179">量程 metrology 中广泛使用的另一个常见应用程序涉及到估计一个小旋转角度。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-179">Another common application, widely used in quantum metrology, involves estimating a small rotation angle.</span></span>
<span data-ttu-id="9f4cd-180">换句话说，我们想要为 $R _z （\theta） $ 形式的未知旋转入口估计 $ \theta $。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-180">In other words, we wish to estimate $\theta$ for an unknown rotation gate of the form $R_z(\theta)$.</span></span>
<span data-ttu-id="9f4cd-181">在这种情况下，我们要与之交互的子例程是： $ $ \begin{align} U & = R_z （\theta） \\\\ & = \begin{bmatrix} e ^ {-i \theta/2} & 0 \\\\ 0 & e ^ {i \theta/2} \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-181">In such cases, the subroutine that we would interact with in order to learn this fixed value of $\theta$ for the gate is $$ \begin{align} U & = R_z(\theta) \\\\ & = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i\theta/2} \end{bmatrix}.</span></span>
<span data-ttu-id="9f4cd-182">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="9f4cd-182">\end{align} $$</span></span>

<span data-ttu-id="9f4cd-183">阶段估算中使用的第二种类型的 oracle 是持续查询 oracle，由 <xref:microsoft.quantum.oracles.continuousoracle> 类型表示。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-183">The second type of oracle used in phase estimation is the continuous query oracle, represented by the <xref:microsoft.quantum.oracles.continuousoracle> type.</span></span>
<span data-ttu-id="9f4cd-184">针对阶段估算的连续查询采用形式 $U （t） $，其中 $t $ 是经典的已知实数。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-184">A continuous query oracle for phase estimation takes the form $U(t)$ where $t$ is a classically known real number.</span></span>
<span data-ttu-id="9f4cd-185">如果允许 $U $ 是固定的单一项，则 oracle 连续查询将采用 $U （t） = U ^ t $ 的形式。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-185">If we let $U$ be a fixed unitary then the continuous query oracle takes the form $U(t) = U^t$.</span></span>
<span data-ttu-id="9f4cd-186">这样，我们就可以查询如 $ \sqrt{U} $ 这样的矩阵，这些矩阵无法直接在离散查询模型中实现。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-186">This allows us to query matrices such as $\sqrt{U}$, which could not be implemented directly in the discrete query model.</span></span>

<span data-ttu-id="9f4cd-187">这种类型的 oracle 非常有用，因为你不会探测特定的单一系统，而是想要了解单一的生成器属性。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-187">This type of oracle is valuable when you're not probing a particular unitary, but rather wish to learn the properties of the generator of the unitary.</span></span>
<span data-ttu-id="9f4cd-188">例如，在 dynamical 量程模拟中，目标是设计一些量程线路，使其大致接近 $U （t） = e ^ {-i H t} $ for Hermitian matrix $H $ 和演化时间 $t $。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-188">For example, in dynamical quantum simulation the goal is to devise quantum circuits that closely approximate $U(t)=e^{-i H t}$ for a Hermitian matrix $H$ and evolution time $t$.</span></span>
<span data-ttu-id="9f4cd-189">$U （t） $ 的本征值直接与 $H $ 的本征值相关。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-189">The eigenvalues of $U(t)$ are directly related to the eigenvalues of $H$.</span></span>
<span data-ttu-id="9f4cd-190">若要查看此内容，请考虑 $H $： $H \ket{E} = E\ket {E} $ 的 eigenvector，然后可以从矩阵指数的电源系列定义中轻松看到 $U （t） \ket{E} = e ^ {i\phi} \ 票证 {E} = e ^ {-iEt} \ket{E} $。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-190">To see this, consider an eigenvector of $H$: $H \ket{E} = E\ket{E}$ then it is easy to see from the power-series definition of the matrix exponential that $U(t) \ket{E} = e^{i\phi}\ket{E}= e^{-iEt}\ket{E}$.</span></span>
<span data-ttu-id="9f4cd-191">因此，估计 $U 的 eigenphase （t） $ $E $ 假设 eigenvector $ \ket{E} $ 输入到阶段估算算法。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-191">Thus estimating the eigenphase of $U(t)$ gives the eigenvalue $E$ assuming the eigenvector $\ket{E}$ is input into the phase estimation algorithm.</span></span>
<span data-ttu-id="9f4cd-192">但是，在这种情况下，可以按用户的意愿选择值 $t $，因为 $t $ 的任何足够小值都可以通过 $E =-\ phi/t $ $E 唯一反转。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-192">However, in this case the value $t$ can be chosen at the user's discretion since for any sufficiently small value of $t$ the eigenvalue $E$ can be uniquely inverted through $E=-\phi/t$.</span></span>
<span data-ttu-id="9f4cd-193">由于量程模拟方法提供执行小数演变的能力，因此，在查询单一阶段时，这会授予阶段估算算法额外的自由度，特别是在离散查询模型只允许 unitaries 形式 $U ^ j $若要应用于整数 $j $ 此连续查询，oracle 允许我们将 $U ^ t $ 形式的窗体大致 ^ t $，以实现任何真正的价值 $t $。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-193">Since quantum simulation methods provide the ability to perform a fractional evolution, this grants phase estimation algorithms an additional freedom when querying the unitary, specifically while the discrete query model allows only unitaries of the form $U^j$ to applied for integer $j$ the continuous query oracle allows us to approximate unitaries of the form $U^t$ for any real valued $t$.</span></span>
<span data-ttu-id="9f4cd-194">这一点非常重要，因为它使我们能够精确地选择可提供有关 $E $ 的最多信息的试验：而基于离散查询的方法必须在算法中选择最大的整数查询来使其成为损害。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-194">This is important to squeeze every last ounce of efficiency out of phase estimation algorithms because it allows us to choose precisely the experiment that would provide the most information about $E$; whereas methods based on discrete queries must make do with compromising by choosing the best integer number of queries in the algorithm.</span></span>

<span data-ttu-id="9f4cd-195">作为此问题的具体示例，请考虑估计不是门的旋转角度但旋转后的量程系统的 procession 频率的问题。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-195">As a concrete example of this, consider the problem of estimating not the rotation angle of a gate but the procession frequency of a rotating quantum system.</span></span>
<span data-ttu-id="9f4cd-196">对于演化时间 $t $ 和 unknown frequency $ \omega $，描述此类量程动态的单一 $U （t） = R_z （2 \ omega t） $。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-196">The unitary that describes such quantum dynamics is $U(t)=R_z(2\omega t)$ for evolution time $t$ and unknown frequency $\omega$.</span></span>
<span data-ttu-id="9f4cd-197">在这种情况下，我们可以使用单个 $R _z $ 入口来模拟任何 $t $ 的 $U （t） $，因此不需要将自己限制为仅对单一的单独查询。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-197">In this context, we can simulate $U(t)$ for any $t$ using a single $R_z$ gate and as such do not need to restrict ourselves to only discrete queries to the unitary.</span></span>
<span data-ttu-id="9f4cd-198">此类连续模型还具有属性，该属性的频率大于 $ 2 \ pi $，可以从使用连续查询的阶段估算流程中获知，因为在显示在 $t $ 的非相当值上执行试验的结果。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-198">Such a continuous model also has the property that frequencies greater than $2\pi$ can be learned from phase estimation processes that use continuous queries because phase information that would otherwise be masked by the branch-cuts of the logarithm function can be revealed from the results of experiments performed on non-commensurate values of $t$.</span></span>
<span data-ttu-id="9f4cd-199">因此，对于这样的问题，例如，针对阶段估计 oracle 的连续查询模型不仅合适，而且还优于离散查询模型。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-199">Thus for problems such as this continuous query models for the phase estimation oracle are not only appropriate but are also preferable to the discrete query model.</span></span>
<span data-ttu-id="9f4cd-200">出于此原因，Q # 功能适用于这两种形式的查询，并将其留给用户，以决定满足其需求的阶段估算算法，以及可用的 oracle 类型。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-200">For this reason Q# has functionality for both forms of queries and leave it to the user to decide upon a phase estimation algorithm to fit their needs and the type of oracle that is available.</span></span>

## <a name="dynamical-generator-modeling"></a><span data-ttu-id="9f4cd-201">Dynamical 生成器建模</span><span class="sxs-lookup"><span data-stu-id="9f4cd-201">Dynamical Generator Modeling</span></span> ##

<span data-ttu-id="9f4cd-202">时间演化的生成器介绍状态随着时间推移的发展方式。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-202">Generators of time-evolution describe how states evolve through time.</span></span> <span data-ttu-id="9f4cd-203">例如，量程状态 $ \ket{\psi} $ 的 dynamics 由 Schrödinger 公式 $ $ \begin{align} i\frac {d \ket{\psi （t）}} {d t} & = H \ket{\psi （t）}，\end{align} $ $ 和 Hermitian matrix $H $ （称为 Hamiltonian，作为生成器动作.</span><span class="sxs-lookup"><span data-stu-id="9f4cd-203">For instance, the dynamics of a quantum state $\ket{\psi}$ is governed by the Schrödinger equation $$ \begin{align} i\frac{d \ket{\psi(t)}}{d t} & = H \ket{\psi(t)}, \end{align} $$ with a Hermitian matrix $H$, known as the Hamiltonian, as the generator of motion.</span></span> <span data-ttu-id="9f4cd-204">给定一个初始状态 $ \ket{\psi （0）} $ $t = $0 时，该公式在时间 $t $ 可能是在原则上写入 $ $ \begin{align} \ket{\psi （t）} = U （t） \ket{\psi （0）}，\end{align} $ $，其中矩阵指数 $U （t） = e ^ {-i H t} $ 称为单一时间演化运算符。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-204">Given an initial state $\ket{\psi(0)}$ at time $t=0$, the formal solution to this equation at time $t$ may be, in principle, written $$ \begin{align} \ket{\psi(t)} = U(t)\ket{\psi(0)}, \end{align} $$ where the matrix exponential $U(t)=e^{-i H t}$ is known as the unitary time-evolution operator.</span></span> <span data-ttu-id="9f4cd-205">尽管我们将重点放在下面这一窗体的发电机上，但我们强调到，该概念更广泛地应用，例如模拟开放的量程系统或更多抽象的差分等式。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-205">Though we focus on generators of this form in the following, we emphasize that the concept applies more broadly, such as to the simulation of open quantum systems, or to more abstract differential equations.</span></span>

<span data-ttu-id="9f4cd-206">Dynamical 模拟的主要目标是对在量程计算机的 qubits 中编码的某些量程状态实施时间演化运算符。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-206">A primary goal of dynamical simulation is to implement the time-evolution operator on some quantum state encoded in qubits of a quantum computer.</span></span>  <span data-ttu-id="9f4cd-207">在许多情况下，Hamiltonian 可能会被分解为某些 $d $ 简化术语的总和</span><span class="sxs-lookup"><span data-stu-id="9f4cd-207">In many cases, the Hamiltonian may be broken into a sum of some $d$ simpler terms</span></span>

<span data-ttu-id="9f4cd-208">$ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} H_j，\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="9f4cd-208">$$ \begin{align} H & = \sum^{d-1}_{j=0} H_j, \end{align} $$</span></span>

<span data-ttu-id="9f4cd-209">在量程计算机上，每个术语单独进行的时间演化非常容易实现。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-209">where time-evolution by each term alone is easy to implement on a quantum computer.</span></span> <span data-ttu-id="9f4cd-210">例如，如果 $H _j $ 是一个 Pauli $X _1X_2 $ 运算符，该运算符作用于 qubit 寄存器 `qubits`的第一个和第二个元素，则在任何时间 $t $ 可以通过调用 `Exp([PauliX,PauliX], t, qubits[1..2])`的操作 `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`来实现，只需调用具有签名的操作即可。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-210">For instance, if $H_j$ is a Pauli $X_1X_2$ operator acting on the 1st and 2nd elements of the qubit register `qubits`, time-evolution by it for any time $t$ may be implemented simply by calling the operation `Exp([PauliX,PauliX], t, qubits[1..2])`, which has signature `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="9f4cd-211">如稍后在 Hamiltonian 模拟中所述，一个解决方案是通过使用一系列简单的操作 $H $ 来估算时间演变。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-211">As discussed later in Hamiltonian Simulation, one solution then is to approximate time-evolution by $H$ with a sequence of simpler operations</span></span>

<span data-ttu-id="9f4cd-212">$ $ \begin{align} U （t） & = \left （e ^ {-iH\_0 t/r} e ^ {-iH\_1 t/r} \cdots e ^ {-iH\_{d} + \Right （d ^ 2 \mathcal{O} \\|H\_j\\| ^ 2 t ^ 2/r），\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="9f4cd-212">$$ \begin{align} U(t) & = \left( e^{-iH\_0 t / r} e^{-iH\_1 t / r} \cdots e^{-iH\_{d-1} t / r} \right)^{r} + \mathcal{O}(d^2 \max_j \\|H\_j\\|^2 t^2/r), \end{align} $$</span></span>

<span data-ttu-id="9f4cd-213">其中整数 $r > $0 控制近似值错误。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-213">where the integer $r > 0$ controls the approximation error.</span></span>

<span data-ttu-id="9f4cd-214">Dynamical 生成器建模库提供了一个框架，用于在更简单的生成器方面系统地编码复杂的生成器。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-214">The dynamical generator modeling library provides a framework for systematically encoding complicated generators in terms of simpler generators.</span></span> <span data-ttu-id="9f4cd-215">然后，可以通过所选的模拟算法将此类描述传递给模拟库，以实现由所选模拟算法进行的时间演化，并自动处理许多详细信息。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-215">Such a description may then be passed to, say, the simulation library to implement time-evolution by a simulation algorithm of choice, with many details automatically taken care of.</span></span>

> [!TIP]
> <span data-ttu-id="9f4cd-216">示例中介绍了下面描述的 dynamical 生成器库。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-216">The dynamical generator library described below is covered in the samples.</span></span> <span data-ttu-id="9f4cd-217">有关基于 Ising 模型的示例，请参阅[ **IsingGenerators**示例](https://github.com/Microsoft/Quantum/tree/master/Samples/src/IsingGenerators)。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-217">For an example based on the Ising model, please see the [**IsingGenerators** sample](https://github.com/Microsoft/Quantum/tree/master/Samples/src/IsingGenerators).</span></span>
> <span data-ttu-id="9f4cd-218">有关基于分子 Hydrogen 的示例，请参阅[**H2SimulationCmdLine**](https://github.com/Microsoft/Quantum/tree/master/Samples/src/H2SimulationCmdLine)和[**H2SimulationGUI**](https://github.com/Microsoft/Quantum/tree/master/Samples/src/H2SimulationGUI)示例。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-218">For an example based on molecular Hydrogen, please see the [**H2SimulationCmdLine**](https://github.com/Microsoft/Quantum/tree/master/Samples/src/H2SimulationCmdLine) and [**H2SimulationGUI**](https://github.com/Microsoft/Quantum/tree/master/Samples/src/H2SimulationGUI) samples.</span></span>

### <a name="complete-description-of-a-generator"></a><span data-ttu-id="9f4cd-219">生成器的完整说明</span><span class="sxs-lookup"><span data-stu-id="9f4cd-219">Complete Description of a Generator</span></span> ###

<span data-ttu-id="9f4cd-220">在顶层，Hamiltonian 的完整说明包含在包含两个组件的 `EvolutionGenerator` 用户定义类型中。：</span><span class="sxs-lookup"><span data-stu-id="9f4cd-220">At the top level, a complete description of a Hamiltonian is contained in the `EvolutionGenerator` user-defined type which has two components.:</span></span>

```qsharp
newtype EvolutionGenerator = (EvolutionSet, GeneratorSystem);
```

<span data-ttu-id="9f4cd-221">`GeneratorSystem` 用户定义类型是 Hamiltonian 的传统说明。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-221">The `GeneratorSystem` user-defined type is a classical description of the Hamiltonian.</span></span>

```qsharp
newtype GeneratorSystem = (Int, (Int -> GeneratorIndex));
```

<span data-ttu-id="9f4cd-222">元组的第一个元素 `Int` 在 Hamiltonian 中存储 $d $ 的字词数量，第二个元素 `(Int -> GeneratorIndex)` 是一个函数，该函数将 $\{0 中的整数索引映射到，1,...,\}$ 到唯一标识每个Hamiltonian 中的基元术语。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-222">The first element `Int` of the tuple stores the number of terms $d$ in the Hamiltonian, and the second element `(Int -> GeneratorIndex)` is a function that maps an integer index in $\{0,1,...,d-1\}$ to a `GeneratorIndex` user-defined type which uniquely identifies each primitive term in the Hamiltonian.</span></span> <span data-ttu-id="9f4cd-223">请注意，通过将 Hamiltonian 中的字词集合表示为函数而不是数组 `GeneratorIndex[]`，这可以实现 `GeneratorIndex` 的实时计算，这在描述包含大量字词的 Hamiltonians 时特别有用。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-223">Note that by expressing the collection of terms in the Hamiltonian as a function rather than as an array `GeneratorIndex[]`, this allows for on-the-fly computation of the `GeneratorIndex` which is especially useful when describing Hamiltonians with a large number of terms.</span></span>

<span data-ttu-id="9f4cd-224">至关重要，我们不会对由 `GeneratorIndex` 标识的基元术语进行简单模拟的约定。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-224">Crucially, we do not impose a convention on what primitive terms identified by the `GeneratorIndex` are easy-to-simulate.</span></span> <span data-ttu-id="9f4cd-225">例如，基元术语可能是 Pauli 运算符，如前文所述，但也可以是 Fermionic annihilation 和创建运算符，通常用于量程化学模拟。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-225">For instance, primitive terms could be Pauli operators as discussed above, but they could also be Fermionic annihilation and creation operators commonly used in quantum chemistry simulation.</span></span> <span data-ttu-id="9f4cd-226">它本身就没有任何意义 `GeneratorIndex`，因为它不会描述它所指向的字词的时间演变如何作为一个量子线路来实现。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-226">By itself, a `GeneratorIndex` is meaningless as it does not describe how time-evolution by the term it points to may be implemented as a quantum circuit.</span></span>

<span data-ttu-id="9f4cd-227">这是通过指定 `EvolutionSet` 用户定义的类型来解决的，该类型将从某个规范集绘制的任何 `GeneratorIndex`映射到单一运算符 `EvolutionUnitary`（以量程线路表示）。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-227">This is resolved by specifying an `EvolutionSet` user-defined type that maps any `GeneratorIndex`, drawn from some canonical set, to a unitary operator, the `EvolutionUnitary`, expressed as a quantum circuit.</span></span> <span data-ttu-id="9f4cd-228">`EvolutionSet` 定义 `GeneratorIndex` 结构的约定，同时定义一组可能的 `GeneratorIndex`。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-228">The `EvolutionSet` defines the convention of how a `GeneratorIndex` is structured, and also defines the set of possible `GeneratorIndex`.</span></span>

```qsharp
newtype EvolutionSet = (GeneratorIndex -> EvolutionUnitary);
```

### <a name="pauli-operator-generators"></a><span data-ttu-id="9f4cd-229">Pauli 运算符生成器</span><span class="sxs-lookup"><span data-stu-id="9f4cd-229">Pauli Operator Generators</span></span> ###

<span data-ttu-id="9f4cd-230">生成器的一个具体和有用的示例是 Hamiltonians，它们都是 Pauli 运算符的总和，每个都可能使用不同的系数。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-230">A concrete and useful example of generators are Hamiltonians that are a sum of Pauli operators, each possibly with a different coefficient.</span></span>
<span data-ttu-id="9f4cd-231">$ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} a_j H_j，\end{align} $ $，其中每个 $ \hat H_j $ 现在都是从 Pauli 组中提取的。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-231">$$ \begin{align} H & = \sum^{d-1}_{j=0} a_j H_j, \end{align} $$ where each $\hat H_j$ is now drawn from the Pauli group.</span></span> <span data-ttu-id="9f4cd-232">对于这类系统，我们提供了 `EvolutionSet` 类型的 `PauliEvolutionSet()`，该类型定义了 Pauli 组元素和系数如何由 `GeneratorIndex`标识（具有以下签名）的约定。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-232">For such systems, we provide the `PauliEvolutionSet()` of type `EvolutionSet` that defines a convention for how an element of the Pauli group and a coefficient may be identified by a `GeneratorIndex`, which has the following signature.</span></span>

```qsharp
newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```

<span data-ttu-id="9f4cd-233">在编码中，第一个参数 `Int[]` 指定一个 Pauli 字符串，其中 $ \hat I\rightarrow $0，$ \hat X\rightarrow $1，$ \hat Y\rightarrow $2，$ \hat Z\rightarrow $3。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-233">In our encoding, the first parameter `Int[]` specifies a Pauli string, where $\hat I\rightarrow 0$, $\hat X\rightarrow 1$, $\hat Y\rightarrow 2$, and $\hat Z\rightarrow 3$.</span></span> <span data-ttu-id="9f4cd-234">第二个参数 `Double[]` 将 Pauli 字符串的系数存储在 Hamiltonian 中。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-234">The second parameter `Double[]` stores the coefficient of the Pauli string in the Hamiltonian.</span></span> <span data-ttu-id="9f4cd-235">请注意，只使用此数组的第一个元素。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-235">Note that only the first element of this array is used.</span></span> <span data-ttu-id="9f4cd-236">第三个参数 `Int[]` 为此 Pauli 字符串操作的 qubits 编制索引，并且必须没有重复元素。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-236">The third parameter `Int[]` indexes the qubits that this Pauli string acts on, and must have no duplicate elements.</span></span> <span data-ttu-id="9f4cd-237">因此，Hamiltonian 术语 $0.4 \hat X_0 \hat Y_8\hat I_2\hat $ 可以表示为</span><span class="sxs-lookup"><span data-stu-id="9f4cd-237">Thus the Hamiltonian term $0.4 \hat X_0 \hat Y_8\hat I_2\hat Z_1$ may be represented as</span></span>

```qsharp
let generatorIndexExample = GeneratorIndex(([1,2,0,3], [0.4]]), [0,8,2,1]);
```

<span data-ttu-id="9f4cd-238">`PauliEvolutionSet()` 是一种将此窗体的任何 `GeneratorIndex` 映射到具有以下签名的 `EvolutionUnitary` 的函数。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-238">The `PauliEvolutionSet()` is a function that maps any `GeneratorIndex` of this form to an `EvolutionUnitary` with the following signature.</span></span>

```qsharp
newtype EvolutionUnitary = ((Double, Qubit[]) => Unit is Adj + Ctl);
```

<span data-ttu-id="9f4cd-239">第一个参数表示一个时间段，此时间段将乘以单一演变的 `GeneratorIndex`中的系数。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-239">The first parameter represents a time-duration, that will be multiplied by the coefficient in the `GeneratorIndex`, of unitary evolution.</span></span> <span data-ttu-id="9f4cd-240">第二个参数是 qubit register 单一操作。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-240">The second parameter is the qubit register the unitary acts on.</span></span> 

### <a name="time-dependent-generators"></a><span data-ttu-id="9f4cd-241">与时间相关的生成器</span><span class="sxs-lookup"><span data-stu-id="9f4cd-241">Time-Dependent Generators</span></span> ###

<span data-ttu-id="9f4cd-242">在许多情况下，我们还对与时间相关的生成器进行建模，如 Schrödinger 公式 $ $ \begin{align} i\frac {d \ket{\psi （t）}} {d t} & = \hat H （t） \ket{\psi （t）}，\end{align} $ $，其中生成器 $ \hat H （t） $ 现在为与时间相关。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-242">In many cases, we are also interested in modelling time-dependent generators, as might occur in the Schrödinger equation $$ \begin{align} i\frac{d \ket{\psi(t)}}{d t} & = \hat H(t) \ket{\psi(t)}, \end{align} $$ where the generator $\hat H(t)$ is now time-dependent.</span></span> <span data-ttu-id="9f4cd-243">这种情况下，与此案例相关的独立生成器的扩展非常简单。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-243">The extension from the time-independent generators above to this case is straightforward.</span></span> <span data-ttu-id="9f4cd-244">不是使用固定 `GeneratorSystem` 描述所有时间 $t $ 的 Hamiltonian，而是使用 `GeneratorSystemTimeDependent` 用户定义类型。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-244">Rather than having a fixed `GeneratorSystem` describing the Hamiltonian for all times $t$, we instead have the `GeneratorSystemTimeDependent` user-defined type.</span></span>

```qsharp
newtype GeneratorSystemTimeDependent = (Double -> GeneratorSystem);
```

<span data-ttu-id="9f4cd-245">第一个参数是连续计划参数 $s \in [0，1] $，并且此类型的函数将返回该计划的 `GeneratorSystem`。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-245">The first parameter is a continuous schedule parameter $s\in [0,1]$, and functions of this type return a `GeneratorSystem` for that schedule.</span></span> <span data-ttu-id="9f4cd-246">请注意，计划参数可能与物理时间参数（例如 $s = t/T $）线性相关，以表示模拟的总时间 $T $。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-246">Note that the schedule parameter may be linearly related to the physical time parameter e.g. $s = t / T$, for some total time of simulation $T$.</span></span> <span data-ttu-id="9f4cd-247">但一般情况下不需要这样做。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-247">In general however, this need not be the case.</span></span>

<span data-ttu-id="9f4cd-248">同样，此生成器的完整说明需要 `EvolutionSet`，因此我们定义 `EvolutionSchedule` 用户定义类型。</span><span class="sxs-lookup"><span data-stu-id="9f4cd-248">Similarly, a complete description of this generator requires an `EvolutionSet`, and so we define an `EvolutionSchedule` user-defined type.</span></span>

```qsharp
newtype EvolutionSchedule = (EvolutionSet, GeneratorSystemTimeDependent);
```
