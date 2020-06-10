---
title: 量程计算术语表
description: 量程计算中使用的常用术语、操作和对象的词汇表。
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
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
ms.openlocfilehash: 2a3b1fe480b9886d0c11255bb1b1e01402dce4f7
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630089"
---
# <a name="quantum-computing-glossary"></a><span data-ttu-id="f8364-103">量程计算术语表</span><span class="sxs-lookup"><span data-stu-id="f8364-103">Quantum computing glossary</span></span>

## <a name="adjoint"></a><span data-ttu-id="f8364-104">Adjoint</span><span class="sxs-lookup"><span data-stu-id="f8364-104">Adjoint</span></span>

<span data-ttu-id="f8364-105">[操作](xref:microsoft.quantum.glossary#operation)的复杂共轭转置。</span><span class="sxs-lookup"><span data-stu-id="f8364-105">The complex conjugate transpose of an [operation](xref:microsoft.quantum.glossary#operation).</span></span> <span data-ttu-id="f8364-106">对于实现[单一](xref:microsoft.quantum.glossary#unitary-operator)运算符的操作，adjoint 是操作的反向，由剑号符号指示。</span><span class="sxs-lookup"><span data-stu-id="f8364-106">For operations that implement a [unitary](xref:microsoft.quantum.glossary#unitary-operator) operator, the adjoint is the inverse of the operation and is indicated by a dagger symbol.</span></span> <span data-ttu-id="f8364-107">例如，如果操作 `U` 表示 $U 的单一运算符 $ ，则 `Adjoint U` 表示 $U ^ \dagger $ 。</span><span class="sxs-lookup"><span data-stu-id="f8364-107">For example, if the operation `U` represents the unitary operator $U$, then `Adjoint U` represents $U^\dagger$.</span></span> <span data-ttu-id="f8364-108">有关详细信息，请参阅[Adjoint](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations)。</span><span class="sxs-lookup"><span data-stu-id="f8364-108">For more information, see [Adjoint](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span></span>

## <a name="ancilla"></a><span data-ttu-id="f8364-109">Ancilla</span><span class="sxs-lookup"><span data-stu-id="f8364-109">Ancilla</span></span>

<span data-ttu-id="f8364-110">一个[qubit](xref:microsoft.quantum.glossary#qubit) ，它充当量子计算机的临时内存，并根据需要分配和取消分配。</span><span class="sxs-lookup"><span data-stu-id="f8364-110">A [qubit](xref:microsoft.quantum.glossary#qubit) that serves as temporary memory for a quantum computer and is allocated and de-allocated as needed.</span></span>  <span data-ttu-id="f8364-111">有关详细信息，请参阅[多个 qubits](xref:microsoft.quantum.concepts.multiple-qubits)。</span><span class="sxs-lookup"><span data-stu-id="f8364-111">For more information, see [Multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

## <a name="bell-state"></a><span data-ttu-id="f8364-112">电铃状态</span><span class="sxs-lookup"><span data-stu-id="f8364-112">Bell state</span></span>

<span data-ttu-id="f8364-113">四个特定最大化[放大](xref:microsoft.quantum.glossary#entanglement)[量程](xref:microsoft.quantum.glossary#quantum-state)中的一种状态，分为两 qubits。</span><span class="sxs-lookup"><span data-stu-id="f8364-113">One of four specific maximally [entangled](xref:microsoft.quantum.glossary#entanglement) [quantum states](xref:microsoft.quantum.glossary#quantum-state) of two qubits.</span></span> <span data-ttu-id="f8364-114">四种状态定义为 $ \ket { \ beta_ {ij } } = （\Mathbb{I } \Otimes X ^ iZ ^ j）（\ket{00 } + \ket{11 } ）/\sqrt{2 } $。</span><span class="sxs-lookup"><span data-stu-id="f8364-114">The four states are defined $\ket{\beta_{ij}} = (\mathbb{I} \otimes X^iZ^j) (\ket{00} + \ket{11}) / \sqrt{2}$.</span></span> <span data-ttu-id="f8364-115">电铃状态也称为[EPR 对](xref:microsoft.quantum.glossary#epr-pair)。</span><span class="sxs-lookup"><span data-stu-id="f8364-115">A Bell state is also known as an [EPR pair](xref:microsoft.quantum.glossary#epr-pair).</span></span>

## <a name="bloch-sphere"></a><span data-ttu-id="f8364-116">Bloch 球体</span><span class="sxs-lookup"><span data-stu-id="f8364-116">Bloch sphere</span></span>

<span data-ttu-id="f8364-117">[Qubit](xref:microsoft.quantum.glossary#qubit) [量程状态](xref:microsoft.quantum.glossary#quantum-state)的图形表示形式，作为三维单位球体中的点。</span><span class="sxs-lookup"><span data-stu-id="f8364-117">A graphical representation of a single-[qubit](xref:microsoft.quantum.glossary#qubit) [quantum state](xref:microsoft.quantum.glossary#quantum-state) as a point in a three-dimensional unit sphere.</span></span> <span data-ttu-id="f8364-118">有关详细信息，请参阅[使用 Bloch 球体直观显示 Qubits 和转换](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere)。</span><span class="sxs-lookup"><span data-stu-id="f8364-118">For more information, see  [Visualizing Qubits and Transformations using the Bloch Sphere](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span></span>

## <a name="callable"></a><span data-ttu-id="f8364-119">多次</span><span class="sxs-lookup"><span data-stu-id="f8364-119">Callable</span></span>

<span data-ttu-id="f8364-120">Q # 语言中的[操作](xref:microsoft.quantum.glossary#operation)或[函数](xref:microsoft.quantum.glossary#function)。</span><span class="sxs-lookup"><span data-stu-id="f8364-120">An [operation](xref:microsoft.quantum.glossary#operation) or [function](xref:microsoft.quantum.glossary#function) in the Q# language.</span></span> <span data-ttu-id="f8364-121">有关详细信息，请参阅[操作和函数](xref:microsoft.quantum.guide.operationsfunctions)。</span><span class="sxs-lookup"><span data-stu-id="f8364-121">For more information, see [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="clifford-group"></a><span data-ttu-id="f8364-122">Clifford 组</span><span class="sxs-lookup"><span data-stu-id="f8364-122">Clifford group</span></span>

<span data-ttu-id="f8364-123">一组操作，这些操作占用[Bloch 球](xref:microsoft.quantum.glossary#bloch-sphere)的 octants 并影响[Pauli 运算符](xref:microsoft.quantum.glossary#pauli-operators)的效果。</span><span class="sxs-lookup"><span data-stu-id="f8364-123">The set of operations that occupy the octants of the [Bloch sphere](xref:microsoft.quantum.glossary#bloch-sphere) and effect permutations of the [Pauli operators](xref:microsoft.quantum.glossary#pauli-operators).</span></span> <span data-ttu-id="f8364-124">其中包括操作[$X $ ](xref:microsoft.quantum.intrinsic.x)、 [$Y $ ](xref:microsoft.quantum.intrinsic.y)、 [$Z $ ](xref:microsoft.quantum.intrinsic.z)、 [$H $ ](xref:microsoft.quantum.intrinsic.h)和[$S $ ](xref:microsoft.quantum.intrinsic.s)。</span><span class="sxs-lookup"><span data-stu-id="f8364-124">These include the operations [$X$](xref:microsoft.quantum.intrinsic.x), [$Y$](xref:microsoft.quantum.intrinsic.y), [$Z$](xref:microsoft.quantum.intrinsic.z), [$H$](xref:microsoft.quantum.intrinsic.h) and [$S$](xref:microsoft.quantum.intrinsic.s).</span></span>

## <a name="controlled"></a><span data-ttu-id="f8364-125">操控</span><span class="sxs-lookup"><span data-stu-id="f8364-125">Controlled</span></span>

<span data-ttu-id="f8364-126">一个量程[操作](xref:microsoft.quantum.glossary#operation)，它将一个或多个[qubits](xref:microsoft.quantum.glossary#qubit)作为目标操作的启用程序。</span><span class="sxs-lookup"><span data-stu-id="f8364-126">A quantum [operation](xref:microsoft.quantum.glossary#operation) that takes one or more [qubits](xref:microsoft.quantum.glossary#qubit) as enablers for the target operation.</span></span> <span data-ttu-id="f8364-127">有关详细信息，请参阅[受控和 adjoint 操作](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations)。</span><span class="sxs-lookup"><span data-stu-id="f8364-127">For more information, see [Controlled and adjoint operations](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).</span></span>

## <a name="dirac-notation"></a><span data-ttu-id="f8364-128">Dirac 表示法</span><span class="sxs-lookup"><span data-stu-id="f8364-128">Dirac Notation</span></span>

<span data-ttu-id="f8364-129">简化[量程状态](xref:microsoft.quantum.glossary#quantum-state)表示形式的符号简写，也称为*寄存器-票证*表示法。</span><span class="sxs-lookup"><span data-stu-id="f8364-129">A symbolic shorthand that simplifies the representation of [quantum states](xref:microsoft.quantum.glossary#quantum-state), also called *bra-ket* notation.</span></span>  <span data-ttu-id="f8364-130">*寄存器*部分表示一个行向量，例如 $ \bra{A } = \begin{ bmatrix } {_1 } & {_2 } \end{ bmatrix } $，*票证*部分表示一个列向量，$ \ket{B } = \begin{ bmatrix } B {_1 } \\ \\ B {_2 } \end{ bmatrix } $。</span><span class="sxs-lookup"><span data-stu-id="f8364-130">The *bra* portion represents a row vector, for example  $\bra{A} = \begin{bmatrix} A{_1} & A{_2} \end{bmatrix}$ and the *ket* portion represents a column vector, $\ket{B} = \begin{bmatrix} B{_1} \\\\ B{_2} \end{bmatrix}$.</span></span> <span data-ttu-id="f8364-131">有关详细信息，请参阅[Dirac 表示法](xref:microsoft.quantum.concepts.dirac)。</span><span class="sxs-lookup"><span data-stu-id="f8364-131">For more information, see [Dirac Notation](xref:microsoft.quantum.concepts.dirac).</span></span>

## <a name="eigenvalue"></a><span data-ttu-id="f8364-132">Eigenvalue</span><span class="sxs-lookup"><span data-stu-id="f8364-132">Eigenvalue</span></span>

<span data-ttu-id="f8364-133">转换应用程序更改给定转换的[eigenvector](xref:microsoft.quantum.glossary#eigenvector)的量的因子。</span><span class="sxs-lookup"><span data-stu-id="f8364-133">The factor by which the magnitude of an [eigenvector](xref:microsoft.quantum.glossary#eigenvector) of a given transformation is changed by the application of the transformation.</span></span>  <span data-ttu-id="f8364-134">给定正方形 matrix $M $ 和 eigenvector $v $ ，然后 $Mv = cv $ ，其中 $c $ 是 eigenvalue，可以是任意参数的复数。</span><span class="sxs-lookup"><span data-stu-id="f8364-134">Given a square matrix $M$ and an eigenvector $v$, then $Mv = cv$, where $c$ is the eigenvalue and can be a complex number of any argument.</span></span> <span data-ttu-id="f8364-135">有关详细信息，请参阅[高级矩阵概念](xref:microsoft.quantum.concepts.matrix-advanced)。</span><span class="sxs-lookup"><span data-stu-id="f8364-135">For more information, see [Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).</span></span>

## <a name="eigenvector"></a><span data-ttu-id="f8364-136">Eigenvector</span><span class="sxs-lookup"><span data-stu-id="f8364-136">Eigenvector</span></span>

<span data-ttu-id="f8364-137">一个向量，其方向与给定的转换保持不变，并且其量的值由与该向量的[eigenvalue](xref:microsoft.quantum.glossary#eigenvalue)相对应的系数更改。</span><span class="sxs-lookup"><span data-stu-id="f8364-137">A vector whose direction is unchanged by a given transformation and whose magnitude is changed by a factor corresponding to that vector's [eigenvalue](xref:microsoft.quantum.glossary#eigenvalue).</span></span> <span data-ttu-id="f8364-138">给定正方形 matrix $M $ 和 eigenvalue $c $ ，然后 $Mv = cv $ ，其中 $v $ 是矩阵的 eigenvector，可以是任意参数的复数。</span><span class="sxs-lookup"><span data-stu-id="f8364-138">Given a square matrix $M$ and an eigenvalue $c$, then $Mv = cv$, where $v$ is an eigenvector of the matrix and can be a complex number of any argument.</span></span> <span data-ttu-id="f8364-139">有关详细信息，请参阅[高级矩阵概念](xref:microsoft.quantum.concepts.matrix-advanced)。</span><span class="sxs-lookup"><span data-stu-id="f8364-139">For more information, see [Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).</span></span>

## <a name="entanglement"></a><span data-ttu-id="f8364-140">纠缠</span><span class="sxs-lookup"><span data-stu-id="f8364-140">Entanglement</span></span>

<span data-ttu-id="f8364-141">量程粒子（如[qubits](xref:microsoft.quantum.glossary#qubit)）可以连接或*放大*，以使它们不能彼此独立地进行描述。</span><span class="sxs-lookup"><span data-stu-id="f8364-141">Quantum particles, such as [qubits](xref:microsoft.quantum.glossary#qubit), can be connected or *entangled* such that they cannot be described independently from each other.</span></span> <span data-ttu-id="f8364-142">即使它们被无限远地分离，它们的度量结果也是相关的。</span><span class="sxs-lookup"><span data-stu-id="f8364-142">Their measurement results are correlated even when they are separated infinitely far away.</span></span> <span data-ttu-id="f8364-143">牵连对于[测量](xref:microsoft.quantum.glossary#measurement)qubit 的[状态](xref:microsoft.quantum.glossary#quantum-state)至关重要。</span><span class="sxs-lookup"><span data-stu-id="f8364-143">Entanglement is essential to [measuring](xref:microsoft.quantum.glossary#measurement) the [state](xref:microsoft.quantum.glossary#quantum-state) of a qubit.</span></span>  <span data-ttu-id="f8364-144">有关详细信息，请参阅[高级矩阵概念](xref:microsoft.quantum.concepts.matrix-advanced)。</span><span class="sxs-lookup"><span data-stu-id="f8364-144">For more information, see [Advanced matrix concepts](xref:microsoft.quantum.concepts.matrix-advanced).</span></span>

## <a name="epr-pair"></a><span data-ttu-id="f8364-145">EPR 对</span><span class="sxs-lookup"><span data-stu-id="f8364-145">EPR pair</span></span>

<span data-ttu-id="f8364-146">四个特定最大化放大量程中的一种[状态](xref:microsoft.quantum.glossary#quantum-state)，分为两[qubits](xref:microsoft.quantum.glossary#qubit)。</span><span class="sxs-lookup"><span data-stu-id="f8364-146">One of four specific maximally entangled [quantum states](xref:microsoft.quantum.glossary#quantum-state) of two [qubits](xref:microsoft.quantum.glossary#qubit).</span></span> <span data-ttu-id="f8364-147">四种状态定义为 $ \ket { \ beta_ {ij } } = （\Mathbb{1 } \Otimes X ^ iZ ^ j）（\ket{00 } + \ket{11 } ）/\sqrt{2 } $。</span><span class="sxs-lookup"><span data-stu-id="f8364-147">The four states are defined $\ket{\beta_{ij}} = (\mathbb{1} \otimes X^iZ^j) (\ket{00} + \ket{11}) / \sqrt{2}$.</span></span> <span data-ttu-id="f8364-148">EPR 对也称为[钟形状态](xref:microsoft.quantum.glossary#bell-state)</span><span class="sxs-lookup"><span data-stu-id="f8364-148">An EPR pair is also known as a [Bell state](xref:microsoft.quantum.glossary#bell-state)</span></span>

## <a name="evolution"></a><span data-ttu-id="f8364-149">演变</span><span class="sxs-lookup"><span data-stu-id="f8364-149">Evolution</span></span>

<span data-ttu-id="f8364-150">[量程状态](xref:microsoft.quantum.glossary#quantum-state)随时间变化的方式。</span><span class="sxs-lookup"><span data-stu-id="f8364-150">How a [quantum state](xref:microsoft.quantum.glossary#quantum-state) changes over time.</span></span> <span data-ttu-id="f8364-151">有关详细信息，请参阅[Matrix 指数](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials)。</span><span class="sxs-lookup"><span data-stu-id="f8364-151">For more information, see [Matrix exponentials](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).</span></span>

## <a name="function"></a><span data-ttu-id="f8364-152">函数</span><span class="sxs-lookup"><span data-stu-id="f8364-152">Function</span></span>
<span data-ttu-id="f8364-153">Q # 语言中纯传统（非量程）的一种子例程。</span><span class="sxs-lookup"><span data-stu-id="f8364-153">A type of subroutine in the Q# language that is purely classical (non-quantum).</span></span> <span data-ttu-id="f8364-154">当函数在量程算法中使用时，它们不能作用于[qubits](xref:microsoft.quantum.glossary#qubit)或调用[操作](xref:microsoft.quantum.glossary#operation)。</span><span class="sxs-lookup"><span data-stu-id="f8364-154">While functions are used within quantum algorithms, they cannot act on [qubits](xref:microsoft.quantum.glossary#qubit) or call [operations](xref:microsoft.quantum.glossary#operation).</span></span> <span data-ttu-id="f8364-155">有关详细信息，请参阅[操作和函数](xref:microsoft.quantum.guide.operationsfunctions)。</span><span class="sxs-lookup"><span data-stu-id="f8364-155">For more information, see [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="gate"></a><span data-ttu-id="f8364-156">护</span><span class="sxs-lookup"><span data-stu-id="f8364-156">Gate</span></span>

<span data-ttu-id="f8364-157">基于传统逻辑入口的概念的量程[操作](xref:microsoft.quantum.glossary#operation)的旧术语。</span><span class="sxs-lookup"><span data-stu-id="f8364-157">A legacy term for a quantum [operation](xref:microsoft.quantum.glossary#operation), based on the concept of classical logic gates.</span></span> <span data-ttu-id="f8364-158">[量程线路](xref:microsoft.quantum.glossary#quantum-circuit-diagram)是入口（或操作）的网络，基于传统逻辑电路的类似概念。</span><span class="sxs-lookup"><span data-stu-id="f8364-158">A [quantum circuit](xref:microsoft.quantum.glossary#quantum-circuit-diagram) is a network of gates (or operations), based on the similar concept of classical logic circuits.</span></span>

## <a name="global-phase"></a><span data-ttu-id="f8364-159">全局阶段</span><span class="sxs-lookup"><span data-stu-id="f8364-159">Global phase</span></span>

<span data-ttu-id="f8364-160">如果两个[状态](xref:microsoft.quantum.glossary#quantum-state)的最大值为 $e ^ {i $ 的复数的倍数 \phi } ，则认为它们在全局阶段中是不同的。</span><span class="sxs-lookup"><span data-stu-id="f8364-160">When two [states](xref:microsoft.quantum.glossary#quantum-state) are identical up to a multiple of a complex number $e^{i\phi}$, they are said to differ up to a global phase.</span></span> <span data-ttu-id="f8364-161">与本地阶段不同，全局阶段不能通过任何[measurment](xref:microsoft.quantum.glossary#measurement)来观察。</span><span class="sxs-lookup"><span data-stu-id="f8364-161">Unlike local phases, global phases cannot be observed through any [measurment](xref:microsoft.quantum.glossary#measurement).</span></span> <span data-ttu-id="f8364-162">有关详细信息，请参阅[Qubit](xref:microsoft.quantum.concepts.qubit)。</span><span class="sxs-lookup"><span data-stu-id="f8364-162">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span>

## <a name="hadamard"></a><span data-ttu-id="f8364-163">Hadamard</span><span class="sxs-lookup"><span data-stu-id="f8364-163">Hadamard</span></span>

<span data-ttu-id="f8364-164">Hadamard 操作（也称为 Hadamard 入口或转换）作用于单个[qubit](xref:microsoft.quantum.glossary#qubit) ， [superposition](xref:microsoft.quantum.glossary#superposition) } } 如果 \ket{0 最初处于 $ \ket{1 $ 状态，则会将其放在 $ qubit $ 或 $ \ket{0 $ 的偶数 superposition 中 } 。</span><span class="sxs-lookup"><span data-stu-id="f8364-164">The Hadamard operation (also referred to as the Hadamard gate or transform) acts on a single [qubit](xref:microsoft.quantum.glossary#qubit) and puts it in an even [superposition](xref:microsoft.quantum.glossary#superposition) of $\ket{0}$ or $\ket{1}$ if the qubit is initially in the $\ket{0}$ state.</span></span> <span data-ttu-id="f8364-165">在 Q # 中，此操作由预定义的操作应用 [`H`](xref:microsoft.quantum.intrinsic.h) 。</span><span class="sxs-lookup"><span data-stu-id="f8364-165">In Q#, this operation is applied by the pre-defined [`H`](xref:microsoft.quantum.intrinsic.h) operation.</span></span>

## <a name="immutable"></a><span data-ttu-id="f8364-166">不可变</span><span class="sxs-lookup"><span data-stu-id="f8364-166">Immutable</span></span>

<span data-ttu-id="f8364-167">不能更改其值的变量。</span><span class="sxs-lookup"><span data-stu-id="f8364-167">A variable whose value cannot be changed.</span></span> <span data-ttu-id="f8364-168">使用关键字创建的 Q # 中的不可变变量 `let` 。</span><span class="sxs-lookup"><span data-stu-id="f8364-168">An immutable variable in Q# is created using the `let` keyword.</span></span> <span data-ttu-id="f8364-169">若要声明*可*更改的变量，请使用[可变](xref:microsoft.quantum.glossary#immutable)关键字进行声明，使用 `set` 关键字修改该值。</span><span class="sxs-lookup"><span data-stu-id="f8364-169">To declare variables that *can* be changed, use the [mutable](xref:microsoft.quantum.glossary#immutable) keyword to declare and the `set` keyword to modify the value.</span></span> 

## <a name="measurement"></a><span data-ttu-id="f8364-170">度量</span><span class="sxs-lookup"><span data-stu-id="f8364-170">Measurement</span></span>

<span data-ttu-id="f8364-171">[Qubit](xref:microsoft.quantum.glossary#qubit) （或一组 qubits）的操作，该操作生成观察结果，实际上获取的是传统位。</span><span class="sxs-lookup"><span data-stu-id="f8364-171">A manipulation of a [qubit](xref:microsoft.quantum.glossary#qubit) (or set of qubits) that yields the result of an observation, in effect obtaining a classical bit.</span></span> <span data-ttu-id="f8364-172">有关详细信息，请参阅[Qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit)。</span><span class="sxs-lookup"><span data-stu-id="f8364-172">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).</span></span>

## <a name="mutable"></a><span data-ttu-id="f8364-173">可变</span><span class="sxs-lookup"><span data-stu-id="f8364-173">Mutable</span></span>

<span data-ttu-id="f8364-174">其值在创建后可以更改的变量。</span><span class="sxs-lookup"><span data-stu-id="f8364-174">A variable whose value may be changed after it is created.</span></span> <span data-ttu-id="f8364-175">使用关键字声明的 Q # 中的可变变量 `mutable` ，并使用关键字进行修改 `set` 。</span><span class="sxs-lookup"><span data-stu-id="f8364-175">A mutable variable in Q# is declared using the `mutable` keyword and modified using the `set` keyword.</span></span> <span data-ttu-id="f8364-176">用关键字创建的变量 `let` 是[不可变](xref:microsoft.quantum.glossary#immutable)的，不能更改其值。</span><span class="sxs-lookup"><span data-stu-id="f8364-176">Variables created with the `let` keyword are [immutable](xref:microsoft.quantum.glossary#immutable) and their value cannot be changed.</span></span>

## <a name="namespace"></a><span data-ttu-id="f8364-177">命名空间</span><span class="sxs-lookup"><span data-stu-id="f8364-177">Namespace</span></span>

<span data-ttu-id="f8364-178">相关名称集合（即[操作](xref:microsoft.quantum.glossary#operation)、[函数](xref:microsoft.quantum.glossary#function)和[用户定义类型](xref:microsoft.quantum.glossary#user-defined-type)）的标签。</span><span class="sxs-lookup"><span data-stu-id="f8364-178">A label for a collection of related names (i.e., [operations](xref:microsoft.quantum.glossary#operation), [functions](xref:microsoft.quantum.glossary#function), and [user-defined types](xref:microsoft.quantum.glossary#user-defined-type)).</span></span> <span data-ttu-id="f8364-179">例如，命名空间为 ""。[准备](xref:microsoft.quantum.preparation)标签在标准库中定义的所有符号都有助于准备初始状态。</span><span class="sxs-lookup"><span data-stu-id="f8364-179">For instance the namespace [Microsoft.Quantum.Preparation](xref:microsoft.quantum.preparation) labels all of the symbols defined in the standard library that help with preparing initial states.</span></span>

## <a name="operation"></a><span data-ttu-id="f8364-180">Operation</span><span class="sxs-lookup"><span data-stu-id="f8364-180">Operation</span></span>

<span data-ttu-id="f8364-181">Q # 中的量程执行的基本单位。</span><span class="sxs-lookup"><span data-stu-id="f8364-181">The basic unit of quantum execution in Q#.</span></span> <span data-ttu-id="f8364-182">它大致等效于 C、c + + 或 Python 中的函数或 c # 或 Java 中的静态方法。</span><span class="sxs-lookup"><span data-stu-id="f8364-182">It is roughly equivalent to a function in C, C++ or Python, or a static method in C# or Java.</span></span> <span data-ttu-id="f8364-183">有关详细信息，请参阅[操作和函数](xref:microsoft.quantum.guide.operationsfunctions)。</span><span class="sxs-lookup"><span data-stu-id="f8364-183">For more information, see [Operations and functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="operator-application"></a><span data-ttu-id="f8364-184">操作员应用程序</span><span class="sxs-lookup"><span data-stu-id="f8364-184">Operator application</span></span>

<span data-ttu-id="f8364-185">执行量程运算。</span><span class="sxs-lookup"><span data-stu-id="f8364-185">Performing a quantum operation.</span></span> <span data-ttu-id="f8364-186">这通常会将单一矩阵应用于当前的量程状态向量。</span><span class="sxs-lookup"><span data-stu-id="f8364-186">This typically applies a unitary matrix to the current quantum state vector.</span></span>

## <a name="oracle"></a><span data-ttu-id="f8364-187">Oracle</span><span class="sxs-lookup"><span data-stu-id="f8364-187">Oracle</span></span>

<span data-ttu-id="f8364-188">在运行时提供量程算法的数据相关信息的子例程。</span><span class="sxs-lookup"><span data-stu-id="f8364-188">A subroutine that provides data-dependent information to a quantum algorithm at runtime.</span></span> <span data-ttu-id="f8364-189">通常，目标是提供与 superposition 中的输入对应的输出[superposition](xref:microsoft.quantum.glossary#superposition) 。</span><span class="sxs-lookup"><span data-stu-id="f8364-189">Typically, the goal is to provide a [superposition](xref:microsoft.quantum.glossary#superposition) of outputs corresponding to inputs that are in superposition.</span></span> <span data-ttu-id="f8364-190">有关详细信息，请参阅[Oracles](xref:microsoft.quantum.libraries.data-structures#oracles)。</span><span class="sxs-lookup"><span data-stu-id="f8364-190">For more information, see [Oracles](xref:microsoft.quantum.libraries.data-structures#oracles).</span></span>

## <a name="partial-application"></a><span data-ttu-id="f8364-191">部分应用程序</span><span class="sxs-lookup"><span data-stu-id="f8364-191">Partial application</span></span>

<span data-ttu-id="f8364-192">调用不包含所有必需输入的[函数](xref:microsoft.quantum.glossary#function)或[操作](xref:microsoft.quantum.glossary#operation)。</span><span class="sxs-lookup"><span data-stu-id="f8364-192">Calling a [function](xref:microsoft.quantum.glossary#function) or [operation](xref:microsoft.quantum.glossary#operation) without all the required inputs.</span></span> <span data-ttu-id="f8364-193">这会返回一个新的可[调用](xref:microsoft.quantum.glossary#callable)，它只需要在未来的应用程序中提供缺少的参数（由下划线指示）。</span><span class="sxs-lookup"><span data-stu-id="f8364-193">This returns a new [callable](xref:microsoft.quantum.glossary#callable) that only needs the missing parameters (indicated by an underscore) to be supplied during a future application.</span></span> <span data-ttu-id="f8364-194">例如，假设函数 `MyFunc(x : int, y : int) : int {return x + y;}` 可部分应用于新函数 `let NewFunc = MyFunc(_, 3)` 。</span><span class="sxs-lookup"><span data-stu-id="f8364-194">For example, given the function `MyFunc(x : int, y : int) : int {return x + y;}` you can partially apply it to a new function `let NewFunc = MyFunc(_, 3)`.</span></span> <span data-ttu-id="f8364-195">然后，你可以在以后使用缺少的参数 `NewFunc(2)` （返回值*5*）调用新函数。</span><span class="sxs-lookup"><span data-stu-id="f8364-195">You can then call the new function at a later time with the missing parameter `NewFunc(2)` which returns the value *5*.</span></span>  <span data-ttu-id="f8364-196">有关详细信息，请参阅[部分应用程序](xref:microsoft.quantum.guide.operationsfunctions#partial-application)。</span><span class="sxs-lookup"><span data-stu-id="f8364-196">For more information, see [Partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application).</span></span>

## <a name="pauli-operators"></a><span data-ttu-id="f8364-197">Pauli 运算符</span><span class="sxs-lookup"><span data-stu-id="f8364-197">Pauli operators</span></span>

<span data-ttu-id="f8364-198">由三个 2 x 2 个单一矩阵组成的一组 `X` ，称为 `Y` 和一个 `Z` 量程运算。</span><span class="sxs-lookup"><span data-stu-id="f8364-198">A set of three 2 x 2 unitary matrices known as the `X`, `Y` and `Z` quantum operations.</span></span> <span data-ttu-id="f8364-199">标识矩阵 $I $ 也通常包含在集中。</span><span class="sxs-lookup"><span data-stu-id="f8364-199">The identity matrix, $I$, is often included in the set as well.</span></span>  <span data-ttu-id="f8364-200">$I = \begin{ bmatrix } 1 & 0 \\ \\ 0 & 1 \end{ bmatrix } $，$X = \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } $，$Y = \begin{ bmatrix } 0 &-i \\ \\ & 0 \end{ bmatrix } $，$Z = \begin{ bmatrix } 1 & 0 \\ \\ 0 &-1 \end{ bmatrix } $。</span><span class="sxs-lookup"><span data-stu-id="f8364-200">$I = \begin{bmatrix} 1 & 0 \\\\ 0 & 1 \end{bmatrix}$, $X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix}$, $Y = \begin{bmatrix} 0 & -i \\\\ i & 0 \end{bmatrix}$, $Z = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}$.</span></span>   <span data-ttu-id="f8364-201">有关详细信息，请参阅[qubit 操作](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)。</span><span class="sxs-lookup"><span data-stu-id="f8364-201">For more information, see [Single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span></span>

## <a name="quantum-circuit-diagram"></a><span data-ttu-id="f8364-202">量程线路关系图</span><span class="sxs-lookup"><span data-stu-id="f8364-202">Quantum circuit diagram</span></span>

<span data-ttu-id="f8364-203">用于以图形方式表示简单量程程序的[操作](xref:microsoft.quantum.glossary#operation)（或[入口](xref:microsoft.quantum.glossary#gate)）序列的一种方法，例如</span><span class="sxs-lookup"><span data-stu-id="f8364-203">A method to graphically represent the sequence of [operations](xref:microsoft.quantum.glossary#operation) (or [gates](xref:microsoft.quantum.glossary#gate)) for simple quantum programs, for example</span></span> 

![示例线路图示](~/media/qpe.png)<span data-ttu-id="f8364-205">.</span><span class="sxs-lookup"><span data-stu-id="f8364-205">.</span></span> 

<span data-ttu-id="f8364-206">有关详细信息，请参阅[量子线路](xref:microsoft.quantum.concepts.circuits)。</span><span class="sxs-lookup"><span data-stu-id="f8364-206">For more information, see [Quantum circuits](xref:microsoft.quantum.concepts.circuits).</span></span>

## <a name="quantum-libraries"></a><span data-ttu-id="f8364-207">量程库</span><span class="sxs-lookup"><span data-stu-id="f8364-207">Quantum libraries</span></span>

<span data-ttu-id="f8364-208">用于创建 Q # 程序的[操作](xref:microsoft.quantum.glossary#operation)、[函数](xref:microsoft.quantum.glossary#function)和[用户定义类型](xref:microsoft.quantum.glossary#user-defined-type)的集合。</span><span class="sxs-lookup"><span data-stu-id="f8364-208">Collections of [operations](xref:microsoft.quantum.glossary#operation), [functions](xref:microsoft.quantum.glossary#function) and [user-defined types](xref:microsoft.quantum.glossary#user-defined-type) for creating Q# programs.</span></span> <span data-ttu-id="f8364-209">默认情况下，将安装[标准库](xref:microsoft.quantum.libraries.standard.intro)。</span><span class="sxs-lookup"><span data-stu-id="f8364-209">The [Standard library](xref:microsoft.quantum.libraries.standard.intro) is installed by default.</span></span> <span data-ttu-id="f8364-210">可用的其他库包括[化学库](xref:microsoft.quantum.chemistry.concepts.intro)、数字[库](xref:microsoft.quantum.numerics.intro)和[机器学习库](xref:microsoft.quantum.machine-learning.concepts.intro)。</span><span class="sxs-lookup"><span data-stu-id="f8364-210">Other libraries available are the [Chemistry library](xref:microsoft.quantum.chemistry.concepts.intro), the [Numerics library](xref:microsoft.quantum.numerics.intro) and the [Machine learning library](xref:microsoft.quantum.machine-learning.concepts.intro).</span></span>

## <a name="quantum-state"></a><span data-ttu-id="f8364-211">量程状态</span><span class="sxs-lookup"><span data-stu-id="f8364-211">Quantum state</span></span>

<span data-ttu-id="f8364-212">隔离的量程系统的准确状态，可以从中提取[度量](xref:microsoft.quantum.glossary#measurement)概率。</span><span class="sxs-lookup"><span data-stu-id="f8364-212">The precise state of an isolated quantum system, from which [measurement](xref:microsoft.quantum.glossary#measurement) probabilities can be extracted.</span></span> <span data-ttu-id="f8364-213">在量程计算中，量程模拟器使用此信息来模拟 qubits 响应操作的方式。</span><span class="sxs-lookup"><span data-stu-id="f8364-213">In quantum computing, the quantum simulator uses this information to simulate how qubits respond to operations.</span></span> <span data-ttu-id="f8364-214">有关详细信息，请参阅[Qubit](xref:microsoft.quantum.concepts.qubit)。</span><span class="sxs-lookup"><span data-stu-id="f8364-214">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span>

## <a name="qubit"></a><span data-ttu-id="f8364-215">Qubit</span><span class="sxs-lookup"><span data-stu-id="f8364-215">Qubit</span></span>

<span data-ttu-id="f8364-216">量程信息的基本单位，类似于传统计算中的*位*。</span><span class="sxs-lookup"><span data-stu-id="f8364-216">A basic unit of quantum information, analogous to a *bit* in classical computing.</span></span> <span data-ttu-id="f8364-217">有关详细信息，请参阅[Qubit](xref:microsoft.quantum.concepts.qubit)。</span><span class="sxs-lookup"><span data-stu-id="f8364-217">For more information, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span>

## <a name="repeat-until-success"></a><span data-ttu-id="f8364-218">重复执行-成功</span><span class="sxs-lookup"><span data-stu-id="f8364-218">Repeat-until-success</span></span>

<span data-ttu-id="f8364-219">Probabilistic 成功的量程算法。</span><span class="sxs-lookup"><span data-stu-id="f8364-219">A quantum algorithm that probabilistically succeeds.</span></span> <span data-ttu-id="f8364-220">如果失败，例程将重试，直到成功（或已达到限制）。</span><span class="sxs-lookup"><span data-stu-id="f8364-220">Upon failure, the routine will retry until successful (or a limit has been reached).</span></span> <span data-ttu-id="f8364-221">有关详细信息，请参阅[重复到成功（ru）](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop)</span><span class="sxs-lookup"><span data-stu-id="f8364-221">For more information, see [Repeat Until Success (RUS)](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop)</span></span>

## <a name="standard-libraries"></a><span data-ttu-id="f8364-222">标准库</span><span class="sxs-lookup"><span data-stu-id="f8364-222">Standard libraries</span></span>

<span data-ttu-id="f8364-223">安装期间与 Q # 编译器一起安装的[操作](xref:microsoft.quantum.glossary#operation)、[函数](xref:microsoft.quantum.glossary#function)和[用户定义类型](xref:microsoft.quantum.glossary#user-defined-type)。</span><span class="sxs-lookup"><span data-stu-id="f8364-223">[Operations](xref:microsoft.quantum.glossary#operation), [functions](xref:microsoft.quantum.glossary#function) and [user-defined types](xref:microsoft.quantum.glossary#user-defined-type) that are installed along with the Q# compiler during installation.</span></span> <span data-ttu-id="f8364-224">标准库实现对于目标计算机而言不可知。</span><span class="sxs-lookup"><span data-stu-id="f8364-224">The standard library implementation is agnostic with respect to target machines.</span></span> <span data-ttu-id="f8364-225">有关详细信息，请参阅[标准库](xref:microsoft.quantum.libraries.standard.intro)。</span><span class="sxs-lookup"><span data-stu-id="f8364-225">For more information, see [Standard libraries](xref:microsoft.quantum.libraries.standard.intro).</span></span>

## <a name="superposition"></a><span data-ttu-id="f8364-226">Superposition</span><span class="sxs-lookup"><span data-stu-id="f8364-226">Superposition</span></span>

<span data-ttu-id="f8364-227">量程计算中的概念计算， [qubit](xref:microsoft.quantum.glossary#qubit)是两个状态的线性组合： $ \ket{0 } $ 和 $ \ket{1 } $，直到[测量](xref:microsoft.quantum.glossary#measurement)为止。</span><span class="sxs-lookup"><span data-stu-id="f8364-227">The concept in quantum computing that a [qubit](xref:microsoft.quantum.glossary#qubit) is a linear combination of two states, $\ket{0}$ and $\ket{1}$, until it is [measured](xref:microsoft.quantum.glossary#measurement).</span></span>  <span data-ttu-id="f8364-228">有关详细信息，请参阅[了解量程计算](xref:microsoft.quantum.overview.understanding)。</span><span class="sxs-lookup"><span data-stu-id="f8364-228">For more information, see [Understanding quantum computing](xref:microsoft.quantum.overview.understanding).</span></span>

## <a name="target-machine"></a><span data-ttu-id="f8364-229">目标计算机</span><span class="sxs-lookup"><span data-stu-id="f8364-229">Target machine</span></span>

<span data-ttu-id="f8364-230">一种编译目标，它将抽象的量程程序降低到硬件或模拟。</span><span class="sxs-lookup"><span data-stu-id="f8364-230">A compilation target that lowers an abstract quantum program towards hardware or simulation.</span></span> <span data-ttu-id="f8364-231">这通常包括重新编写以实现多种目的，包括门替换、用于纠错的编码、几何布局和其他功能。</span><span class="sxs-lookup"><span data-stu-id="f8364-231">This typically include re-writes for many purposes including gate replacement, encoding for error correction, geometric layout and others.</span></span> <span data-ttu-id="f8364-232">有关详细信息，请参阅[量程模拟器和主机应用程序](xref:microsoft.quantum.machines)。</span><span class="sxs-lookup"><span data-stu-id="f8364-232">For more information, see [Quantum simulators and host applications](xref:microsoft.quantum.machines).</span></span>

## <a name="teleportation"></a><span data-ttu-id="f8364-233">隐形传送</span><span class="sxs-lookup"><span data-stu-id="f8364-233">Teleportation</span></span>

<span data-ttu-id="f8364-234">一种方法，用于将一个[qubit](xref:microsoft.quantum.glossary#qubit)的数据（即[量程状态](xref:microsoft.quantum.glossary#quantum-state)）从一个位置重新生成到另一个位置，而无需使用[牵连](xref:microsoft.quantum.glossary#entanglement)和[度量](xref:microsoft.quantum.glossary#measurement)实际移动 qubit。</span><span class="sxs-lookup"><span data-stu-id="f8364-234">A method for regenerating data, or the [quantum state](xref:microsoft.quantum.glossary#quantum-state), of one [qubit](xref:microsoft.quantum.glossary#qubit) from one place to another without physically moving the qubit, using [entanglement](xref:microsoft.quantum.glossary#entanglement) and [measurement](xref:microsoft.quantum.glossary#measurement).</span></span>  <span data-ttu-id="f8364-235">有关详细信息，请参阅[量子线路](xref:microsoft.quantum.concepts.circuits)和[量子 Katas](xref:microsoft.quantum.overview.katas)的相应 kata。</span><span class="sxs-lookup"><span data-stu-id="f8364-235">For more information, see [Quantum circuits](xref:microsoft.quantum.concepts.circuits) and the respective kata at [Quantum Katas](xref:microsoft.quantum.overview.katas).</span></span>

## <a name="tuple"></a><span data-ttu-id="f8364-236">Tuple</span><span class="sxs-lookup"><span data-stu-id="f8364-236">Tuple</span></span>

<span data-ttu-id="f8364-237">作为单个值的逗号分隔值的集合。</span><span class="sxs-lookup"><span data-stu-id="f8364-237">A collection of comma-separated values that acts as a single value.</span></span> <span data-ttu-id="f8364-238">元组的*类型*由其包含的值的类型定义。</span><span class="sxs-lookup"><span data-stu-id="f8364-238">The *type* of a tuple is defined by the types of values it contains.</span></span> <span data-ttu-id="f8364-239">在 Q # 中，元组是[不可变](xref:microsoft.quantum.glossary#immutable)的，并且可以嵌套、包含数组或用于数组。</span><span class="sxs-lookup"><span data-stu-id="f8364-239">In Q#, tuples are [immutable](xref:microsoft.quantum.glossary#immutable) and can be nested, contain arrays, or used in an array.</span></span> <span data-ttu-id="f8364-240">有关详细信息，请参阅[元组类型](xref:microsoft.quantum.guide.types#tuple-types)。</span><span class="sxs-lookup"><span data-stu-id="f8364-240">For more information, see [Tuple types](xref:microsoft.quantum.guide.types#tuple-types).</span></span>

## <a name="unitary-operator"></a><span data-ttu-id="f8364-241">单一运算符</span><span class="sxs-lookup"><span data-stu-id="f8364-241">Unitary operator</span></span>

<span data-ttu-id="f8364-242">一个运算符，其反正等于其[adjoint](xref:microsoft.quantum.glossary#adjoint)，即 $UU ^ {\dagger } = \id $ 。</span><span class="sxs-lookup"><span data-stu-id="f8364-242">An operator whose inverse is equal to its [adjoint](xref:microsoft.quantum.glossary#adjoint), i.e., $UU^{\dagger} = \id$.</span></span>

## <a name="user-defined-type"></a><span data-ttu-id="f8364-243">用户定义类型</span><span class="sxs-lookup"><span data-stu-id="f8364-243">User-defined type</span></span>

<span data-ttu-id="f8364-244">可能称为单个单元的内置或以前定义的类型的集合。</span><span class="sxs-lookup"><span data-stu-id="f8364-244">A collection of built-in or previously defined types that may be referred to as a single unit.</span></span> <span data-ttu-id="f8364-245">有关详细信息，请参阅[用户定义类型](xref:microsoft.quantum.guide.types#user-defined-types)。</span><span class="sxs-lookup"><span data-stu-id="f8364-245">For more information, see [User-defined types](xref:microsoft.quantum.guide.types#user-defined-types).</span></span>