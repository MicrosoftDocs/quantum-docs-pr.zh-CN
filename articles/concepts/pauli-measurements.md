---
title: Pauli 度量值
description: 了解如何使用 qubit Pauli 测量操作。
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: fcd30c171859f96c3f9cc74664ecba8df0a02855
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907505"
---
# <a name="pauli-measurements"></a><span data-ttu-id="b785e-103">Pauli 度量值</span><span class="sxs-lookup"><span data-stu-id="b785e-103">Pauli Measurements</span></span>

<span data-ttu-id="b785e-104">在前面的讨论中，我们重点介绍计算基础度量值。</span><span class="sxs-lookup"><span data-stu-id="b785e-104">In the previous discussions, we have focused on computational basis measurements.</span></span>
<span data-ttu-id="b785e-105">事实上，从符号的角度来看，量子计算会出现其他常见的度量，这在计算基础度量方面非常方便。</span><span class="sxs-lookup"><span data-stu-id="b785e-105">In fact, there are other common measurements that occur in quantum computing that, from a notational perspective, are convenient to express in terms of computational basis measurements.</span></span>
<span data-ttu-id="b785e-106">当你使用 Q # 时，你将遇到的最常见的度量值可能是*Pauli 的度量值*，它将计算基础度量值纳入其他基准，并在不同 qubits 之间进行奇偶校验。</span><span class="sxs-lookup"><span data-stu-id="b785e-106">As you work with Q#, the most common kind of measurements that you'll run into will likely be *Pauli measurements*, which generalize computational basis measurements to include measurements in other bases, and of parity between different qubits.</span></span>
<span data-ttu-id="b785e-107">在这种情况下，通常会讨论度量 Pauli 运算符，通常是运算符，如 $X、Y、Z $ 或 $Z \otimes Z、X\otimes X、X\otimes Y $ 等。</span><span class="sxs-lookup"><span data-stu-id="b785e-107">In such cases, it is common to discuss measuring a Pauli operator, in general an operator such as $X,Y,Z$ or $Z\otimes Z, X\otimes X, X\otimes Y$, and so forth.</span></span>

> [!TIP]
> <span data-ttu-id="b785e-108">在 Q # 中，多 qubit Pauli 运算符通常由 `Pauli[]`类型的数组表示。</span><span class="sxs-lookup"><span data-stu-id="b785e-108">In Q#, multi-qubit Pauli operators are generally represented by arrays of type `Pauli[]`.</span></span>
> <span data-ttu-id="b785e-109">例如，若要表示 $X \otimes Z \otimes Y $，可以使用数组 `[PauliX, PauliZ, PauliY]`。</span><span class="sxs-lookup"><span data-stu-id="b785e-109">For example, to represent $X \otimes Z \otimes Y$, you can use the array `[PauliX, PauliZ, PauliY]`.</span></span>

<span data-ttu-id="b785e-110">在量程错误纠正的子字段中，讨论 Pauli 运算符的度量值尤其常见。</span><span class="sxs-lookup"><span data-stu-id="b785e-110">Discussing measurement in terms of Pauli operators is especially common in the subfield of quantum error correction.</span></span>
<span data-ttu-id="b785e-111">在 Q # 中，我们遵循类似的约定;现在，我们将介绍此替代度量视图。</span><span class="sxs-lookup"><span data-stu-id="b785e-111">In Q#, we follow a similar convention; we now explain this alternative view of measurements.</span></span>

<span data-ttu-id="b785e-112">在深入了解有关如何思考 Pauli 度量的详细信息之前，请考虑测量量程内单个 qubit 对量程状态的作用。</span><span class="sxs-lookup"><span data-stu-id="b785e-112">Before delving into the details of how to think of a Pauli measurement, it is useful to think about what measuring a single qubit inside a quantum computer does to the quantum state.</span></span>
<span data-ttu-id="b785e-113">假设有一个 $n 的 "qubit" 量程状态;然后，测量一个 qubit 会立即将该状态的一半作为 $ 2 ^ n $ 可能的一半。</span><span class="sxs-lookup"><span data-stu-id="b785e-113">Imagine that we have an $n$-qubit quantum state; then measuring one qubit immediately rules out half of the $2^n$ possibilities that state could be in.</span></span>
<span data-ttu-id="b785e-114">换言之，该度量值将量程状态投影到两个半个空格。</span><span class="sxs-lookup"><span data-stu-id="b785e-114">In other words, the measurement projects the quantum state onto one of two half-spaces.</span></span>
<span data-ttu-id="b785e-115">我们可以通用化我们对量化指标的看法，以反映这种直觉。</span><span class="sxs-lookup"><span data-stu-id="b785e-115">We can generalize the way we think about measurement to reflect this intuition.</span></span>

<span data-ttu-id="b785e-116">为了简洁地识别这些 subspaces，我们需要一种用于描述这些的语言。</span><span class="sxs-lookup"><span data-stu-id="b785e-116">In order to concisely identify these subspaces, we need a language for describing them.</span></span>
<span data-ttu-id="b785e-117">描述这两个 subspaces 的一种方法是通过一个矩阵来指定它们，该矩阵只包含两个唯一的本征值，约定为 "\pm $1"。</span><span class="sxs-lookup"><span data-stu-id="b785e-117">One way to describe the two subspaces is by specifying them through a matrix that just has two unique eigenvalues, taken by convention to be $\pm 1$.</span></span>
<span data-ttu-id="b785e-118">有关以这种方式描述 subspaces 的简单示例，请考虑 $Z $：</span><span class="sxs-lookup"><span data-stu-id="b785e-118">For a simple example of describing subspaces in this way, consider $Z$:</span></span>

<span data-ttu-id="b785e-119">$ $ \begin{align} Z & = \begin{bmatrix} 1 & 0 \\\\ 0 &-1 \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="b785e-119">$$ \begin{align} Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="b785e-120">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="b785e-120">\end{align} $$</span></span>

<span data-ttu-id="b785e-121">通过读取 $Z Pauli $ matrix 的对角元素，我们可以看到 $Z $ 具有两个本征向量、$ \ket{0}$ 和 $ \ket{1}$，其中包含相应的本征值 $ \pm $1。</span><span class="sxs-lookup"><span data-stu-id="b785e-121">By reading the diagonal elements of the Pauli-$Z$ matrix, we can see that $Z$ has two eigenvectors, $\ket{0}$ and $\ket{1}$, with corresponding eigenvalues $\pm 1$.</span></span>
<span data-ttu-id="b785e-122">因此，如果我们测量 qubit 并获取 `Zero` （对应于状态 $ \ket{0}$），我们知道我们的 qubit 的状态是 $Z $ operator 的 $ + $1 eigenstate。</span><span class="sxs-lookup"><span data-stu-id="b785e-122">Thus, if we measure the qubit and obtain `Zero` (corresponding to the state $\ket{0}$), we know that the state of our qubit is a $+1$ eigenstate of the $Z$ operator.</span></span>
<span data-ttu-id="b785e-123">同样，如果我们获取 `One`，我们知道，qubit 的状态为 $Z $ 的 $-$1 eigenstate。</span><span class="sxs-lookup"><span data-stu-id="b785e-123">Similarly, if we obtain `One`, we know that the state of our qubit is a $-1$ eigenstate of $Z$.</span></span>
<span data-ttu-id="b785e-124">此过程在 Pauli 度量语言中称为 "度量 Pauli $Z $"，完全等同于执行计算基础度量。</span><span class="sxs-lookup"><span data-stu-id="b785e-124">This process is referred to in the language of Pauli measurements as "measuring Pauli $Z$," and is entirely equivalent to performing a computational basis measurement.</span></span>

<span data-ttu-id="b785e-125">为 $Z $ 的单一转换的任何 $ 2 \ $2 矩阵都还满足此条件。</span><span class="sxs-lookup"><span data-stu-id="b785e-125">Any $2\times 2$ matrix that is a unitary transformation of $Z$ also satisfies this criteria.</span></span>
<span data-ttu-id="b785e-126">也就是说，我们还可以使用矩阵 $A = U ^ \dagger Z U $，其中 $U $ 是任何其他单一矩阵，以便为矩阵定义其 $ \pm $1 本征向量中的两个测量结果。</span><span class="sxs-lookup"><span data-stu-id="b785e-126">That is, we could also use a matrix $A=U^\dagger Z U$, where $U$ is any other unitary matrix, to give a matrix that defines the two outcomes of a measurement in its $\pm 1$ eigenvectors.</span></span>
<span data-ttu-id="b785e-127">Pauli 度量值的表示法通过将 $X、Y、Z $ 度量值识别为可从 qubit 获取信息的等效度量来引用这种单一等效性。</span><span class="sxs-lookup"><span data-stu-id="b785e-127">The notation of Pauli measurements references this unitary equivalence by identifying $X,Y,Z$ measurements as equivalent measurements that one could do to gain information from a qubit.</span></span>
<span data-ttu-id="b785e-128">为方便起见，下面提供了这些度量值。</span><span class="sxs-lookup"><span data-stu-id="b785e-128">These measurements are given below for convenience.</span></span>


|<span data-ttu-id="b785e-129">Pauli 度量</span><span class="sxs-lookup"><span data-stu-id="b785e-129">Pauli Measurement</span></span>  |<span data-ttu-id="b785e-130">单一转换</span><span class="sxs-lookup"><span data-stu-id="b785e-130">Unitary transformation</span></span>  |
|-------------------|------------------------|
| <span data-ttu-id="b785e-131">$Z $</span><span class="sxs-lookup"><span data-stu-id="b785e-131">$Z$</span></span>               | <span data-ttu-id="b785e-132">$ \boldone $</span><span class="sxs-lookup"><span data-stu-id="b785e-132">$\boldone$</span></span>             |
| <span data-ttu-id="b785e-133">$X $</span><span class="sxs-lookup"><span data-stu-id="b785e-133">$X$</span></span>               | <span data-ttu-id="b785e-134">$H $</span><span class="sxs-lookup"><span data-stu-id="b785e-134">$H$</span></span>                    |
| <span data-ttu-id="b785e-135">$Y $</span><span class="sxs-lookup"><span data-stu-id="b785e-135">$Y$</span></span>               | <span data-ttu-id="b785e-136">$HS ^ {\dagger} $</span><span class="sxs-lookup"><span data-stu-id="b785e-136">$HS^{\dagger}$</span></span>         |

<span data-ttu-id="b785e-137">也就是说，使用这种语言时，"度量值 $Y $" 相当于应用 $HS ^ \dagger $，然后以计算为基础进行度量，其中[`S`](xref:microsoft.quantum.intrinsic.s)是一个内部量程操作，有时称为 "阶段入口"，可由单一矩阵模拟</span><span class="sxs-lookup"><span data-stu-id="b785e-137">That is, using this language, "measure $Y$" is equivalent to applying $HS^\dagger$ and then measuring in the computational basis, where [`S`](xref:microsoft.quantum.intrinsic.s) is an intrinsic quantum operation sometimes called the "phase gate," and can be simulated by the unitary matrix</span></span>

<span data-ttu-id="b785e-138">$ $ \begin{align} S = \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="b785e-138">$$ \begin{align} S = \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
<span data-ttu-id="b785e-139">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="b785e-139">\end{align} $$</span></span>

<span data-ttu-id="b785e-140">它还等效于将 $HS ^ \dagger $ 应用于量程状态向量，然后测量 $ $Z $，以便以下操作等效于 `Measure([PauliY], [q]])`：</span><span class="sxs-lookup"><span data-stu-id="b785e-140">It is also equivalent to applying $HS^\dagger$ to the quantum state vector and then measuring $Z$, such that the following operation is equivalent to `Measure([PauliY], [q]])`:</span></span>

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        H(q);
        Adjoint S(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

<span data-ttu-id="b785e-141">然后，将转换回计算基础，以将 $SH $ 应用到量程状态向量，从而找到正确的状态;在上面的代码片段中，转换回计算基础的方式是通过使用 `within … apply` 块自动处理。</span><span class="sxs-lookup"><span data-stu-id="b785e-141">The correct state would then be found by transforming back to the computational basis, which amounts to applying $SH$ to the quantum state vector; in the above snippet, the transformation back to the computational basis is handled automatically by the use of the `within … apply` block.</span></span>

<span data-ttu-id="b785e-142">在 Q # 中，我们说结果---也就是说，从与状态---交互中提取的传统信息由 $j \in \\{\texttt{Zero}，\texttt{One}\\} $ 的 `Result` 值指定，以指示结果是否位于 Pauli 运算符度量的 $ （-1） ^ j $ eigenspace 中。</span><span class="sxs-lookup"><span data-stu-id="b785e-142">In Q#, we say the outcome---that is, the classical information extracted from interacting with the state---is given by a `Result` value $j \in \\{\texttt{Zero}, \texttt{One}\\}$ indicating if the result is in the $(-1)^j$ eigenspace of the Pauli operator measured.</span></span>


## <a name="multiple-qubit-measurements"></a><span data-ttu-id="b785e-143">多 qubit 度量</span><span class="sxs-lookup"><span data-stu-id="b785e-143">Multiple-qubit measurements</span></span>

<span data-ttu-id="b785e-144">多 qubit Pauli 运算符的度量值的定义类似，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b785e-144">Measurements of multi-qubit Pauli operators are defined similarly, as seen from:</span></span>

<span data-ttu-id="b785e-145">$ $ Z\otimes Z = \begin{bmatrix}1 & 0 & 0 & 0\\\\ 0 & & 0 & 0\\\\ 0 & 0 & & 0\\\\ 0 & 0 & 1 \ end {bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="b785e-145">$$ Z\otimes Z = \begin{bmatrix}1 &0 &0&0\\\\  0&-1&0&0\\\\ 0&0&-1&0\\\\ 0&0&0&1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="b785e-146">因此，两个 Pauli $Z $ 运算符的 tensor 产品构成一个矩阵，其中包含由 $ + $1 和 $-$1 本征值组成的两个空格。</span><span class="sxs-lookup"><span data-stu-id="b785e-146">Thus the tensor products of two Pauli-$Z$ operators forms a matrix composed of two spaces consisting of $+1$ and $-1$ eigenvalues.</span></span>
<span data-ttu-id="b785e-147">与单 qubit 大小写一样，两者都构成一半空间，这意味着可访问的矢量空间的一半属于 $ + $1 eigenspace，另一半是 $-$1 eigenspace。</span><span class="sxs-lookup"><span data-stu-id="b785e-147">As with the single-qubit case, both constitute a half-space meaning that half of the accessible vector space belongs to the $+1$ eigenspace and the remaining half to the $-1$ eigenspace.</span></span>
<span data-ttu-id="b785e-148">一般情况下，从 tensor 产品的定义可以轻松地看出 $Z Pauli $ operators 的任何 tensor 产品以及标识也服从这一点。</span><span class="sxs-lookup"><span data-stu-id="b785e-148">In general, it is easy to see from the definition of the tensor product that any tensor product of Pauli-$Z$ operators and the identity also obeys this.</span></span>
<span data-ttu-id="b785e-149">例如，</span><span class="sxs-lookup"><span data-stu-id="b785e-149">For example,</span></span>

<span data-ttu-id="b785e-150">$ $ \begin{align} Z \otimes \boldone = \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & & \\0 \\ & 0 & 0 & 0-1 \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="b785e-150">$$ \begin{align} Z \otimes \boldone = \begin{bmatrix} 1 &  0 &  0 &  0 \\\\ 0 &  1 &  0 &  0 \\\\ 0 &  0 & -1 &  0 \\\\ 0 &  0 &  0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="b785e-151">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="b785e-151">\end{align} $$</span></span>

<span data-ttu-id="b785e-152">与之前一样，此类矩阵的任何单一转换还将描述 $ \pm $1 本征值标记的两个半角空格。</span><span class="sxs-lookup"><span data-stu-id="b785e-152">As before, any unitary transformation of such matrices also describes two half-spaces labeled by $\pm 1$ eigenvalues.</span></span>
<span data-ttu-id="b785e-153">例如，$X $Z = HXH $ 的标识中的 \otimes X = H\otimes H （Z\otimes Z） H\otimes H $。</span><span class="sxs-lookup"><span data-stu-id="b785e-153">For example, $X\otimes X = H\otimes H(Z\otimes Z)H\otimes H$  from the identity that $Z=HXH$.</span></span>
<span data-ttu-id="b785e-154">与 qubit 情况类似，所有 qubit Pauli 度量值都可以编写为 $U ^ \dagger （Z\otimes \id） U $，$ 4 \ $4 单一矩阵 $U $。</span><span class="sxs-lookup"><span data-stu-id="b785e-154">Similar to the one-qubit case, all two-qubit Pauli-measurements can be written as $U^\dagger (Z\otimes \id) U$ for $4\times 4$ unitary matrices $U$.</span></span> <span data-ttu-id="b785e-155">枚举下表中的转换。</span><span class="sxs-lookup"><span data-stu-id="b785e-155">We enumerate the transformations in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="b785e-156">在下表中，我们使用 $ \operatorname{SWAP} $ 指示矩阵 $ $ \begin{align} \operatorname{SWAP} & = \left （\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{matrix}\right） \end{align} $ $ 用于模拟内部操作[`SWAP`](xref:microsoft.quantum.intrinsic)。</span><span class="sxs-lookup"><span data-stu-id="b785e-156">In the table below, we use $\operatorname{SWAP}$ to indicate the matrix $$ \begin{align} \operatorname{SWAP} & = \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{matrix}\right) \end{align} $$ used to simulate the intrinsic operation [`SWAP`](xref:microsoft.quantum.intrinsic).</span></span>

|<span data-ttu-id="b785e-157">Pauli 度量</span><span class="sxs-lookup"><span data-stu-id="b785e-157">Pauli Measurement</span></span>     |<span data-ttu-id="b785e-158">单一转换</span><span class="sxs-lookup"><span data-stu-id="b785e-158">Unitary transformation</span></span>  |
|----------------------|------------------------|
| <span data-ttu-id="b785e-159">$Z \otimes \boldone $</span><span class="sxs-lookup"><span data-stu-id="b785e-159">$Z \otimes \boldone$</span></span> | <span data-ttu-id="b785e-160">$ \boldone \otimes \boldone $</span><span class="sxs-lookup"><span data-stu-id="b785e-160">$\boldone \otimes \boldone$</span></span> |
| <span data-ttu-id="b785e-161">$Z \otimes \boldone $</span><span class="sxs-lookup"><span data-stu-id="b785e-161">$Z\otimes \boldone$</span></span> | <span data-ttu-id="b785e-162">$ \boldone\otimes \boldone $</span><span class="sxs-lookup"><span data-stu-id="b785e-162">$\boldone\otimes \boldone$</span></span> |
| <span data-ttu-id="b785e-163">$X \otimes \boldone $</span><span class="sxs-lookup"><span data-stu-id="b785e-163">$X\otimes \boldone$</span></span> | <span data-ttu-id="b785e-164">$H \otimes \boldone $</span><span class="sxs-lookup"><span data-stu-id="b785e-164">$H\otimes \boldone$</span></span> |
| <span data-ttu-id="b785e-165">$Y \otimes \boldone $</span><span class="sxs-lookup"><span data-stu-id="b785e-165">$Y\otimes \boldone$</span></span> | <span data-ttu-id="b785e-166">$HS ^ \dagger\otimes \boldone $</span><span class="sxs-lookup"><span data-stu-id="b785e-166">$HS^\dagger\otimes \boldone$</span></span> |
| <span data-ttu-id="b785e-167">$ \boldone \otimes Z $</span><span class="sxs-lookup"><span data-stu-id="b785e-167">$\boldone \otimes Z$</span></span> | <span data-ttu-id="b785e-168">$ \operatorname{SWAP} $</span><span class="sxs-lookup"><span data-stu-id="b785e-168">$\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="b785e-169">$ \boldone \otimes X $</span><span class="sxs-lookup"><span data-stu-id="b785e-169">$\boldone \otimes X$</span></span> | <span data-ttu-id="b785e-170">$ （H\otimes \boldone） \operatorname{SWAP} $</span><span class="sxs-lookup"><span data-stu-id="b785e-170">$(H\otimes \boldone)\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="b785e-171">$ \boldone \otimes Y $</span><span class="sxs-lookup"><span data-stu-id="b785e-171">$\boldone \otimes Y$</span></span> | <span data-ttu-id="b785e-172">$ （HS ^ \dagger\otimes \boldone） \operatorname{SWAP} $</span><span class="sxs-lookup"><span data-stu-id="b785e-172">$(HS^\dagger\otimes \boldone)\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="b785e-173">$Z \otimes Z $</span><span class="sxs-lookup"><span data-stu-id="b785e-173">$Z\otimes Z$</span></span> | <span data-ttu-id="b785e-174">$ \operatorname{CNOT}\_{10}$</span><span class="sxs-lookup"><span data-stu-id="b785e-174">$\operatorname{CNOT}\_{10}$</span></span> |
| <span data-ttu-id="b785e-175">$X \otimes Z $</span><span class="sxs-lookup"><span data-stu-id="b785e-175">$X\otimes Z$</span></span> | <span data-ttu-id="b785e-176">$ \operatorname{CNOT}\_{10}（H\otimes \boldone） $</span><span class="sxs-lookup"><span data-stu-id="b785e-176">$\operatorname{CNOT}\_{10}(H\otimes \boldone)$</span></span> |
| <span data-ttu-id="b785e-177">$Y \otimes Z $</span><span class="sxs-lookup"><span data-stu-id="b785e-177">$Y\otimes Z$</span></span> | <span data-ttu-id="b785e-178">$ \operatorname{CNOT}\_{10}（HS ^ \dagger\otimes \boldone） $</span><span class="sxs-lookup"><span data-stu-id="b785e-178">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes \boldone)$</span></span> |
| <span data-ttu-id="b785e-179">$Z \otimes X $</span><span class="sxs-lookup"><span data-stu-id="b785e-179">$Z\otimes X$</span></span> | <span data-ttu-id="b785e-180">$ \operatorname{CNOT}\_{10}（\boldone\otimes H） $</span><span class="sxs-lookup"><span data-stu-id="b785e-180">$\operatorname{CNOT}\_{10}(\boldone\otimes H)$</span></span> |
| <span data-ttu-id="b785e-181">$X \otimes X $</span><span class="sxs-lookup"><span data-stu-id="b785e-181">$X\otimes X$</span></span> | <span data-ttu-id="b785e-182">$ \operatorname{CNOT}\_{10}（H\otimes H） $</span><span class="sxs-lookup"><span data-stu-id="b785e-182">$\operatorname{CNOT}\_{10}(H\otimes H)$</span></span> |
| <span data-ttu-id="b785e-183">$Y \otimes X $</span><span class="sxs-lookup"><span data-stu-id="b785e-183">$Y\otimes X$</span></span> | <span data-ttu-id="b785e-184">$ \operatorname{CNOT}\_{10}（HS ^ \dagger\otimes H） $</span><span class="sxs-lookup"><span data-stu-id="b785e-184">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes H)$</span></span> |
| <span data-ttu-id="b785e-185">$Z \otimes Y $</span><span class="sxs-lookup"><span data-stu-id="b785e-185">$Z\otimes Y$</span></span> | <span data-ttu-id="b785e-186">$ \operatorname{CNOT}\_{10}（\boldone \otimes HS ^ \dagger） $</span><span class="sxs-lookup"><span data-stu-id="b785e-186">$\operatorname{CNOT}\_{10}(\boldone \otimes HS^\dagger)$</span></span> |
| <span data-ttu-id="b785e-187">$X \otimes Y $</span><span class="sxs-lookup"><span data-stu-id="b785e-187">$X\otimes Y$</span></span> | <span data-ttu-id="b785e-188">$ \operatorname{CNOT}\_{10}（H\otimes HS ^ \dagger） $</span><span class="sxs-lookup"><span data-stu-id="b785e-188">$\operatorname{CNOT}\_{10}(H\otimes HS^\dagger)$</span></span> |
| <span data-ttu-id="b785e-189">$Y \otimes Y $</span><span class="sxs-lookup"><span data-stu-id="b785e-189">$Y\otimes Y$</span></span> | <span data-ttu-id="b785e-190">$ \operatorname{CNOT}\_{10}（HS ^ \dagger\otimes HS ^ \dagger） $</span><span class="sxs-lookup"><span data-stu-id="b785e-190">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes HS^\dagger)$</span></span> |

<span data-ttu-id="b785e-191">此处出现[`CNOT`](xref:microsoft.quantum.intrinsic.cnot)操作的原因如下。</span><span class="sxs-lookup"><span data-stu-id="b785e-191">Here, the [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operation appears for the following reason.</span></span>
<span data-ttu-id="b785e-192">每个不包含 $ \boldone $ matrix 的 Pauli 度量值都等效于一个单一的，以便按以上推理 $Z \otimes Z $。</span><span class="sxs-lookup"><span data-stu-id="b785e-192">Each Pauli measurement that does not include the $\boldone$ matrix is equivalent up to a unitary to $Z\otimes Z$ by the above reasoning.</span></span>
<span data-ttu-id="b785e-193">$Z \otimes Z $ 的本征值仅依赖于构成每个计算基础向量的 qubits 的奇偶校验，并且用于计算此奇偶校验并将其存储在第一位的受控 not 运算。</span><span class="sxs-lookup"><span data-stu-id="b785e-193">The eigenvalues of $Z\otimes Z$ only depend on the parity of the qubits that comprise each computational basis vector, and the controlled-not operations serve to compute this parity and store it in the first bit.</span></span>
<span data-ttu-id="b785e-194">然后，在度量第一位后，可以恢复生成的半角空格的标识，这相当于测量 Pauli 运算符。</span><span class="sxs-lookup"><span data-stu-id="b785e-194">Then once the first bit is measured, we can recover the identity of the resultant half-space, which is equivalent to measuring the Pauli operator.</span></span>

<span data-ttu-id="b785e-195">另外一个注意事项：尽管测量 $Z \otimes Z $ 与按顺序 $Z \otimes \mathbb{1}$ 和 $ \mathbb{1} \otimes Z $，此假设将为 false。</span><span class="sxs-lookup"><span data-stu-id="b785e-195">One additional note: while it may be tempting to assume that measuring $Z\otimes Z$ is the same as sequentially measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$, this assumption would be false.</span></span>
<span data-ttu-id="b785e-196">原因是度量 $Z \otimes Z $ 将量程状态投影到这些运算符的 $ + $1 或 $-$1 eigenstate 中。</span><span class="sxs-lookup"><span data-stu-id="b785e-196">The reason is that measuring $Z\otimes Z$ projects the quantum state into either the $+1$ or $-1$ eigenstate of these operators.</span></span>
<span data-ttu-id="b785e-197">测量 $Z \otimes \mathbb{1}$，then $ \mathbb{1} \otimes Z $ 将量程状态向量首先投影到 $Z \otimes \mathbb{1}$ 的半个空格上，然后再投影到 $ \mathbb{1} \otimes Z $ 的半个空格。</span><span class="sxs-lookup"><span data-stu-id="b785e-197">Measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$ projects the quantum state vector first onto a half space of $Z\otimes \mathbb{1}$ and then onto a half space of $\mathbb{1} \otimes Z$.</span></span>
<span data-ttu-id="b785e-198">由于有四个计算基准向量，同时执行这两个度量会将状态降到一个四分之一空间，因此将其减少为单个计算基础向量。</span><span class="sxs-lookup"><span data-stu-id="b785e-198">As there are four computational basis vectors, performing both measurements reduces the state to a quarter-space and hence reduces it to a single computational basis vector.</span></span>

## <a name="correlations-between-qubits"></a><span data-ttu-id="b785e-199">Qubits 之间的关联</span><span class="sxs-lookup"><span data-stu-id="b785e-199">Correlations between qubits</span></span>
<span data-ttu-id="b785e-200">查看度量标准（例如 $X \otimes X $ 或 $Z \otimes Z $）的 tensor 产品的另一种方法是，这些度量值使你可以查看在这两个 qubits 之间的关联中存储的信息。</span><span class="sxs-lookup"><span data-stu-id="b785e-200">Another way of looking at measuring tensor products of Pauli matrices such as $X\otimes X$ or $Z\otimes Z$ is that these measurements let you look at information stored in the correlations between the two qubits.</span></span>
<span data-ttu-id="b785e-201">度量 $X \otimes \id $ 使你可以查看在第一个 qubit 中本地存储的信息。</span><span class="sxs-lookup"><span data-stu-id="b785e-201">Measuring $X\otimes \id$ lets you look at information that is locally stored in the first qubit.</span></span>
<span data-ttu-id="b785e-202">尽管这两种类型的度量在量程计算中都同样很有价值，但前者会导致量程计算的强大功能。</span><span class="sxs-lookup"><span data-stu-id="b785e-202">While both types of measurements are equally valuable in quantum computing, the former illuminates the power of quantum computing.</span></span>
<span data-ttu-id="b785e-203">它在量程计算中显示，通常情况下，你想要学习的信息不会存储在任何单个 qubit 中，而是在所有 qubits 中同时存储为非本地存储，因此仅通过联合度量（例如 $Z \otimes Z $）来查看此项信息成为清单。</span><span class="sxs-lookup"><span data-stu-id="b785e-203">It reveals that in quantum computing, often the information you wish to learn is not stored in any single qubit but rather stored non-locally in all the qubits at once, and therefore only by looking at it through a joint measurement (e.g. $Z\otimes Z$) does this information become manifest.</span></span>

<span data-ttu-id="b785e-204">例如，在 "纠错" 中，我们经常想要了解在学习有关我们尝试保护的状态时所发生的错误。</span><span class="sxs-lookup"><span data-stu-id="b785e-204">For example, in error correction, we often wish to learn what error occurred while learning nothing about the state that we're trying to protect.</span></span>
<span data-ttu-id="b785e-205">"[位翻转" 代码示例](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code)显示了如何使用诸如 $Z \otimes z \otimes \id $ 和 $ \Id \otimes Z \otimes z $ 这类度量的示例。</span><span class="sxs-lookup"><span data-stu-id="b785e-205">The [bit-flip code sample](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) shows an example of how you can do that using measurements like $Z \otimes Z \otimes \id$ and $\id \otimes Z \otimes Z$.</span></span>
<!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded. -->

<span data-ttu-id="b785e-206">也可以测量任意 Pauli 运算符（如 $X \otimes Y \otimes Z \otimes \boldone $）。</span><span class="sxs-lookup"><span data-stu-id="b785e-206">Arbitrary Pauli operators such as $X\otimes Y \otimes Z \otimes \boldone$ can also be measured.</span></span>
<span data-ttu-id="b785e-207">Pauli 运算符的所有此类 tensor 产品仅具有两个本征值 $ \pm $1，并且两个 eigenspaces 构成整个矢量空间的半个空格。</span><span class="sxs-lookup"><span data-stu-id="b785e-207">All such tensor products of Pauli operators have only two eigenvalues $\pm 1$ and both eigenspaces constitute half-spaces of the entire vector space.</span></span>
<span data-ttu-id="b785e-208">因此，它们符合上面所述的要求。</span><span class="sxs-lookup"><span data-stu-id="b785e-208">Thus they coincide with the requirements stated above.</span></span>

<span data-ttu-id="b785e-209">在 Q # 中，此类度量值将返回 $j $ （如果度量值产生 eigenspace 符号 $ （-1） ^ j $ 的结果）。</span><span class="sxs-lookup"><span data-stu-id="b785e-209">In Q#, such measurements return $j$ if the measurement yields a result in the eigenspace of sign $(-1)^j$.</span></span>
<span data-ttu-id="b785e-210">将 Pauli 度量作为 Q # 中的内置功能非常有用，因为测量此类运算符需要使用受控-NOT 入口和基础转换的长链来描述将操作表达为 $Z $ 和 $ \id $ 的 tensor 产品所需的 diagonalizing $U $ 门。</span><span class="sxs-lookup"><span data-stu-id="b785e-210">Having Pauli measurements as a built-in feature in Q# is helpful because measuring such operators requires long chains of controlled-NOT gates and basis transformations to describe the diagonalizing $U$ gate needed to express the operation as a tensor product of $Z$ and $\id$.</span></span>
<span data-ttu-id="b785e-211">通过能够指定想要执行其中一项预定义度量，无需担心如何转换基础，以使计算基础度量提供必要的信息。</span><span class="sxs-lookup"><span data-stu-id="b785e-211">By being able to specify that you wish to do one of these pre-defined measurements, you don't need to worry about how to transform your basis such that a computational basis measurement provides the necessary information.</span></span>
<span data-ttu-id="b785e-212">Q # 会自动处理所有必要的基础转换。</span><span class="sxs-lookup"><span data-stu-id="b785e-212">Q# handles all the necessary basis transformations for you automatically.</span></span>
<span data-ttu-id="b785e-213">有关详细信息，请参阅[`Measure`](xref:microsoft.quantum.intrinsic.measure)和[`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis)操作。</span><span class="sxs-lookup"><span data-stu-id="b785e-213">For more information, see the [`Measure`](xref:microsoft.quantum.intrinsic.measure) and [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operations.</span></span>

## <a name="the-no-cloning-theorem"></a><span data-ttu-id="b785e-214">无克隆定理</span><span class="sxs-lookup"><span data-stu-id="b785e-214">The No-Cloning Theorem</span></span>

<span data-ttu-id="b785e-215">量程信息非常强大。</span><span class="sxs-lookup"><span data-stu-id="b785e-215">Quantum information is powerful.</span></span>
<span data-ttu-id="b785e-216">它使我们能够以指数形式比最佳已知传统算法更快地执行令人惊叹的东西，或高效模拟经典需要指数成本来准确模拟的相关 electron 系统。</span><span class="sxs-lookup"><span data-stu-id="b785e-216">It enables us to do amazing things such as factor numbers exponentially faster than the best known classical algorithms, or efficiently simulate correlated electron systems that classically require exponential cost to simulate accurately.</span></span>
<span data-ttu-id="b785e-217">但对量程计算的强大功能有一些限制。</span><span class="sxs-lookup"><span data-stu-id="b785e-217">However, there are limitations to the power of quantum computing.</span></span>
<span data-ttu-id="b785e-218">这种限制是由*无克隆定理*提供的。</span><span class="sxs-lookup"><span data-stu-id="b785e-218">One such limitation is given by the *No-Cloning Theorem*.</span></span>

<span data-ttu-id="b785e-219">不克隆的定理为名称正好。</span><span class="sxs-lookup"><span data-stu-id="b785e-219">The No-Cloning Theorem is aptly named.</span></span>
<span data-ttu-id="b785e-220">它不允许量程计算机克隆通用量程状态。</span><span class="sxs-lookup"><span data-stu-id="b785e-220">It disallows cloning of generic quantum states by a quantum computer.</span></span>
<span data-ttu-id="b785e-221">定理的证明非常简单。</span><span class="sxs-lookup"><span data-stu-id="b785e-221">The proof of the theorem is remarkably straightforward.</span></span>
<span data-ttu-id="b785e-222">虽然在这里我们的讨论中，无克隆定理的完整证明是一项很少的技术，但在我们的范围内没有额外的辅助 qubits 的证明（辅助 qubits 在计算期间用于暂存空间，并且在 Q # 中易于使用和管理，请参阅 <xref:microsoft.quantum.techniques.qubits>）。</span><span class="sxs-lookup"><span data-stu-id="b785e-222">While a full proof of the no-cloning theorem is a little too technical for our discussion here, the proof in the case of no additional auxiliary qubits is within our scope (auxiliary qubits are qubits used for scratch space during a computation and are easily used and managed in Q#, see <xref:microsoft.quantum.techniques.qubits>).</span></span>

<span data-ttu-id="b785e-223">对于此类量程计算机，克隆操作必须由单一矩阵进行描述。</span><span class="sxs-lookup"><span data-stu-id="b785e-223">For such a quantum computer, the cloning operation must be described by a unitary matrix.</span></span>
<span data-ttu-id="b785e-224">我们不允许进行度量，因为它会损坏我们尝试克隆的量程状态。</span><span class="sxs-lookup"><span data-stu-id="b785e-224">We disallow measurement, since it would corrupt the quantum state we are trying to clone.</span></span>
<span data-ttu-id="b785e-225">若要模拟克隆操作，我们希望单一矩阵使用 $ $ U \ket{\psi} \ket 的属性，为任何状态 $ \ket{\psi} ${0} = \ket{\psi} \ket{\psi} $ $。</span><span class="sxs-lookup"><span data-stu-id="b785e-225">To simulate the cloning operation, we want the unitary matrix used to have the property that $$ U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi} $$ for any state $\ket{\psi}$.</span></span>
<span data-ttu-id="b785e-226">然后，matrix 乘法的线性属性表示对于任何第二个量程状态 $ \ket{\phi} $，</span><span class="sxs-lookup"><span data-stu-id="b785e-226">The linearity property of matrix multiplication then implies that for any second quantum state $\ket{\phi}$,</span></span>

<span data-ttu-id="b785e-227">$ $ \begin{align} U \left [\frac{1}{\sqrt{2}} \left （\ket{\phi} + \ket{\psi} \right） \right] \ket{0} & = \frac{1}{\sqrt{2}} U\ket {\ phi} \ 票证{0} + \frac{1}{\sqrt{2}} U\ket {\ psi} \ 票证{0} \\\\ & = \frac{1}{\sqrt{2}} \left （\ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi} \right） \\\\ & \ne \left （\frac{1}{\sqrt{2}} \left （\ket{\phi} + \ket{\psi} \right） \right） \otimes \left （\frac{1}{\sqrt{2}} \left （\ket{\phi} + \ket{\psi} \right） \right）。</span><span class="sxs-lookup"><span data-stu-id="b785e-227">$$ \begin{align} U \left[ \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right] \ket{0} & = \frac{1}{\sqrt{2}} U\ket{\phi}\ket{0} + \frac{1}{\sqrt{2}} U\ket{\psi}\ket{0} \\\\ & = \frac{1}{\sqrt{2}} \left( \ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi} \right) \\\\ & \ne \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right) \otimes \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right).</span></span>
<span data-ttu-id="b785e-228">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="b785e-228">\end{align} $$</span></span>

<span data-ttu-id="b785e-229">这提供了不克隆定理背后的基本直觉：复制未知量程状态的任何设备必须至少在其复制的某些状态下引发错误。</span><span class="sxs-lookup"><span data-stu-id="b785e-229">This provides the fundamental intuition behind the No-Cloning Theorem: any device that copies an unknown quantum state must induce errors on at least some of the states it copies.</span></span>
<span data-ttu-id="b785e-230">虽然 cloner 在输入状态下线性处理的关键假设可以通过添加和度量辅助 qubits 来突破，此类交互也会通过测量统计信息泄漏有关系统的信息并防止精确在这种情况下进行克隆。</span><span class="sxs-lookup"><span data-stu-id="b785e-230">While the key assumption that the cloner acts linearly on the input state can be violated through the addition and measurement of auxiliary qubits, such interactions also leak information about the system through the measurement statistics and prevent exact cloning in such cases as well.</span></span>
<span data-ttu-id="b785e-231">有关无克隆定理的更完整的证明，请参阅[以获取详细信息](xref:microsoft.quantum.more-information)。</span><span class="sxs-lookup"><span data-stu-id="b785e-231">For a more complete proof of the No-Cloning Theorem see [For more information](xref:microsoft.quantum.more-information).</span></span>

<span data-ttu-id="b785e-232">无克隆定理对于定性了解量程计算非常重要，因为如果可以将量程状态重新克隆，则会被授予近乎神奇的功能，可以从量程状态中学习。</span><span class="sxs-lookup"><span data-stu-id="b785e-232">The No-Cloning Theorem is important for qualitative understanding of quantum computing because if you could clone quantum states inexpensively then you would be granted a near-magical ability to learn from quantum states.</span></span>
<span data-ttu-id="b785e-233">事实上，您可能违反了海森堡的 vaunted 不确定性原则。</span><span class="sxs-lookup"><span data-stu-id="b785e-233">Indeed, you could violate Heisenberg's vaunted uncertainty principle.</span></span>
<span data-ttu-id="b785e-234">或者，您可以使用最佳的 cloner 从复杂的量程分布中获取一个示例，并从一个示例中了解有关该分布的所有内容。</span><span class="sxs-lookup"><span data-stu-id="b785e-234">Alternatively, you could use an optimal cloner to take a single sample from a complex quantum distribution and learn everything you could possibly learn about that distribution from just one sample.</span></span>
<span data-ttu-id="b785e-235">这就像你翻转硬币和观察打印头，然后在告诉朋友，使其响应 "Ah 该硬币的分布必须与 $p = 0.512643 \ ldots $！</span><span class="sxs-lookup"><span data-stu-id="b785e-235">This would be like you flipping a coin and observing heads and then upon telling a friend about the result having them respond "Ah the distribution of that coin must be Bernoulli with $p=0.512643\ldots$!"</span></span>  <span data-ttu-id="b785e-236">此类语句是不 sensical 的，因为有一位信息（头结果）只是不能提供编码分发所需的多个信息，而不会有大量的信息。</span><span class="sxs-lookup"><span data-stu-id="b785e-236">Such a statement would be non-sensical because one bit of information (the heads outcome) simply cannot provide the many bits of information needed to encode the distribution without substantial prior information.</span></span>
<span data-ttu-id="b785e-237">同样，如果没有以前的信息，我们就不能完全克隆量程状态，因为我们不知道 $p $ 就无法准备系综的此类硬币。</span><span class="sxs-lookup"><span data-stu-id="b785e-237">Similarly, without prior information we cannot perfectly clone a quantum state just as we cannot prepare an ensemble of such coins without knowing $p$.</span></span>

<span data-ttu-id="b785e-238">信息在量程计算中不可用。</span><span class="sxs-lookup"><span data-stu-id="b785e-238">Information is not free in quantum computing.</span></span>
<span data-ttu-id="b785e-239">每个 qubit 都提供一项信息，而不克隆定理显示没有后门，可以利用它来解决有关系统所获得的信息与对其调用的干扰之间的基本平衡点。</span><span class="sxs-lookup"><span data-stu-id="b785e-239">Each qubit measured gives a single bit of information, and the No-Cloning Theorem shows that there is no backdoor that can be exploited to get around the fundamental tradeoff between information gained about the system and the disturbance invoked upon it.</span></span>
