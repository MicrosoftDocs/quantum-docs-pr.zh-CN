---
title: 'Q # 标准库-prelude |Microsoft Docs'
description: 'Q # 标准库-prelude'
author: QuantumWriter
uid: microsoft.quantum.libraries.standard.prelude
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: dddb3d4a5ebcdca16da41a5ae5520d98ea900a7f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73183227"
---
# <a name="the-prelude"></a><span data-ttu-id="09eca-103">Prelude</span><span class="sxs-lookup"><span data-stu-id="09eca-103">The Prelude</span></span> #

<span data-ttu-id="09eca-104">"问答" 开发工具包附带的 Q # 编译器和目标计算机提供了一组内部函数和操作，可在 Q # 中编写量程程序时使用。</span><span class="sxs-lookup"><span data-stu-id="09eca-104">The Q# compiler and the target machines included with the Quantum Development Kit provide a set of intrinsic functions and operations that can be used when writing quantum programs in Q#.</span></span>

## <a name="intrinsic-operations-and-functions"></a><span data-ttu-id="09eca-105">内部操作和函数</span><span class="sxs-lookup"><span data-stu-id="09eca-105">Intrinsic Operations and Functions</span></span> ##

<span data-ttu-id="09eca-106">标准库中定义的内部操作大致分为以下几个类别之一：</span><span class="sxs-lookup"><span data-stu-id="09eca-106">The intrinsic operations defined in the standard library roughly fall into one of several categories:</span></span>

- <span data-ttu-id="09eca-107"><xref:microsoft.quantum.core> 命名空间中收集的基本传统函数。</span><span class="sxs-lookup"><span data-stu-id="09eca-107">Essential classical functions, collected in the <xref:microsoft.quantum.core> namespace.</span></span>
- <span data-ttu-id="09eca-108">表示由[Clifford 和 $T $ 关口](xref:microsoft.quantum.concepts.qubit)组成的 unitaries 的操作。</span><span class="sxs-lookup"><span data-stu-id="09eca-108">Operations representing unitaries composed of [Clifford and $T$ gates](xref:microsoft.quantum.concepts.qubit).</span></span>
- <span data-ttu-id="09eca-109">表示各种运算符旋转的操作。</span><span class="sxs-lookup"><span data-stu-id="09eca-109">Operations representing rotations about various operators.</span></span>
- <span data-ttu-id="09eca-110">实现度量的操作。</span><span class="sxs-lookup"><span data-stu-id="09eca-110">Operations implementing measurements.</span></span>

<span data-ttu-id="09eca-111">由于 Clifford + $T $ 入口集[通用](xref:microsoft.quantum.concepts.multiple-qubits)于量程计算，因此这些操作足以满足 negligibly 小错误中的任何量程算法的要求。</span><span class="sxs-lookup"><span data-stu-id="09eca-111">Since the Clifford + $T$ gate set is [universal](xref:microsoft.quantum.concepts.multiple-qubits) for quantum computing, these operations suffice to approximately implement any quantum algorithm within negligibly small error.</span></span>
<span data-ttu-id="09eca-112">通过同时提供旋转，Q # 允许程序员在单个 qubit 单一和 CNOT-CONTAINS 入口库中工作。</span><span class="sxs-lookup"><span data-stu-id="09eca-112">By providing rotations as well, Q# allows the programmer to work within the single qubit unitary and CNOT gate library.</span></span> <span data-ttu-id="09eca-113">此库更容易考虑，因为它不需要程序员直接学习 Clifford + $T $ 分解，而是因为存在用于将单个 qubit unitaries 编译到 Clifford 和 $T $ 入口的高效方法（请参阅[此处](xref:microsoft.quantum.more-information)）有关详细信息）。</span><span class="sxs-lookup"><span data-stu-id="09eca-113">This library is much easier to think about because it does not  require the programmer to directly express the Clifford + $T$ decomposition and because highly efficient methods exist for compiling single qubit unitaries into Clifford and $T$ gates (see [here](xref:microsoft.quantum.more-information) for more information).</span></span>

<span data-ttu-id="09eca-114">在可能的情况下，在 prelude 中定义的操作（作用于 qubits）允许应用 `Controlled` 变体，以便目标计算机将执行相应的分解。</span><span class="sxs-lookup"><span data-stu-id="09eca-114">Where possible, the operations defined in the prelude which act on qubits allow for applying the `Controlled` variant, such that the target machine will perform the appropriate decomposition.</span></span>

<span data-ttu-id="09eca-115">在 prelude 的此部分中定义的许多函数和操作都位于 @"microsoft.quantum.intrinsic" 命名空间中，因此，大多数 Q # 源文件会在初始命名空间声明之后立即具有 `open Microsoft.Quantum.Intrinsic;` 指令。</span><span class="sxs-lookup"><span data-stu-id="09eca-115">Many of the functions and operations defined in this portion of the prelude are in the @"microsoft.quantum.intrinsic" namespace, such that most Q# source files will have an `open Microsoft.Quantum.Intrinsic;` directive immediately following the initial namespace declaration.</span></span>
<span data-ttu-id="09eca-116">将自动打开 <xref:microsoft.quantum.core> 命名空间，这样就可以在没有 `open` 语句的情况下使用 <xref:microsoft.quantum.core.length> 等函数。</span><span class="sxs-lookup"><span data-stu-id="09eca-116">The <xref:microsoft.quantum.core> namespace is automatically opened, so that functions such as <xref:microsoft.quantum.core.length> can be used without an `open` statement at all.</span></span>

### <a name="common-single-qubit-unitary-operations"></a><span data-ttu-id="09eca-117">常见的单一 Qubit 单一操作</span><span class="sxs-lookup"><span data-stu-id="09eca-117">Common Single-Qubit Unitary Operations</span></span> ###

<span data-ttu-id="09eca-118">Prelude 还定义了很多常见[的 qubit 操作](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)。</span><span class="sxs-lookup"><span data-stu-id="09eca-118">The prelude also defines many common [single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span></span>
<span data-ttu-id="09eca-119">所有这些操作都允许 `Controlled` 和 `Adjoint` 函子。</span><span class="sxs-lookup"><span data-stu-id="09eca-119">All of these operations allow both the `Controlled` and `Adjoint` functors.</span></span>

#### <a name="pauli-operators"></a><span data-ttu-id="09eca-120">Pauli 运算符</span><span class="sxs-lookup"><span data-stu-id="09eca-120">Pauli Operators</span></span> ####

<span data-ttu-id="09eca-121"><xref:microsoft.quantum.intrinsic.x> 运算实现 Pauli $X $ operator。</span><span class="sxs-lookup"><span data-stu-id="09eca-121">The <xref:microsoft.quantum.intrinsic.x> operation implements the Pauli $X$ operator.</span></span>
<span data-ttu-id="09eca-122">这有时也称为 `NOT` 入口。</span><span class="sxs-lookup"><span data-stu-id="09eca-122">This is sometimes also known as the `NOT` gate.</span></span>
<span data-ttu-id="09eca-123">它 `(Qubit => Unit is Adj + Ctl)`签名。</span><span class="sxs-lookup"><span data-stu-id="09eca-123">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="09eca-124">它对应于 qubit 单一：</span><span class="sxs-lookup"><span data-stu-id="09eca-124">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="09eca-125">\begin{equation} \begin{bmatrix} 0 & 1 \\\\% FIXME：目前使用 quadwhack 黑客。</span><span class="sxs-lookup"><span data-stu-id="09eca-125">\begin{equation} \begin{bmatrix} 0 & 1 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="09eca-126">1 & 0 \end{bmatrix} \end{equation}</span><span class="sxs-lookup"><span data-stu-id="09eca-126">1 & 0 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="09eca-127"><xref:microsoft.quantum.intrinsic.y> 运算实现 Pauli $Y $ operator。</span><span class="sxs-lookup"><span data-stu-id="09eca-127">The <xref:microsoft.quantum.intrinsic.y> operation implements the Pauli $Y$ operator.</span></span>
<span data-ttu-id="09eca-128">它 `(Qubit => Unit is Adj + Ctl)`签名。</span><span class="sxs-lookup"><span data-stu-id="09eca-128">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="09eca-129">它对应于 qubit 单一：</span><span class="sxs-lookup"><span data-stu-id="09eca-129">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="09eca-130">\begin{equation} \begin{bmatrix} 0 &-i \\\\% FIXME：这目前使用 quadwhack 黑客。</span><span class="sxs-lookup"><span data-stu-id="09eca-130">\begin{equation} \begin{bmatrix} 0 & -i \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="09eca-131">我 & 0 \end{bmatrix} \end{equation}</span><span class="sxs-lookup"><span data-stu-id="09eca-131">i & 0 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="09eca-132"><xref:microsoft.quantum.intrinsic.z> 运算实现 Pauli $Z $ operator。</span><span class="sxs-lookup"><span data-stu-id="09eca-132">The <xref:microsoft.quantum.intrinsic.z> operation implements the Pauli $Z$ operator.</span></span>
<span data-ttu-id="09eca-133">它 `(Qubit => Unit is Adj + Ctl)`签名。</span><span class="sxs-lookup"><span data-stu-id="09eca-133">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="09eca-134">它对应于 qubit 单一：</span><span class="sxs-lookup"><span data-stu-id="09eca-134">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="09eca-135">\begin{equation} \begin{bmatrix} 1 & 0 \\\\% FIXME：此操作当前使用 quadwhack 黑客。</span><span class="sxs-lookup"><span data-stu-id="09eca-135">\begin{equation} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="09eca-136">0 &-1 \end{bmatrix} \end{equation}</span><span class="sxs-lookup"><span data-stu-id="09eca-136">0 & -1 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="09eca-137">下面我们看到映射到[Bloch 球体](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere)的这些转换（每种情况下的旋转轴突出显示为红色）：</span><span class="sxs-lookup"><span data-stu-id="09eca-137">Below we see these transformations mapped to the [Bloch sphere](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (the rotation axis in each case is highlighted red):</span></span>

![映射到 Bloch 球体的 Pauli 操作](~/media/prelude_pauliBloch.png)

<span data-ttu-id="09eca-139">需要注意的是，将相同的 Pauli 入口两次应用到同一个 qubit 会取消操作（因为现在已在表面上执行2π（360°）到 Bloch 球的完全旋转，因而回到了起始点）。</span><span class="sxs-lookup"><span data-stu-id="09eca-139">It is important to note that applying the same Pauli gate twice to the same qubit cancels out the operation (because you have now performed a full rotation of 2π (360°) over the surface to the Bloch Sphere, thus arriving back at the starting point).</span></span> <span data-ttu-id="09eca-140">接下来，我们将提供以下标识：</span><span class="sxs-lookup"><span data-stu-id="09eca-140">This brings us to the following identity:</span></span>

<span data-ttu-id="09eca-141">$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \boldone $ $</span><span class="sxs-lookup"><span data-stu-id="09eca-141">$$ X^2=Y^2=Z^2=\boldone $$</span></span>

<span data-ttu-id="09eca-142">这可以在 Bloch 球体上 visualised：</span><span class="sxs-lookup"><span data-stu-id="09eca-142">This can be visualised on the Bloch sphere:</span></span>

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a><span data-ttu-id="09eca-144">其他 Qubit Cliffords</span><span class="sxs-lookup"><span data-stu-id="09eca-144">Other Single-Qubit Cliffords</span></span> ####

<span data-ttu-id="09eca-145"><xref:microsoft.quantum.intrinsic.h> 操作实现 Hadamard 入口。</span><span class="sxs-lookup"><span data-stu-id="09eca-145">The <xref:microsoft.quantum.intrinsic.h> operation implements the Hadamard gate.</span></span>
<span data-ttu-id="09eca-146">这将交换目标 qubit 的 Pauli $X $ 和 $Z $ 轴，从而 $H \ket{0} = \ket{+} \mathrel{： =} （\ket{0} + \ket{1}）/\sqrt{2}$ 和 $H \ket{+} = \ket{0}$。</span><span class="sxs-lookup"><span data-stu-id="09eca-146">This interchanges the Pauli $X$ and $Z$ axes of the target qubit, such that $H\ket{0} = \ket{+} \mathrel{:=} (\ket{0} + \ket{1}) / \sqrt{2}$ and $H\ket{+} = \ket{0}$.</span></span>
<span data-ttu-id="09eca-147">它 `(Qubit => Unit is Adj + Ctl)`签名，并对应于 qubit 单一：</span><span class="sxs-lookup"><span data-stu-id="09eca-147">It has signature `(Qubit => Unit is Adj + Ctl)`, and corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="09eca-148">\begin{equation} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\% FIXME：这目前使用 quadwhack 黑客。</span><span class="sxs-lookup"><span data-stu-id="09eca-148">\begin{equation} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="09eca-149">1 &-1 \end{bmatrix} \end{equation}</span><span class="sxs-lookup"><span data-stu-id="09eca-149">1 & -1 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="09eca-150">Hadamard 入口特别重要，因为它可用于创建 $ \ket{0}$ 和 $ \ket{1}$ 状态的 superposition。</span><span class="sxs-lookup"><span data-stu-id="09eca-150">The Hadamard gate is particularly important as it can be used to create a superposition of the $\ket{0}$ and $\ket{1}$ states.</span></span> <span data-ttu-id="09eca-151">在 Bloch 球表示中，最简单的方法是将这种方式视为绕 x 轴旋转 $ \pi $ 弧度（$ 180 ^ \circ $），后跟围绕 y 轴的（顺时针）旋转，按 $ \ pi/2 $ 弧度（$ 90 ^ \circ $）：</span><span class="sxs-lookup"><span data-stu-id="09eca-151">In the Bloch sphere representation, it is easiest to think of this as a rotation of $\ket{\psi}$ around the x-axis by $\pi$ radians ($180^\circ$) followed by a (clockwise) rotation around the y-axis by $\pi/2$ radians ($90^\circ$):</span></span>

![映射到 Bloch 球体的 Hadamard 操作](~/media/prelude_hadamardBloch.png)

<span data-ttu-id="09eca-153"><xref:microsoft.quantum.intrinsic.s> 操作实现 $S $ 的阶段入口。</span><span class="sxs-lookup"><span data-stu-id="09eca-153">The <xref:microsoft.quantum.intrinsic.s> operation implements the phase gate $S$.</span></span>
<span data-ttu-id="09eca-154">这是 $Z Pauli $ operation 的 matrix 平方根。</span><span class="sxs-lookup"><span data-stu-id="09eca-154">This is the matrix square root of the Pauli $Z$ operation.</span></span>
<span data-ttu-id="09eca-155">也就是说，$S ^ 2 = Z $。</span><span class="sxs-lookup"><span data-stu-id="09eca-155">That is, $S^2 = Z$.</span></span>
<span data-ttu-id="09eca-156">它 `(Qubit => Unit is Adj + Ctl)`签名，并对应于 qubit 单一：</span><span class="sxs-lookup"><span data-stu-id="09eca-156">It has signature `(Qubit => Unit is Adj + Ctl)`, and corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="09eca-157">\begin{equation} \begin{bmatrix} 1 & 0 \\\\% FIXME：此操作当前使用 quadwhack 黑客。</span><span class="sxs-lookup"><span data-stu-id="09eca-157">\begin{equation} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="09eca-158">0 & i \end{bmatrix} \end{equation}</span><span class="sxs-lookup"><span data-stu-id="09eca-158">0 & i \end{bmatrix} \end{equation}</span></span>

#### <a name="rotations"></a><span data-ttu-id="09eca-159">旋转</span><span class="sxs-lookup"><span data-stu-id="09eca-159">Rotations</span></span> ####

<span data-ttu-id="09eca-160">除了上面的 Pauli 和 Clifford 操作，Q # prelude 还提供了多种表达旋转方式的方法。</span><span class="sxs-lookup"><span data-stu-id="09eca-160">In addition to the Pauli and Clifford operations above, the Q# prelude provides a variety of ways of expressing rotations.</span></span>
<span data-ttu-id="09eca-161">如[qubit 操作](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)中所述，旋转能力对于量子算法至关重要。</span><span class="sxs-lookup"><span data-stu-id="09eca-161">As described in [single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations), the ability to rotate is critical to quantum algorithms.</span></span>

<span data-ttu-id="09eca-162">首先，我们可以使用 $H $ 和 $T $ 入口（其中 $H $ 是 Hadamard 操作，其中 \begin{equation} T \mathrel{： =} \begin{bmatrix} 1 & 0 \\\\% FIXME：这当前使用四whack 黑客。</span><span class="sxs-lookup"><span data-stu-id="09eca-162">We start by recalling that we can express any single-qubit operation using the $H$ and $T$ gates, where $H$ is the Hadamard operation, and where \begin{equation} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quad back whack hack.</span></span>
<span data-ttu-id="09eca-163">0 & e ^ {i \pi/4} \end{bmatrix} \end{equation} 这是 <xref:microsoft.quantum.intrinsic.s> 操作的平方根，$T ^ 2 = S $。</span><span class="sxs-lookup"><span data-stu-id="09eca-163">0 & e^{i \pi / 4} \end{bmatrix} \end{equation} This is the square root of the <xref:microsoft.quantum.intrinsic.s> operation, such that $T^2 = S$.</span></span>
<span data-ttu-id="09eca-164">$T $ 入口反过来又由 <xref:microsoft.quantum.intrinsic.t> 操作实现，并具有签名 `(Qubit => Unit is Adj + Ctl)`，这表示它是对 qubit 的单一操作。</span><span class="sxs-lookup"><span data-stu-id="09eca-164">The $T$ gate is in turn implemented by the <xref:microsoft.quantum.intrinsic.t> operation, and has signature `(Qubit => Unit is Adj + Ctl)`, indicating that it is a unitary operation on a single-qubit.</span></span>

<span data-ttu-id="09eca-165">尽管这是足以描述任意单一 qubit 操作的原则，但不同的目标计算机可能具有更有效的方法来旋转 Pauli 运算符，因此 prelude 包括多种方法来 convienently表达此类旋转。</span><span class="sxs-lookup"><span data-stu-id="09eca-165">Even though this is in principle sufficient to describe any arbitrary single-qubit operation, different target machines may have more efficient representations for rotations about Pauli operators, such that the prelude includes a variety of ways to convienently express such rotations.</span></span>
<span data-ttu-id="09eca-166">其中最基本的方法是 <xref:microsoft.quantum.intrinsic.r> 操作，该操作实现绕指定的 Pauli 轴、\begin{equation} R （\sigma、\phi） \mathrel{： =} \exp （-i \phi \sigma/2）、\end{equation} （其中 $ \sigma $ 为 Pauli 运算符，$ \phi $ 为角度，其中 $\exp $ 表示矩阵指数。</span><span class="sxs-lookup"><span data-stu-id="09eca-166">The most basic of these is the <xref:microsoft.quantum.intrinsic.r> operation, which implements a rotation around a specified Pauli axis, \begin{equation} R(\sigma, \phi) \mathrel{:=} \exp(-i \phi \sigma / 2), \end{equation} where $\sigma$ is a Pauli operator, $\phi$ is an angle, and where $\exp$ represents the matrix exponential.</span></span>
<span data-ttu-id="09eca-167">它具有签名 `((Pauli, Double, Qubit) => Unit is Adj + Ctl)`，其中，输入的前两个部分表示 $R （\sigma，\phi） $ 指定单一运算符所需的传统参数 $ \sigma $ 和 $ \phi $。</span><span class="sxs-lookup"><span data-stu-id="09eca-167">It has signature `((Pauli, Double, Qubit) => Unit is Adj + Ctl)`, where the first two parts of the input represent the classical arguments $\sigma$ and $\phi$ needed to specify the unitary operator $R(\sigma, \phi)$.</span></span>
<span data-ttu-id="09eca-168">可以部分应用 $ \sigma $ 和 $ \phi $，以获取其类型为单一 qubit 单一的操作。</span><span class="sxs-lookup"><span data-stu-id="09eca-168">We can partially apply $\sigma$ and $\phi$ to obtain an operation whose type is that of a single-qubit unitary.</span></span>
<span data-ttu-id="09eca-169">例如，`R(PauliZ, PI() / 4, _)` 的类型 `(Qubit => Unit is Adj + Ctl)`。</span><span class="sxs-lookup"><span data-stu-id="09eca-169">For example, `R(PauliZ, PI() / 4, _)` has type `(Qubit => Unit is Adj + Ctl)`.</span></span>

> [!NOTE]
> <span data-ttu-id="09eca-170"><xref:microsoft.quantum.intrinsic.r> 运算将输入角度除以2并将其与-1 相乘。</span><span class="sxs-lookup"><span data-stu-id="09eca-170">The <xref:microsoft.quantum.intrinsic.r> operation divides the input angle by 2 and multiplies it by -1.</span></span>
> <span data-ttu-id="09eca-171">对于 $Z $ 旋转，这意味着 $ eigenstate{0}$ 通过 $-\phi/$2 旋转，$ \ket{1}$ eigenstate 将旋转 $ \phi/$2，以便 $ \ket{1}$ eigenstate 相对于 $ \phi{0}$ \ket 旋转 $ eigenstate $。</span><span class="sxs-lookup"><span data-stu-id="09eca-171">For $Z$ rotations, this means that the $\ket{0}$ eigenstate is rotated by $-\phi / 2$ and the $\ket{1}$ eigenstate is rotated by $\phi / 2$, so that the $\ket{1}$ eigenstate is rotated by $\phi$ relative to the $\ket{0}$ eigenstate.</span></span>
>
> <span data-ttu-id="09eca-172">具体而言，这意味着 `T` 和 `R(PauliZ, PI() / 8, _)` 只会因无关的[全局阶段](xref:microsoft.quantum.glossary#global-phase)而异。</span><span class="sxs-lookup"><span data-stu-id="09eca-172">In particular, this means that `T` and `R(PauliZ, PI() / 8, _)` differ only by an irrelevant [global phase](xref:microsoft.quantum.glossary#global-phase).</span></span>
> <span data-ttu-id="09eca-173">出于此原因，$T $ 有时称为 $ \frac{\pi}{8}$-入口。</span><span class="sxs-lookup"><span data-stu-id="09eca-173">For this reason, $T$ is sometimes known as the $\frac{\pi}{8}$-gate.</span></span>
>
> <span data-ttu-id="09eca-174">另请注意，围绕 `PauliI` 进行旋转仅适用于 $ \phi/$2 的全局阶段。</span><span class="sxs-lookup"><span data-stu-id="09eca-174">Note also that rotating around `PauliI` simply applies a global phase of $\phi / 2$.</span></span> <span data-ttu-id="09eca-175">尽管此类阶段与[概念文档](xref:microsoft.quantum.concepts.qubit)中的观点无关，但它们与受控 `PauliI` 旋转相关。</span><span class="sxs-lookup"><span data-stu-id="09eca-175">While such phases are irrelevant, as argued in [the conceptual documents](xref:microsoft.quantum.concepts.qubit), they are relevant for controlled `PauliI` rotations.</span></span>

<span data-ttu-id="09eca-176">在量程算法中，将循环表达为 dyadic 分式通常非常有用，例如，对于某些 $k \in \mathbb{Z} $ 和 $n \in $，$ \phi = \pi k/2 ^ n $。</span><span class="sxs-lookup"><span data-stu-id="09eca-176">Within quantum algorithms, it is often useful to express rotations as dyadic fractions, such that $\phi = \pi k / 2^n$ for some $k \in \mathbb{Z}$ and $n \in \mathbb{N}$.</span></span>
<span data-ttu-id="09eca-177"><xref:microsoft.quantum.intrinsic.rfrac> 操作使用此约定实现围绕指定 Pauli 轴的旋转。</span><span class="sxs-lookup"><span data-stu-id="09eca-177">The <xref:microsoft.quantum.intrinsic.rfrac> operation implements a rotation around a specified Pauli axis using this convention.</span></span>
<span data-ttu-id="09eca-178">它与 <xref:microsoft.quantum.intrinsic.r> 的不同之处在于，旋转角度指定为 `Int`类型的两个输入，解释为 dyadic 分数。</span><span class="sxs-lookup"><span data-stu-id="09eca-178">It differs from <xref:microsoft.quantum.intrinsic.r> in that the rotation angle is specified as two inputs of type `Int`, interpreted as a dyadic fraction.</span></span>
<span data-ttu-id="09eca-179">因此，`RFrac` 具有 `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)`签名。</span><span class="sxs-lookup"><span data-stu-id="09eca-179">Thus, `RFrac` has signature `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="09eca-180">它实现 qubit single $ \exp （i \pi k \sigma/2 ^ n） $，其中 $ \sigma $ 是与第一个参数对应的 Pauli 矩阵，$k $ 是第二个参数，$n $ 是第三个参数。</span><span class="sxs-lookup"><span data-stu-id="09eca-180">It implements the single-qubit unitary $\exp(i \pi k \sigma / 2^n)$, where $\sigma$ is the Pauli matrix corresponding to the first argument, $k$ is the second argument, and $n$ is the third argument.</span></span>
<span data-ttu-id="09eca-181">`RFrac(_,k,n,_)` 与 `R(_,-πk/2^n,_)`相同;请注意，角度是分数的*负值*。</span><span class="sxs-lookup"><span data-stu-id="09eca-181">`RFrac(_,k,n,_)` is the same as `R(_,-πk/2^n,_)`; note that the angle is the *negative* of the fraction.</span></span>

<span data-ttu-id="09eca-182"><xref:microsoft.quantum.intrinsic.rx> 运算实现绕 Pauli $X $ 轴的旋转。</span><span class="sxs-lookup"><span data-stu-id="09eca-182">The <xref:microsoft.quantum.intrinsic.rx> operation implements a rotation around the Pauli $X$ axis.</span></span>
<span data-ttu-id="09eca-183">它 `((Double, Qubit) => Unit is Adj + Ctl)`签名。</span><span class="sxs-lookup"><span data-stu-id="09eca-183">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="09eca-184">`Rx(_, _)` 与 `R(PauliX, _, _)`相同。</span><span class="sxs-lookup"><span data-stu-id="09eca-184">`Rx(_, _)` is the same as `R(PauliX, _, _)`.</span></span>

<span data-ttu-id="09eca-185"><xref:microsoft.quantum.intrinsic.ry> 运算实现绕 Pauli $Y $ 轴的旋转。</span><span class="sxs-lookup"><span data-stu-id="09eca-185">The <xref:microsoft.quantum.intrinsic.ry> operation implements a rotation around the Pauli $Y$ axis.</span></span>
<span data-ttu-id="09eca-186">它 `((Double, Qubit) => Unit is Adj + Ctl)`签名。</span><span class="sxs-lookup"><span data-stu-id="09eca-186">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="09eca-187">`Ry(_, _)` 与 `R(PauliY,_ , _)`相同。</span><span class="sxs-lookup"><span data-stu-id="09eca-187">`Ry(_, _)` is the same as `R(PauliY,_ , _)`.</span></span>

<span data-ttu-id="09eca-188"><xref:microsoft.quantum.intrinsic.rz> 运算实现绕 Pauli $Z $ 轴的旋转。</span><span class="sxs-lookup"><span data-stu-id="09eca-188">The <xref:microsoft.quantum.intrinsic.rz> operation implements a rotation around the Pauli $Z$ axis.</span></span>
<span data-ttu-id="09eca-189">它 `((Double, Qubit) => Unit is Adj + Ctl)`签名。</span><span class="sxs-lookup"><span data-stu-id="09eca-189">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="09eca-190">`Rz(_, _)` 与 `R(PauliZ, _, _)`相同。</span><span class="sxs-lookup"><span data-stu-id="09eca-190">`Rz(_, _)` is the same as `R(PauliZ, _, _)`.</span></span>

<span data-ttu-id="09eca-191"><xref:microsoft.quantum.intrinsic.r1> 操作按给定的量实现对 $ \ket{1}$ $ $Z $ 的 $-$1 eigenstate 的旋转。</span><span class="sxs-lookup"><span data-stu-id="09eca-191">The <xref:microsoft.quantum.intrinsic.r1> operation implements a rotation by the given amount around $\ket{1}$, the $-1$ eigenstate of $Z$.</span></span>
<span data-ttu-id="09eca-192">它 `((Double, Qubit) => Unit is Adj + Ctl)`签名。</span><span class="sxs-lookup"><span data-stu-id="09eca-192">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="09eca-193">`R1(phi,_)` 与 `R(PauliZ,phi,_)` 后跟 `R(PauliI,-phi,_)`相同。</span><span class="sxs-lookup"><span data-stu-id="09eca-193">`R1(phi,_)` is the same as `R(PauliZ,phi,_)` followed by `R(PauliI,-phi,_)`.</span></span>

<span data-ttu-id="09eca-194"><xref:microsoft.quantum.intrinsic.r1frac> 运算按照 Z = 1 eigenstate 的给定量实现小数旋转。</span><span class="sxs-lookup"><span data-stu-id="09eca-194">The <xref:microsoft.quantum.intrinsic.r1frac> operation implements a fractional rotation by the given amount around the Z=1 eigenstate.</span></span>
<span data-ttu-id="09eca-195">它 `((Int,Int, Qubit) => Unit is Adj + Ctl)`签名。</span><span class="sxs-lookup"><span data-stu-id="09eca-195">It has signature `((Int,Int, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="09eca-196">`R1Frac(k,n,_)` 与 `RFrac(PauliZ,-k.n+1,_)` 后跟 `RFrac(PauliI,k,n+1,_)`相同。</span><span class="sxs-lookup"><span data-stu-id="09eca-196">`R1Frac(k,n,_)` is the same as `RFrac(PauliZ,-k.n+1,_)` followed by `RFrac(PauliI,k,n+1,_)`.</span></span>

<span data-ttu-id="09eca-197">下面显示了一个旋转操作示例（围绕此实例中的 Pauli $Z $ axis），如下所示：</span><span class="sxs-lookup"><span data-stu-id="09eca-197">An example of a rotation operation (around the Pauli $Z$ axis, in this instance) mapped onto the Bloch sphere is shown below:</span></span>

![映射到 Bloch 球体的旋转操作](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a><span data-ttu-id="09eca-199">多 Qubit 操作</span><span class="sxs-lookup"><span data-stu-id="09eca-199">Multi-Qubit Operations</span></span> ####

<span data-ttu-id="09eca-200">除了上面的单一 qubit 操作外，prelude 还定义了多个多 qubit 操作。</span><span class="sxs-lookup"><span data-stu-id="09eca-200">In addition to the single-qubit operations above, the prelude also defines several multi-qubit operations.</span></span>

<span data-ttu-id="09eca-201">首先，<xref:microsoft.quantum.intrinsic.cnot> 操作执行标准受控`NOT` 门，\begin{equation} \operatorname{CNOT} \mathrel{： =} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1\\\\ 0 & 0 & 1 & 0 \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="09eca-201">First, the <xref:microsoft.quantum.intrinsic.cnot> operation performs a standard controlled-`NOT` gate, \begin{equation} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}.</span></span>
<span data-ttu-id="09eca-202">\end{equation} 它具有 `((Qubit, Qubit) => Unit is Adj + Ctl)`的签名，表示 $ \operatorname{CNOT} $ act unitarily 两个单独的 qubits。</span><span class="sxs-lookup"><span data-stu-id="09eca-202">\end{equation} It has signature `((Qubit, Qubit) => Unit is Adj + Ctl)`, representing that $\operatorname{CNOT}$ acts unitarily on two individual qubits.</span></span>
<span data-ttu-id="09eca-203">`CNOT(q1, q2)` 与 `(Controlled X)([q1], q2)`相同。</span><span class="sxs-lookup"><span data-stu-id="09eca-203">`CNOT(q1, q2)` is the same as `(Controlled X)([q1], q2)`.</span></span>
<span data-ttu-id="09eca-204">由于 `Controlled` 函子允许对寄存器进行控制，因此，我们使用数组文本 `[q1]` 指示只需要一个控件。</span><span class="sxs-lookup"><span data-stu-id="09eca-204">Since the `Controlled` functor allows for controlling on a register, we use the array literal `[q1]` to indicate that we want only the one control.</span></span>

<span data-ttu-id="09eca-205"><xref:microsoft.quantum.intrinsic.ccnot> 操作执行双向控制的非入口，有时也称为 Toffoli 入口。</span><span class="sxs-lookup"><span data-stu-id="09eca-205">The <xref:microsoft.quantum.intrinsic.ccnot> operation performs doubly-controlled NOT gate, sometimes also known as the Toffoli gate.</span></span>
<span data-ttu-id="09eca-206">它 `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)`签名。</span><span class="sxs-lookup"><span data-stu-id="09eca-206">It has signature `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="09eca-207">`CCNOT(q1, q2, q3)` 与 `(Controlled X)([q1, q2], q3)`相同。</span><span class="sxs-lookup"><span data-stu-id="09eca-207">`CCNOT(q1, q2, q3)` is the same as `(Controlled X)([q1, q2], q3)`.</span></span>

<span data-ttu-id="09eca-208"><xref:microsoft.quantum.intrinsic.swap> 操作将交换两个 qubits 的量程状态。</span><span class="sxs-lookup"><span data-stu-id="09eca-208">The <xref:microsoft.quantum.intrinsic.swap> operation swaps the quantum states of two qubits.</span></span>
<span data-ttu-id="09eca-209">也就是说，它实现了单一矩阵 \begin{equation} \operatorname{SWAP} \mathrel{： =} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & \\\\ &0 & 0 & 1 \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="09eca-209">That is, it implements the unitary matrix \begin{equation} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}.</span></span>
<span data-ttu-id="09eca-210">\end{equation} 签名 `((Qubit, Qubit) => Unit is Adj + Ctl)`。</span><span class="sxs-lookup"><span data-stu-id="09eca-210">\end{equation} It has signature `((Qubit, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="09eca-211">`SWAP(q1,q2)` 等效于 `CNOT(q1, q2)` 后跟 `CNOT(q2, q1)`，然后 `CNOT(q1, q2)`。</span><span class="sxs-lookup"><span data-stu-id="09eca-211">`SWAP(q1,q2)` is equivalent to `CNOT(q1, q2)` followed by `CNOT(q2, q1)` and then `CNOT(q1, q2)`.</span></span>

> [!NOTE]
> <span data-ttu-id="09eca-212">交换*门与使用*类型 `Qubit[]`重新排列变量的元素不同。</span><span class="sxs-lookup"><span data-stu-id="09eca-212">The SWAP gate is *not* the same as rearranging the elements of a variable with type `Qubit[]`.</span></span>
> <span data-ttu-id="09eca-213">应用 `SWAP(q1, q2)` 会导致 `q1` 和 `q2`所引用的 qubits 的状态发生更改，而 `let swappedRegister = [q2, q1];` 只影响我们引用这些 qubits 的方式。</span><span class="sxs-lookup"><span data-stu-id="09eca-213">Applying `SWAP(q1, q2)` causes a change to the state of the qubits referred to by `q1` and `q2`, while `let swappedRegister = [q2, q1];` only affects how we refer to those qubits.</span></span>
> <span data-ttu-id="09eca-214">此外，`(Controlled SWAP)([q0], (q1, q2))` 允许 `SWAP` 在第三个 qubit 的状态下进行条件，我们无法通过重新排列元素来表示。</span><span class="sxs-lookup"><span data-stu-id="09eca-214">Moreover, `(Controlled SWAP)([q0], (q1, q2))` allows for `SWAP` to be conditioned on the state of a third qubit, which we cannot represent by rearranging elements.</span></span>
> <span data-ttu-id="09eca-215">受控交换门（也称为 Fredkin 入口）的强大功能足以包含所有传统计算。</span><span class="sxs-lookup"><span data-stu-id="09eca-215">The controlled-SWAP gate, also known as the Fredkin gate, is powerful enough to include all classical computation.</span></span>

<span data-ttu-id="09eca-216">最后，prelude 提供两个用于表示多 qubit Pauli 运算符的指数的操作。</span><span class="sxs-lookup"><span data-stu-id="09eca-216">Finally, the prelude provides two operations for representing exponentials of multi-qubit Pauli operators.</span></span>
<span data-ttu-id="09eca-217"><xref:microsoft.quantum.intrinsic.exp> 操作基于 Pauli 矩阵的 tensor 产品执行旋转，如多 qubit 单一 \begin{equation} \operatorname{Exp} （\vec{\sigma}，\phi） \mathrel{： =} \exp\left （i \phi \sigma_0 \otimes \sigma_1 \otimes \cdots \otimes \sigma_n \right）、\end{equation} （其中 $ \vec{\sigma} = （\sigma_0，\sigma_1，\dots ..，\sigma_n） $ 是一系列单 qubit Pauli 运算符，其中 $ \phi $ 为角度。</span><span class="sxs-lookup"><span data-stu-id="09eca-217">The <xref:microsoft.quantum.intrinsic.exp> operation performs a rotation based on a tensor product of Pauli matrices, as represented by the multi-qubit unitary \begin{equation} \operatorname{Exp}(\vec{\sigma}, \phi) \mathrel{:=} \exp\left(i \phi \sigma_0 \otimes \sigma_1 \otimes \cdots \otimes \sigma_n \right), \end{equation} where $\vec{\sigma} = (\sigma_0, \sigma_1, \dots, \sigma_n)$ is a sequence of single-qubit Pauli operators, and where $\phi$ is an angle.</span></span>
<span data-ttu-id="09eca-218">`Exp` 旋转将 $ \vec{\sigma} $ 表示为 `Pauli` 元素的数组，使其具有签名 `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`。</span><span class="sxs-lookup"><span data-stu-id="09eca-218">The `Exp` rotation represents $\vec{\sigma}$ as an array of `Pauli` elements, such that it has signature `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="09eca-219"><xref:microsoft.quantum.intrinsic.expfrac> 操作使用上述 dyadic 分数表示法执行相同的旋转。</span><span class="sxs-lookup"><span data-stu-id="09eca-219">The <xref:microsoft.quantum.intrinsic.expfrac> operation performs the same rotation, using the dyadic fraction notation discussed above.</span></span>
<span data-ttu-id="09eca-220">它 `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)`签名。</span><span class="sxs-lookup"><span data-stu-id="09eca-220">It has signature `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)`.</span></span>

> [!WARNING]
> <span data-ttu-id="09eca-221">Pauli 运算符的 tensor 产品的指数与指数运算符 Pauli 的 tensor 产品不同。</span><span class="sxs-lookup"><span data-stu-id="09eca-221">Exponentials of the tensor product of Pauli operators are not the same as tensor products of the exponentials of Pauli operators.</span></span>
> <span data-ttu-id="09eca-222">也就是说，$e ^ {i （Z \otimes Z） \phi} \ne e ^ {i Z \phi} \otimes e ^ {i Z \phi} $。</span><span class="sxs-lookup"><span data-stu-id="09eca-222">That is, $e^{i (Z \otimes Z) \phi} \ne e^{i Z \phi} \otimes e^{i Z \phi}$.</span></span>

### <a name="measurements"></a><span data-ttu-id="09eca-223">度量</span><span class="sxs-lookup"><span data-stu-id="09eca-223">Measurements</span></span> ###

<span data-ttu-id="09eca-224">度量时，所测量的运算符的 + 1 eigenvalue 对应于 `Zero` 结果，并将-1 eigenvalue 到 `One` 结果。</span><span class="sxs-lookup"><span data-stu-id="09eca-224">When measuring, the +1 eigenvalue of the operator being measured corresponds to a `Zero` result, and the -1 eigenvalue to a `One` result.</span></span>

> [!NOTE]
> <span data-ttu-id="09eca-225">虽然这种约定看起来很奇怪，但它具有两种非常好的优点。</span><span class="sxs-lookup"><span data-stu-id="09eca-225">While this convention might seem odd, it has two very nice advantages.</span></span>
> <span data-ttu-id="09eca-226">首先，观察结果 $ \ket{0}$ 由 `Result` 值 `Zero`表示，同时观察 $ \ket{1}$ 对应于 `One`。</span><span class="sxs-lookup"><span data-stu-id="09eca-226">First, observing the outcome $\ket{0}$ is represented by the `Result` value `Zero`, while observing $\ket{1}$ corresponds to `One`.</span></span>
> <span data-ttu-id="09eca-227">其次，我们可以写出 eigenvalue $ \lambda $ 对应于结果 $r $ 是 $ \lambda = （-1） ^ r $。</span><span class="sxs-lookup"><span data-stu-id="09eca-227">Second, we can write out that the eigenvalue $\lambda$ corresponding to a result $r$ is $\lambda = (-1)^r$.</span></span>

<span data-ttu-id="09eca-228">度量运算既不支持 `Adjoint` 也不支持 `Controlled` 函子。</span><span class="sxs-lookup"><span data-stu-id="09eca-228">Measurement operations support neither the `Adjoint` nor the `Controlled` functor.</span></span>

<span data-ttu-id="09eca-229"><xref:microsoft.quantum.intrinsic.measure> 操作在 Pauli 运算符的指定产品中执行一个或多个 qubits 的联合度量。</span><span class="sxs-lookup"><span data-stu-id="09eca-229">The <xref:microsoft.quantum.intrinsic.measure> operation performs a joint measurement of one or more qubits in the specified product of Pauli operators.</span></span>
<span data-ttu-id="09eca-230">如果 Pauli 数组和 qubit 数组的长度不同，则操作将失败。</span><span class="sxs-lookup"><span data-stu-id="09eca-230">If the Pauli array and qubit array are different lengths, then the operation fails.</span></span>
<span data-ttu-id="09eca-231">`Measure` 具有 `((Pauli[], Qubit[]) => Result)`签名。</span><span class="sxs-lookup"><span data-stu-id="09eca-231">`Measure` has signature `((Pauli[], Qubit[]) => Result)`.</span></span>

<span data-ttu-id="09eca-232">请注意，联合度量不同于分别测量每个 qubit。</span><span class="sxs-lookup"><span data-stu-id="09eca-232">Note that a joint measurement is not the same as measuring each qubit individually.</span></span>
<span data-ttu-id="09eca-233">例如，请考虑状态 $ \ket{11} = \ket{1} \otimes \ket{1} = X\otimes X \ket{00}$。</span><span class="sxs-lookup"><span data-stu-id="09eca-233">For example, consider the state $\ket{11} = \ket{1} \otimes \ket{1} = X\otimes X \ket{00}$.</span></span>
<span data-ttu-id="09eca-234">$Z 每个 _0 $ 和分别 _1 $ $Z，得到 $r _0 = $1 和 $r _1 = $1 的结果。</span><span class="sxs-lookup"><span data-stu-id="09eca-234">Measuring $Z_0$ and $Z_1$ each individually, we get the results $r_0 = 1$ and $r_1 = 1$.</span></span>
<span data-ttu-id="09eca-235">$Z 度量 Z_1 $，但我们得到了单一结果 $r _ {\textrm{joint}} = $0，表示 $ \ket{11}$ 的 pairity 为正值。</span><span class="sxs-lookup"><span data-stu-id="09eca-235">Measuring $Z_0 Z_1$, however, we get the single result $r_{\textrm{joint}} = 0$, representing that the pairity of $\ket{11}$ is positive.</span></span>
<span data-ttu-id="09eca-236">采用不同的方式： $ （-1） ^ {r_0 + r_1} = （-1） ^ r_ {\textrm{joint}}） $。</span><span class="sxs-lookup"><span data-stu-id="09eca-236">Put differently, $(-1)^{r_0 + r_1} = (-1)^r_{\textrm{joint}})$.</span></span>
<span data-ttu-id="09eca-237">严重的是，由于我们*只*会从此度量值中了解奇偶校验，因此将保留在 superposition 的 2 2-qubit 状态之间、$ \ket{00}$ 和 $ \ket{11}$ 之间显示的任何量程信息。</span><span class="sxs-lookup"><span data-stu-id="09eca-237">Critically, since we *only* learn the parity from this measurement, any quantum information represented in the superposition between the two two-qubit states of positive parity, $\ket{00}$ and $\ket{11}$, is preserved.</span></span>
<span data-ttu-id="09eca-238">此属性将在以后介绍错误更正。</span><span class="sxs-lookup"><span data-stu-id="09eca-238">This property will be essential later, as we discuss error correction.</span></span>

<span data-ttu-id="09eca-239">为方便起见，prelude 还提供了两个其他操作来测量 qubits。</span><span class="sxs-lookup"><span data-stu-id="09eca-239">For convenience, the prelude also provides two other operations for measuring qubits.</span></span>
<span data-ttu-id="09eca-240">首先，由于执行 qubit 度量值非常常见，因此 prelude 定义了这种情况的简写形式。</span><span class="sxs-lookup"><span data-stu-id="09eca-240">First, since performing single-qubit measurements is quite common, the prelude defines a shorthand for this case.</span></span>
<span data-ttu-id="09eca-241"><xref:microsoft.quantum.intrinsic.m> 操作对单个 qubit 上的 Pauli $Z $ 运算符进行度量，并具有签名 `(Qubit => Result)`。</span><span class="sxs-lookup"><span data-stu-id="09eca-241">The <xref:microsoft.quantum.intrinsic.m> operation measures the Pauli $Z$ operator on a single qubit, and has signature `(Qubit => Result)`.</span></span>
<span data-ttu-id="09eca-242">`M(q)` 等效于 `Measure([PauliZ], [q])`。</span><span class="sxs-lookup"><span data-stu-id="09eca-242">`M(q)` is equivalent to `Measure([PauliZ], [q])`.</span></span>

<span data-ttu-id="09eca-243"><xref:microsoft.quantum.measurement.multim>*分别*对每个 qubits 数组的每个数组 $Z $ 运算符进行度量，返回为每个 qubit 获取的 `Result` 值的*数组*。</span><span class="sxs-lookup"><span data-stu-id="09eca-243">The <xref:microsoft.quantum.measurement.multim> measures the Pauli $Z$ operator *separately* on each of an array of qubits, returning the *array* of `Result` values obtained for each qubit.</span></span>
<span data-ttu-id="09eca-244">在某些情况下，这可以进行优化。</span><span class="sxs-lookup"><span data-stu-id="09eca-244">In some cases this can be optimized.</span></span> <span data-ttu-id="09eca-245">它有签名（`Qubit[] => Result[])`。</span><span class="sxs-lookup"><span data-stu-id="09eca-245">It has signature (`Qubit[] => Result[])`.</span></span>
<span data-ttu-id="09eca-246">`MultiM(qs)` 等效于：</span><span class="sxs-lookup"><span data-stu-id="09eca-246">`MultiM(qs)` is equivalent to:</span></span>

```qsharp
mutable rs = new Result[Length(qs)];
for (index in 0..Length(qs)-1)
{
    set rs[index] = M(qs[index]);
}
return rs;
```

## <a name="extension-functions-and-operations"></a><span data-ttu-id="09eca-247">扩展函数和操作</span><span class="sxs-lookup"><span data-stu-id="09eca-247">Extension Functions and Operations</span></span> ##

<span data-ttu-id="09eca-248">此外，prelude 在 .NET 级别定义一组丰富的数学和类型转换函数，以便在 Q # 代码中使用。</span><span class="sxs-lookup"><span data-stu-id="09eca-248">In addition, the prelude defines a rich set of mathematical and type conversion functions at the .NET level for use within Q# code.</span></span>
<span data-ttu-id="09eca-249">例如，<xref:microsoft.quantum.extensions.math> 命名空间定义有用的操作，如 <xref:microsoft.quantum.extensions.math.sin> 和 <xref:microsoft.quantum.extensions.math.log>。</span><span class="sxs-lookup"><span data-stu-id="09eca-249">For instance, the <xref:microsoft.quantum.extensions.math> namespace defines useful operations such as <xref:microsoft.quantum.extensions.math.sin> and <xref:microsoft.quantum.extensions.math.log>.</span></span>
<span data-ttu-id="09eca-250">量程开发工具包提供的实现使用传统的 .NET 基类库，因此可能需要在量程程序与其传统驱动程序之间进行额外的通信往返。</span><span class="sxs-lookup"><span data-stu-id="09eca-250">The implementation provided by the Quantum Development Kit uses the classical .NET base class library, and thus may involve an additional communications round trip between quantum programs and their classical drivers.</span></span>
<span data-ttu-id="09eca-251">虽然这对于本地模拟器不存在问题，但在将远程模拟器或实际硬件用作目标计算机时，这可能是一个性能问题。</span><span class="sxs-lookup"><span data-stu-id="09eca-251">While this does not present a problem for a local simulator, this can be a performance issue when using a remote simulator or actual hardware as a target machine.</span></span>
<span data-ttu-id="09eca-252">也就是说，单个目标计算机可以通过使用对该特定系统更有效的版本替代这些操作来缓解此性能影响。</span><span class="sxs-lookup"><span data-stu-id="09eca-252">That said, an individual target machine may mitigate this performance impact by overriding these operations with versions that are more efficient for that particular system.</span></span>

### <a name="math"></a><span data-ttu-id="09eca-253">符号</span><span class="sxs-lookup"><span data-stu-id="09eca-253">Math</span></span> ###

<span data-ttu-id="09eca-254"><xref:microsoft.quantum.extensions.math> 命名空间提供 .NET 基类库[`System.Math` 类](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1)中许多有用的函数。</span><span class="sxs-lookup"><span data-stu-id="09eca-254">The <xref:microsoft.quantum.extensions.math> namespace provides many useful functions from the .NET base class library's [`System.Math` class](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1).</span></span>
<span data-ttu-id="09eca-255">这些函数的使用方式与任何其他 Q # 函数的使用方式相同：</span><span class="sxs-lookup"><span data-stu-id="09eca-255">These functions can be used in the same manner as any other Q# functions:</span></span>

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

<span data-ttu-id="09eca-256">如果已基于其参数的类型重载了某个 .NET 静态方法，则相应的 Q # 函数将使用一个后缀（表示其输入的类型）进行批注：</span><span class="sxs-lookup"><span data-stu-id="09eca-256">Where a .NET static method has been overloaded based on the type of its arguments, the corresponding Q# function is annotated with a suffix indicating the type of its input:</span></span>

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a><span data-ttu-id="09eca-257">按位运算</span><span class="sxs-lookup"><span data-stu-id="09eca-257">Bitwise Operations</span></span> ###

<span data-ttu-id="09eca-258">最后，<xref:microsoft.quantum.extensions.bitwise> 命名空间提供了几个有用的函数，用于通过按位运算符来处理整数。</span><span class="sxs-lookup"><span data-stu-id="09eca-258">Finally, the <xref:microsoft.quantum.extensions.bitwise> namespace provides several useful functions for manipulating integers through bitwise operators.</span></span>
<span data-ttu-id="09eca-259">例如，<xref:microsoft.quantum.extensions.bitwise.parity> 将整数的按位奇偶校验作为另一个整数返回。</span><span class="sxs-lookup"><span data-stu-id="09eca-259">For instance, <xref:microsoft.quantum.extensions.bitwise.parity> returns the bitwise parity of an integer as another integer.</span></span>
