---
<span data-ttu-id="37214-101">title： Pauli 度量说明：了解如何使用单 qubit Pauli 度量值操作。</span><span class="sxs-lookup"><span data-stu-id="37214-101">title: Pauli Measurements description: Learn how to work with single- and multi-qubit Pauli measurement operations.</span></span>
<span data-ttu-id="37214-102">author： bradben uid： pauli： benbra： v-ms. 日期： 12/11/2017 ms. 主题：文章不是：</span><span class="sxs-lookup"><span data-stu-id="37214-102">author: bradben uid: microsoft.quantum.concepts.pauli ms.author: v-benbra ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="37214-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="37214-103">"Q#"</span></span>
- <span data-ttu-id="37214-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="37214-104">"$$v"</span></span>
- <span data-ttu-id="37214-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="37214-105">"$$"</span></span>
- <span data-ttu-id="37214-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="37214-106">"$$"</span></span>
- <span data-ttu-id="37214-107">"$"</span><span class="sxs-lookup"><span data-stu-id="37214-107">"$"</span></span>
- <span data-ttu-id="37214-108">"$"</span><span class="sxs-lookup"><span data-stu-id="37214-108">"$"</span></span>
- <span data-ttu-id="37214-109">"$"</span><span class="sxs-lookup"><span data-stu-id="37214-109">"$"</span></span>
- <span data-ttu-id="37214-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="37214-110">"$$"</span></span>
- <span data-ttu-id="37214-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="37214-111">"\cdots"</span></span>
- <span data-ttu-id="37214-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="37214-112">"bmatrix"</span></span>
- <span data-ttu-id="37214-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="37214-113">"\ddots"</span></span>
- <span data-ttu-id="37214-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="37214-114">"\equiv"</span></span>
- <span data-ttu-id="37214-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="37214-115">"\sum"</span></span>
- <span data-ttu-id="37214-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="37214-116">"\begin"</span></span>
- <span data-ttu-id="37214-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="37214-117">"\end"</span></span>
- <span data-ttu-id="37214-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="37214-118">"\sqrt"</span></span>
- <span data-ttu-id="37214-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="37214-119">"\otimes"</span></span>
- <span data-ttu-id="37214-120">"{"</span><span class="sxs-lookup"><span data-stu-id="37214-120">"{"</span></span>
- <span data-ttu-id="37214-121">"}"</span><span class="sxs-lookup"><span data-stu-id="37214-121">"}"</span></span>
- <span data-ttu-id="37214-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="37214-122">"\text"</span></span>
- <span data-ttu-id="37214-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="37214-123">"\phi"</span></span>
- <span data-ttu-id="37214-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="37214-124">"\kappa"</span></span>
- <span data-ttu-id="37214-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="37214-125">"\psi"</span></span>
- <span data-ttu-id="37214-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="37214-126">"\alpha"</span></span>
- <span data-ttu-id="37214-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="37214-127">"\beta"</span></span>
- <span data-ttu-id="37214-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="37214-128">"\gamma"</span></span>
- <span data-ttu-id="37214-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="37214-129">"\delta"</span></span>
- <span data-ttu-id="37214-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="37214-130">"\omega"</span></span>
- <span data-ttu-id="37214-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="37214-131">"\bra"</span></span>
- <span data-ttu-id="37214-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="37214-132">"\ket"</span></span>
- <span data-ttu-id="37214-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="37214-133">"\boldone"</span></span>
- <span data-ttu-id="37214-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="37214-134">"\\\\"</span></span>
- <span data-ttu-id="37214-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="37214-135">"\\"</span></span>
- <span data-ttu-id="37214-136">"="</span><span class="sxs-lookup"><span data-stu-id="37214-136">"="</span></span>
- <span data-ttu-id="37214-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="37214-137">"\frac"</span></span>
- <span data-ttu-id="37214-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="37214-138">"\text"</span></span>
- <span data-ttu-id="37214-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="37214-139">"\mapsto"</span></span>
- <span data-ttu-id="37214-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="37214-140">"\dagger"</span></span>
- <span data-ttu-id="37214-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="37214-141">"\to"</span></span>
- <span data-ttu-id="37214-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="37214-142">"\begin{cases}"</span></span>
- <span data-ttu-id="37214-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="37214-143">"\end{cases}"</span></span>
- <span data-ttu-id="37214-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="37214-144">"\operatorname"</span></span>
- <span data-ttu-id="37214-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="37214-145">"\braket"</span></span>
- <span data-ttu-id="37214-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="37214-146">"\id"</span></span>
- <span data-ttu-id="37214-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="37214-147">"\expect"</span></span>
- <span data-ttu-id="37214-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="37214-148">"\defeq"</span></span>
- <span data-ttu-id="37214-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="37214-149">"\variance"</span></span>
- <span data-ttu-id="37214-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="37214-150">"\dd"</span></span>
- <span data-ttu-id="37214-151">"&"</span><span class="sxs-lookup"><span data-stu-id="37214-151">"&"</span></span>
- <span data-ttu-id="37214-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="37214-152">"\begin{align}"</span></span>
- <span data-ttu-id="37214-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="37214-153">"\end{align}"</span></span>
- <span data-ttu-id="37214-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="37214-154">"\Lambda"</span></span>
- <span data-ttu-id="37214-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="37214-155">"\lambda"</span></span>
- <span data-ttu-id="37214-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="37214-156">"\Omega"</span></span>
- <span data-ttu-id="37214-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="37214-157">"\mathrm"</span></span>
- <span data-ttu-id="37214-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="37214-158">"\left"</span></span>
- <span data-ttu-id="37214-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="37214-159">"\right"</span></span>
- <span data-ttu-id="37214-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="37214-160">"\qquad"</span></span>
- <span data-ttu-id="37214-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="37214-161">"\times"</span></span>
- <span data-ttu-id="37214-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="37214-162">"\big"</span></span>
- <span data-ttu-id="37214-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="37214-163">"\langle"</span></span>
- <span data-ttu-id="37214-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="37214-164">"\rangle"</span></span>
- <span data-ttu-id="37214-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="37214-165">"\bigg"</span></span>
- <span data-ttu-id="37214-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="37214-166">"\Big"</span></span>
- <span data-ttu-id="37214-167">"|"</span><span class="sxs-lookup"><span data-stu-id="37214-167">"|"</span></span>
- <span data-ttu-id="37214-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="37214-168">"\mathbb"</span></span>
- <span data-ttu-id="37214-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="37214-169">"\vec"</span></span>
- <span data-ttu-id="37214-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="37214-170">"\in"</span></span>
- <span data-ttu-id="37214-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="37214-171">"\texttt"</span></span>
- <span data-ttu-id="37214-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="37214-172">"\ne"</span></span>
- <span data-ttu-id="37214-173">"<"</span><span class="sxs-lookup"><span data-stu-id="37214-173">"<"</span></span>
- <span data-ttu-id="37214-174">">"</span><span class="sxs-lookup"><span data-stu-id="37214-174">">"</span></span>
- <span data-ttu-id="37214-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="37214-175">"\leq"</span></span>
- <span data-ttu-id="37214-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="37214-176">"\geq"</span></span>
- <span data-ttu-id="37214-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="37214-177">"~~"</span></span>
- <span data-ttu-id="37214-178">"~"</span><span class="sxs-lookup"><span data-stu-id="37214-178">"~"</span></span>
- <span data-ttu-id="37214-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="37214-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="37214-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="37214-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="37214-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="37214-181">"\_"</span></span>

---

# <a name="pauli-measurements"></a><span data-ttu-id="37214-182">Pauli 度量值</span><span class="sxs-lookup"><span data-stu-id="37214-182">Pauli Measurements</span></span>

<span data-ttu-id="37214-183">在前面的讨论中，我们重点介绍计算基础度量值。</span><span class="sxs-lookup"><span data-stu-id="37214-183">In the previous discussions, we have focused on computational basis measurements.</span></span>
<span data-ttu-id="37214-184">事实上，从符号的角度来看，量子计算会出现其他常见的度量，这在计算基础度量方面非常方便。</span><span class="sxs-lookup"><span data-stu-id="37214-184">In fact, there are other common measurements that occur in quantum computing that, from a notational perspective, are convenient to express in terms of computational basis measurements.</span></span>
<span data-ttu-id="37214-185">当你使用时 Q# ，你将遇到的最常见的度量值可能是 *Pauli 的度量值*，它将计算基础度量值纳入其他基准，并在不同 qubits 之间进行奇偶校验。</span><span class="sxs-lookup"><span data-stu-id="37214-185">As you work with Q#, the most common kind of measurements that you'll run into will likely be *Pauli measurements*, which generalize computational basis measurements to include measurements in other bases, and of parity between different qubits.</span></span>
<span data-ttu-id="37214-186">在这种情况下，通常会讨论度量 Pauli 运算符，通常是运算符（例如 $ x、Y、z $ 或 $ z \otimes z、x \otimes x、x \otimes Y $ 等）。</span><span class="sxs-lookup"><span data-stu-id="37214-186">In such cases, it is common to discuss measuring a Pauli operator, in general an operator such as $X,Y,Z$ or $Z\otimes Z, X\otimes X, X\otimes Y$, and so forth.</span></span>

> [!TIP]
<span data-ttu-id="37214-187">> 在中 Q# ，多 Qubit Pauli 运算符通常由类型的数组表示 `Pauli[]` 。</span><span class="sxs-lookup"><span data-stu-id="37214-187">> In Q#, multi-qubit Pauli operators are generally represented by arrays of type `Pauli[]`.</span></span>
<span data-ttu-id="37214-188">> 例如，若要表示 $ X \otimes Z \otimes Y $ ，可以使用数组 `[PauliX, PauliZ, PauliY]` 。</span><span class="sxs-lookup"><span data-stu-id="37214-188">> For example, to represent $X \otimes Z \otimes Y$, you can use the array `[PauliX, PauliZ, PauliY]`.</span></span>

<span data-ttu-id="37214-189">在量程错误纠正的子字段中，讨论 Pauli 运算符的度量值尤其常见。</span><span class="sxs-lookup"><span data-stu-id="37214-189">Discussing measurement in terms of Pauli operators is especially common in the subfield of quantum error correction.</span></span>
<span data-ttu-id="37214-190">在中 Q# ，我们遵循类似的约定; 现在我们介绍了此替代方法视图。</span><span class="sxs-lookup"><span data-stu-id="37214-190">In Q#, we follow a similar convention; we now explain this alternative view of measurements.</span></span>

<span data-ttu-id="37214-191">在深入了解有关如何思考 Pauli 度量的详细信息之前，请考虑测量量程内单个 qubit 对量程状态的作用。</span><span class="sxs-lookup"><span data-stu-id="37214-191">Before delving into the details of how to think of a Pauli measurement, it is useful to think about what measuring a single qubit inside a quantum computer does to the quantum state.</span></span>
<span data-ttu-id="37214-192">假设我们有一个 $ qubit 的 $ 量程状态，然后将一个 qubit 立即测量为 $ 2 ^ n 的一半 $ ，这可能是状态的一半。</span><span class="sxs-lookup"><span data-stu-id="37214-192">Imagine that we have an $n$-qubit quantum state; then measuring one qubit immediately rules out half of the $2^n$ possibilities that state could be in.</span></span>
<span data-ttu-id="37214-193">换言之，该度量值将量程状态投影到两个半个空格。</span><span class="sxs-lookup"><span data-stu-id="37214-193">In other words, the measurement projects the quantum state onto one of two half-spaces.</span></span>
<span data-ttu-id="37214-194">我们可以通用化我们对量化指标的看法，以反映这种直觉。</span><span class="sxs-lookup"><span data-stu-id="37214-194">We can generalize the way we think about measurement to reflect this intuition.</span></span>

<span data-ttu-id="37214-195">为了简洁地识别这些 subspaces，我们需要一种用于描述这些的语言。</span><span class="sxs-lookup"><span data-stu-id="37214-195">In order to concisely identify these subspaces, we need a language for describing them.</span></span>
<span data-ttu-id="37214-196">描述这两个 subspaces 的一种方法是通过一个矩阵来指定它们，该矩阵只包含两个唯一的本征值，约定为 $ \pm 1 $ 。</span><span class="sxs-lookup"><span data-stu-id="37214-196">One way to describe the two subspaces is by specifying them through a matrix that just has two unique eigenvalues, taken by convention to be $\pm 1$.</span></span>
<span data-ttu-id="37214-197">有关以这种方式描述 subspaces 的简单示例，请考虑使用 $ Z $ ：</span><span class="sxs-lookup"><span data-stu-id="37214-197">For a simple example of describing subspaces in this way, consider $Z$:</span></span>

$$
\begin{align}
  <span data-ttu-id="37214-198">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="37214-198">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="37214-199">通过读取 Pauli 矩阵的对角线元素 $ $ ，我们可以看到 $ Z $ 有两个本征向量， $ \ket { 0 } $ 和 $ \ket { 1 } $ ，其中包含相应的本征值 $ \pm 1 $ 。</span><span class="sxs-lookup"><span data-stu-id="37214-199">By reading the diagonal elements of the Pauli-$Z$ matrix, we can see that $Z$ has two eigenvectors, $\ket{0}$ and $\ket{1}$, with corresponding eigenvalues $\pm 1$.</span></span>
<span data-ttu-id="37214-200">因此，如果我们测量 qubit 并获取与 `Zero` 状态 0) 对应的 ($ \ket { } $ ，则我们知道 qubit 的状态是 $ Z 运算符的 + 1 $ eigenstate $ $ 。</span><span class="sxs-lookup"><span data-stu-id="37214-200">Thus, if we measure the qubit and obtain `Zero` (corresponding to the state $\ket{0}$), we know that the state of our qubit is a $+1$ eigenstate of the $Z$ operator.</span></span>
<span data-ttu-id="37214-201">同样，如果我们获得 `One` ，我们知道我们 qubit 的状态是 $ Z 的-1 $ eigenstate $ $ 。此过程被称为 "度量 Pauli Z" 的 Pauli 度量语言 $ $ ，完全等同于执行计算基础度量。</span><span class="sxs-lookup"><span data-stu-id="37214-201">Similarly, if we obtain `One`, we know that the state of our qubit is a $-1$ eigenstate of $Z$. This process is referred to in the language of Pauli measurements as "measuring Pauli $Z$," and is entirely equivalent to performing a computational basis measurement.</span></span>

<span data-ttu-id="37214-202">$ \times $ 作为 Z 的单一转换的任意 2 2 矩阵 $ $ 还满足此条件。</span><span class="sxs-lookup"><span data-stu-id="37214-202">Any $2\times 2$ matrix that is a unitary transformation of $Z$ also satisfies this criteria.</span></span>
<span data-ttu-id="37214-203">也就是说，我们还可以使用矩阵 $ a = u ^ \dagger Z u $ ，其中 $ u $ 是任何其他的单一矩阵，以便为矩阵定义 $ \pm 1 本征向量中度量值的两个结果 $ 。</span><span class="sxs-lookup"><span data-stu-id="37214-203">That is, we could also use a matrix $A=U^\dagger Z U$, where $U$ is any other unitary matrix, to give a matrix that defines the two outcomes of a measurement in its $\pm 1$ eigenvectors.</span></span>
<span data-ttu-id="37214-204">Pauli 度量值的表示法通过标识 X、Y、Z 度量值来引用这种单一等效性，该度量 $ $ 值可以从 qubit 获取信息。</span><span class="sxs-lookup"><span data-stu-id="37214-204">The notation of Pauli measurements references this unitary equivalence by identifying $X,Y,Z$ measurements as equivalent measurements that one could do to gain information from a qubit.</span></span>
<span data-ttu-id="37214-205">为方便起见，下面提供了这些度量值。</span><span class="sxs-lookup"><span data-stu-id="37214-205">These measurements are given below for convenience.</span></span>


<span data-ttu-id="37214-206">|Pauli 度量  | 单一转换  |</span><span class="sxs-lookup"><span data-stu-id="37214-206">|Pauli Measurement  |Unitary transformation  |</span></span>
|-------------------|------------------------|
<span data-ttu-id="37214-207">|$ $ Z |               $\boldone$             |</span><span class="sxs-lookup"><span data-stu-id="37214-207">| $Z$               | $\boldone$             |</span></span>
<span data-ttu-id="37214-208">|$ $ X |$H               $                    |</span><span class="sxs-lookup"><span data-stu-id="37214-208">| $X$               | $H$                    |</span></span>
<span data-ttu-id="37214-209">|$ $ Y |$HS ^               {\dagger}$         |</span><span class="sxs-lookup"><span data-stu-id="37214-209">| $Y$               | $HS^{\dagger}$         |</span></span>

<span data-ttu-id="37214-210">也就是说，使用这种语言时，"度量值 $ Y $ " 等效于应用 $ HS ^， \dagger $ 然后以计算为基础，其中 [`S`](xref:microsoft.quantum.intrinsic.s) 是一个内部量程操作，有时称为 "阶段入口"，可由单一矩阵模拟</span><span class="sxs-lookup"><span data-stu-id="37214-210">That is, using this language, "measure $Y$" is equivalent to applying $HS^\dagger$ and then measuring in the computational basis, where [`S`](xref:microsoft.quantum.intrinsic.s) is an intrinsic quantum operation sometimes called the "phase gate," and can be simulated by the unitary matrix</span></span>

$$
\begin{align}
    <span data-ttu-id="37214-211">S =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="37214-211">S = \begin{bmatrix}</span></span>
        <span data-ttu-id="37214-212">1 & 0 \\\\ 0 & i \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="37214-212">1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="37214-213">它还等效于将 $ HS ^ 应用于 \dagger $ 量程状态向量，然后再测量 $ Z，以使 $ 以下操作等效于 `Measure([PauliY], [q])` ：</span><span class="sxs-lookup"><span data-stu-id="37214-213">It is also equivalent to applying $HS^\dagger$ to the quantum state vector and then measuring $Z$, such that the following operation is equivalent to `Measure([PauliY], [q])`:</span></span>

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        Adjoint S(q);
        H(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

<span data-ttu-id="37214-214">然后，将转换回计算基础，并将其应用于量程状态向量，从而找到正确的状态 $ $ ; 在上面的代码段中，转换回计算基础会通过使用块自动进行处理 `within … apply` 。</span><span class="sxs-lookup"><span data-stu-id="37214-214">The correct state would then be found by transforming back to the computational basis, which amounts to applying $SH$ to the quantum state vector; in the above snippet, the transformation back to the computational basis is handled automatically by the use of the `within … apply` block.</span></span>

<span data-ttu-id="37214-215">在中 Q# ，我们说结果---也就是说，从状态---交互中提取的传统信息由 `Result` 值 $ j \in \\ { \texttt { 零提供 } ， \texttt { 一个 } \\ } $ 指示结果是否处于 $ Pauli 运算符度量的 (-1) ^ j $ eigenspace 中。</span><span class="sxs-lookup"><span data-stu-id="37214-215">In Q#, we say the outcome---that is, the classical information extracted from interacting with the state---is given by a `Result` value $j \in \\{\texttt{Zero}, \texttt{One}\\}$ indicating if the result is in the $(-1)^j$ eigenspace of the Pauli operator measured.</span></span>


## <a name="multiple-qubit-measurements"></a><span data-ttu-id="37214-216">多 qubit 度量</span><span class="sxs-lookup"><span data-stu-id="37214-216">Multiple-qubit measurements</span></span>

<span data-ttu-id="37214-217">多 qubit Pauli 运算符的度量值的定义类似，如下所示：</span><span class="sxs-lookup"><span data-stu-id="37214-217">Measurements of multi-qubit Pauli operators are defined similarly, as seen from:</span></span>

$$
<span data-ttu-id="37214-218">Z \otimes z = \begin{bmatrix} 1 & 0 & 0 0 0 & \\\\  0 & -1 0 0 0 0 & & \\\\ & & -1 & 0 \\\\ & & & \end{bmatrix} 0 0 0 1。</span><span class="sxs-lookup"><span data-stu-id="37214-218">Z\otimes Z = \begin{bmatrix}1 &0 &0&0\\\\  0&-1&0&0\\\\ 0&0&-1&0\\\\ 0&0&0&1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="37214-219">因此，两个 Pauli 运算符的 tensor 产品构成一个矩阵，其中包含 $ $ 两个由 $ + 1 $ 和 $ -1 本征值 $ 组成的空格。</span><span class="sxs-lookup"><span data-stu-id="37214-219">Thus the tensor products of two Pauli-$Z$ operators forms a matrix composed of two spaces consisting of $+1$ and $-1$ eigenvalues.</span></span>
<span data-ttu-id="37214-220">与单一 qubit 的情况一样，两者都构成一半空间，这意味着可访问的矢量空间的一半属于 $ + 1 $ eigenspace，另一半是 $ -1 $ eigenspace。</span><span class="sxs-lookup"><span data-stu-id="37214-220">As with the single-qubit case, both constitute a half-space meaning that half of the accessible vector space belongs to the $+1$ eigenspace and the remaining half to the $-1$ eigenspace.</span></span>
<span data-ttu-id="37214-221">通常，可以很容易地从 tensor 产品的定义中看出 Pauli 运算符的任何 tensor 产品 $ $ 和标识也服从这一点。</span><span class="sxs-lookup"><span data-stu-id="37214-221">In general, it is easy to see from the definition of the tensor product that any tensor product of Pauli-$Z$ operators and the identity also obeys this.</span></span>
<span data-ttu-id="37214-222">例如，应用于对象的</span><span class="sxs-lookup"><span data-stu-id="37214-222">For example,</span></span>

$$
\begin{align}
    <span data-ttu-id="37214-223">\otimes \boldone Z =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="37214-223">Z \otimes \boldone = \begin{bmatrix}</span></span>
        <span data-ttu-id="37214-224">1 & 0 & 0 0 &\\\\</span><span class="sxs-lookup"><span data-stu-id="37214-224">1 &  0 &  0 &  0 \\\\</span></span>
        <span data-ttu-id="37214-225">0 &  1 &  0 &  0 \\\\</span><span class="sxs-lookup"><span data-stu-id="37214-225">0 &  1 &  0 &  0 \\\\</span></span>
        <span data-ttu-id="37214-226">0 &  0 & -1 &  0 \\\\</span><span class="sxs-lookup"><span data-stu-id="37214-226">0 &  0 & -1 &  0 \\\\</span></span>
        <span data-ttu-id="37214-227">0 &  0 &  0 & -1 \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="37214-227">0 &  0 &  0 & -1 \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="37214-228">与之前一样，此类矩阵的任何单一转换还将描述 \pm 1 本征值标记的两个半角空格 $ $ 。</span><span class="sxs-lookup"><span data-stu-id="37214-228">As before, any unitary transformation of such matrices also describes two half-spaces labeled by $\pm 1$ eigenvalues.</span></span>
<span data-ttu-id="37214-229">例如， $ x \otimes x = h \otimes h (z \otimes z) h \otimes h $  与 z HXH 的标识 $ 相同 = $ 。</span><span class="sxs-lookup"><span data-stu-id="37214-229">For example, $X\otimes X = H\otimes H(Z\otimes Z)H\otimes H$  from the identity that $Z=HXH$.</span></span>
<span data-ttu-id="37214-230">与 qubit 情况类似，所有 qubit Pauli 度量值都可以作为 $ u ^ \dagger (Z \otimes \id) u 写入 $ 4 个 $ \times $ 单一矩阵 $ u $ 。枚举下表中的转换。</span><span class="sxs-lookup"><span data-stu-id="37214-230">Similar to the one-qubit case, all two-qubit Pauli-measurements can be written as $U^\dagger (Z\otimes \id) U$ for $4\times 4$ unitary matrices $U$. We enumerate the transformations in the following table.</span></span>

> [!NOTE]
<span data-ttu-id="37214-231">>在下表中，我们使用 $ \operatorname { SWAP } $ 指示矩阵 >$$</span><span class="sxs-lookup"><span data-stu-id="37214-231">> In the table below, we use $\operatorname{SWAP}$ to indicate the matrix > $$</span></span>
<span data-ttu-id="37214-232">> \begin{align}</span><span class="sxs-lookup"><span data-stu-id="37214-232">> \begin{align}</span></span>
<span data-ttu-id="37214-233">>     \operatorname{交换 } &=</span><span class="sxs-lookup"><span data-stu-id="37214-233">>     \operatorname{SWAP} & =</span></span>
<span data-ttu-id="37214-234">>     \left (\begin { 矩阵}</span><span class="sxs-lookup"><span data-stu-id="37214-234">>     \left(\begin{matrix}</span></span>
<span data-ttu-id="37214-235">>1 & 0 & 0 0 &\\\\</span><span class="sxs-lookup"><span data-stu-id="37214-235">>         1 & 0 & 0 & 0 \\\\</span></span>
<span data-ttu-id="37214-236">>         0 & 0 & 1 & 0 \\\\</span><span class="sxs-lookup"><span data-stu-id="37214-236">>         0 & 0 & 1 & 0 \\\\</span></span>
<span data-ttu-id="37214-237">>         0 & 1 & 0 & 0 \\\\</span><span class="sxs-lookup"><span data-stu-id="37214-237">>         0 & 1 & 0 & 0 \\\\</span></span>
<span data-ttu-id="37214-238">>0 & 0 & 0 & 1 > \end { 矩阵 } \right) >     \end{align}</span><span class="sxs-lookup"><span data-stu-id="37214-238">>         0 & 0 & 0 & 1 >     \end{matrix}\right) > \end{align}</span></span>
<span data-ttu-id="37214-239">> $$</span><span class="sxs-lookup"><span data-stu-id="37214-239">> $$</span></span>
<span data-ttu-id="37214-240">> 用于模拟内部操作 [`SWAP`](xref:microsoft.quantum.intrinsic) 。</span><span class="sxs-lookup"><span data-stu-id="37214-240">> used to simulate the intrinsic operation [`SWAP`](xref:microsoft.quantum.intrinsic).</span></span>

<span data-ttu-id="37214-241">|Pauli 度量     | 单一转换  |</span><span class="sxs-lookup"><span data-stu-id="37214-241">|Pauli Measurement     |Unitary transformation  |</span></span>
|----------------------|------------------------|
<span data-ttu-id="37214-242">|$ \otimes \boldone Z $| $\boldone\otimes\boldone$|</span><span class="sxs-lookup"><span data-stu-id="37214-242">| $Z\otimes \boldone$ | $\boldone\otimes \boldone$ |</span></span>
<span data-ttu-id="37214-243">|$ \otimes \boldone X $| $\otimes \boldone H $|</span><span class="sxs-lookup"><span data-stu-id="37214-243">| $X\otimes \boldone$ | $H\otimes \boldone$ |</span></span>
<span data-ttu-id="37214-244">|$ \otimes \boldone Y $| $HS \dagger \otimes \boldone ^ $|</span><span class="sxs-lookup"><span data-stu-id="37214-244">| $Y\otimes \boldone$ | $HS^\dagger\otimes \boldone$ |</span></span>
<span data-ttu-id="37214-245">|$\boldone \otimesZ $ | $ \operatorname { 交换 } $|</span><span class="sxs-lookup"><span data-stu-id="37214-245">| $\boldone \otimes Z$ | $\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="37214-246">|$\boldone \otimesX $ | $ (H \otimes \boldone) \operatorname { 交换 } $|</span><span class="sxs-lookup"><span data-stu-id="37214-246">| $\boldone \otimes X$ | $(H\otimes \boldone)\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="37214-247">|$\boldone \otimesY $ | $ (HS ^ \dagger \otimes \boldone) \operatorname { 交换 } $|</span><span class="sxs-lookup"><span data-stu-id="37214-247">| $\boldone \otimes Y$ | $(HS^\dagger\otimes \boldone)\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="37214-248">|$Z \otimesZ $ | $ \operatorname { cnot-contains } \_ { 10 } $|</span><span class="sxs-lookup"><span data-stu-id="37214-248">| $Z\otimes Z$ | $\operatorname{CNOT}\_{10}$ |</span></span>
<span data-ttu-id="37214-249">|$X \otimesZ $ | $ \operatorname { cnot-contains } \_ { 10 } (H \otimes \boldone) $|</span><span class="sxs-lookup"><span data-stu-id="37214-249">| $X\otimes Z$ | $\operatorname{CNOT}\_{10}(H\otimes \boldone)$ |</span></span>
<span data-ttu-id="37214-250">|$Y \otimesZ $ | $ \operatorname { cnot-contains } \_ { 10 } (HS ^ \dagger \otimes \boldone) $|</span><span class="sxs-lookup"><span data-stu-id="37214-250">| $Y\otimes Z$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes \boldone)$ |</span></span>
<span data-ttu-id="37214-251">|$Z \otimesX $ | $ \operatorname { cnot-contains } \_ { 10 } (\boldone \otimes H) $|</span><span class="sxs-lookup"><span data-stu-id="37214-251">| $Z\otimes X$ | $\operatorname{CNOT}\_{10}(\boldone\otimes H)$ |</span></span>
<span data-ttu-id="37214-252">|$X \otimesX $ | $ \operatorname { cnot-contains } \_ { 10 } (h \otimes h) $|</span><span class="sxs-lookup"><span data-stu-id="37214-252">| $X\otimes X$ | $\operatorname{CNOT}\_{10}(H\otimes H)$ |</span></span>
<span data-ttu-id="37214-253">|$Y \otimesX $ | $ \operatorname { cnot-contains } \_ { 10 } (HS ^ \dagger \otimes H) $|</span><span class="sxs-lookup"><span data-stu-id="37214-253">| $Y\otimes X$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes H)$ |</span></span>
<span data-ttu-id="37214-254">|$Z \otimesY $ | $ \operatorname { cnot-contains } \_ { 10 } (\boldone \otimes HS ^ \dagger) $|</span><span class="sxs-lookup"><span data-stu-id="37214-254">| $Z\otimes Y$ | $\operatorname{CNOT}\_{10}(\boldone \otimes HS^\dagger)$ |</span></span>
<span data-ttu-id="37214-255">|$X \otimesY $ | $ \operatorname { cnot-contains } \_ { 10 } (H \otimes HS ^ \dagger) $|</span><span class="sxs-lookup"><span data-stu-id="37214-255">| $X\otimes Y$ | $\operatorname{CNOT}\_{10}(H\otimes HS^\dagger)$ |</span></span>
<span data-ttu-id="37214-256">|$Y \otimesY $ | $ \operatorname { cnot-contains } \_ { 10 } (HS ^ \dagger \otimes HS \dagger) $|</span><span class="sxs-lookup"><span data-stu-id="37214-256">| $Y\otimes Y$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes HS^\dagger)$ |</span></span>

<span data-ttu-id="37214-257">[`CNOT`](xref:microsoft.quantum.intrinsic.cnot)此时，操作出现的原因如下。</span><span class="sxs-lookup"><span data-stu-id="37214-257">Here, the [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operation appears for the following reason.</span></span>
<span data-ttu-id="37214-258">不包含矩阵的每个 Pauli 度量 $ \boldone $ 都等效于以上推理的单一到 $ z \otimes z $ 。</span><span class="sxs-lookup"><span data-stu-id="37214-258">Each Pauli measurement that does not include the $\boldone$ matrix is equivalent up to a unitary to $Z\otimes Z$ by the above reasoning.</span></span>
<span data-ttu-id="37214-259">$Z z 的本征值 \otimes $ 仅依赖于构成每个计算基础向量的 qubits 的奇偶校验，并且用于计算此奇偶校验并将其存储在第一位的受控非运算。</span><span class="sxs-lookup"><span data-stu-id="37214-259">The eigenvalues of $Z\otimes Z$ only depend on the parity of the qubits that comprise each computational basis vector, and the controlled-not operations serve to compute this parity and store it in the first bit.</span></span>
<span data-ttu-id="37214-260">然后，在度量第一位后，可以恢复生成的半角空格的标识，这相当于测量 Pauli 运算符。</span><span class="sxs-lookup"><span data-stu-id="37214-260">Then once the first bit is measured, we can recover the identity of the resultant half-space, which is equivalent to measuring the Pauli operator.</span></span>

<span data-ttu-id="37214-261">另外一个注意事项：尽管度量 $ z \otimes z 与 $ 按顺序测量 $ z \otimes \mathbb { 1 } $ 和 1 z 的顺序相同 $ \mathbb { ，但这种 } \otimes $ 假定是 false。</span><span class="sxs-lookup"><span data-stu-id="37214-261">One additional note: while it may be tempting to assume that measuring $Z\otimes Z$ is the same as sequentially measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$, this assumption would be false.</span></span>
<span data-ttu-id="37214-262">原因是度量 $ z \otimes z $ 将量程状态投影到了 $ 这些运算符的 + 1 $ 或 $ -1 $ eigenstate 中。</span><span class="sxs-lookup"><span data-stu-id="37214-262">The reason is that measuring $Z\otimes Z$ projects the quantum state into either the $+1$ or $-1$ eigenstate of these operators.</span></span>
<span data-ttu-id="37214-263">$先度量 z \otimes \mathbb { 1 } $ ，然后再 $ \mathbb { } \otimes $ 将量程状态向量投影到 Z 1 的半个空格上 $ \otimes \mathbb { } $ ，然后计算为 $ \mathbb { 1 } \otimes z $ 的半个空格。由于有四个计算基准向量，同时执行这两个度量会将状态降到一个四分之一空间，因此将其减少为单个计算基础向量。</span><span class="sxs-lookup"><span data-stu-id="37214-263">Measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$ projects the quantum state vector first onto a half space of $Z\otimes \mathbb{1}$ and then onto a half space of $\mathbb{1} \otimes Z$. As there are four computational basis vectors, performing both measurements reduces the state to a quarter-space and hence reduces it to a single computational basis vector.</span></span>

## <a name="correlations-between-qubits"></a><span data-ttu-id="37214-264">量子位之间的关联</span><span class="sxs-lookup"><span data-stu-id="37214-264">Correlations between qubits</span></span>
<span data-ttu-id="37214-265">另一种方法是查看度量标准（例如 $ x x 或 z z）的 tensor 产品， \otimes $ $ \otimes $ 这些度量值使你可以查看在这两个 qubits 间的关联中存储的信息。</span><span class="sxs-lookup"><span data-stu-id="37214-265">Another way of looking at measuring tensor products of Pauli matrices such as $X\otimes X$ or $Z\otimes Z$ is that these measurements let you look at information stored in the correlations between the two qubits.</span></span>
<span data-ttu-id="37214-266">度量 $ X \otimes \id $ 使你可以查看在第一个 qubit 中本地存储的信息。</span><span class="sxs-lookup"><span data-stu-id="37214-266">Measuring $X\otimes \id$ lets you look at information that is locally stored in the first qubit.</span></span>
<span data-ttu-id="37214-267">尽管这两种类型的度量在量程计算中都同样很有价值，但前者会导致量程计算的强大功能。</span><span class="sxs-lookup"><span data-stu-id="37214-267">While both types of measurements are equally valuable in quantum computing, the former illuminates the power of quantum computing.</span></span>
<span data-ttu-id="37214-268">它在量程计算中表现出这一点，通常情况下，您想要学习的信息并不存储在任何单个 qubit 中，而是一次只存储在所有 qubits 中，因此，这种情况下，只能通过联合 (度量来查看 $ 此信息，例如 z \otimes z $) 会将此信息变为清单。</span><span class="sxs-lookup"><span data-stu-id="37214-268">It reveals that in quantum computing, often the information you wish to learn is not stored in any single qubit but rather stored non-locally in all the qubits at once, and therefore only by looking at it through a joint measurement (e.g. $Z\otimes Z$) does this information become manifest.</span></span>

<span data-ttu-id="37214-269">例如，在 "纠错" 中，我们经常想要了解在学习有关我们尝试保护的状态时所发生的错误。</span><span class="sxs-lookup"><span data-stu-id="37214-269">For example, in error correction, we often wish to learn what error occurred while learning nothing about the state that we're trying to protect.</span></span>
<span data-ttu-id="37214-270">"[位翻转" 代码示例](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code)显示了如何使用 $ Z \otimes z \otimes \id $ 和 $ \id \otimes z \otimes z $ < 等度量来执行此操作的示例。--TODO：在载入的情况下，将其更改为指向示例浏览器的链接。</span><span class="sxs-lookup"><span data-stu-id="37214-270">The [bit-flip code sample](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code) shows an example of how you can do that using measurements like $Z \otimes Z \otimes \id$ and $\id \otimes Z \otimes Z$. <!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded.</span></span> -->

<span data-ttu-id="37214-271">$ \otimes \otimes \otimes \boldone $ 也可以测量 X Y Z 等任意 Pauli 运算符。</span><span class="sxs-lookup"><span data-stu-id="37214-271">Arbitrary Pauli operators such as $X\otimes Y \otimes Z \otimes \boldone$ can also be measured.</span></span>
<span data-ttu-id="37214-272">Pauli 运算符的所有此类 tensor 产品仅具有两个本征值 $ \pm 1 $ ，两个 eigenspaces 构成整个矢量空间的半个空格。</span><span class="sxs-lookup"><span data-stu-id="37214-272">All such tensor products of Pauli operators have only two eigenvalues $\pm 1$ and both eigenspaces constitute half-spaces of the entire vector space.</span></span>
<span data-ttu-id="37214-273">因此，它们符合上面所述的要求。</span><span class="sxs-lookup"><span data-stu-id="37214-273">Thus they coincide with the requirements stated above.</span></span>

<span data-ttu-id="37214-274">在中 Q# ， $ $ 如果度量值生成的结果为 eigenspace ( 的 $) ^ j，则此类度量值将返回 j $ 。</span><span class="sxs-lookup"><span data-stu-id="37214-274">In Q#, such measurements return $j$ if the measurement yields a result in the eigenspace of sign $(-1)^j$.</span></span>
<span data-ttu-id="37214-275">将 Pauli 度量作为内置功能 Q# 非常有用，因为测量此类运算符需要使用受控-NOT 入口和基础转换的长链来描述将 $ $ 操作表达为 Z 和的 tensor 产品所需的 diagonalizing U 门 $ $ $ \id $ 。</span><span class="sxs-lookup"><span data-stu-id="37214-275">Having Pauli measurements as a built-in feature in Q# is helpful because measuring such operators requires long chains of controlled-NOT gates and basis transformations to describe the diagonalizing $U$ gate needed to express the operation as a tensor product of $Z$ and $\id$.</span></span>
<span data-ttu-id="37214-276">通过能够指定想要执行其中一项预定义度量，无需担心如何转换基础，以使计算基础度量提供必要的信息。</span><span class="sxs-lookup"><span data-stu-id="37214-276">By being able to specify that you wish to do one of these pre-defined measurements, you don't need to worry about how to transform your basis such that a computational basis measurement provides the necessary information.</span></span>
<span data-ttu-id="37214-277">Q# 自动为你处理所有必要的基础转换。</span><span class="sxs-lookup"><span data-stu-id="37214-277">Q# handles all the necessary basis transformations for you automatically.</span></span>
<span data-ttu-id="37214-278">有关详细信息，请参阅 [`Measure`](xref:microsoft.quantum.intrinsic.measure) 和 [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) 操作。</span><span class="sxs-lookup"><span data-stu-id="37214-278">For more information, see the [`Measure`](xref:microsoft.quantum.intrinsic.measure) and [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operations.</span></span>

## <a name="the-no-cloning-theorem"></a><span data-ttu-id="37214-279">无克隆定理</span><span class="sxs-lookup"><span data-stu-id="37214-279">The No-Cloning Theorem</span></span>

<span data-ttu-id="37214-280">量程信息非常强大。</span><span class="sxs-lookup"><span data-stu-id="37214-280">Quantum information is powerful.</span></span>
<span data-ttu-id="37214-281">它使我们能够以指数形式比最佳已知传统算法更快地执行令人惊叹的东西，或高效模拟经典需要指数成本来准确模拟的相关 electron 系统。</span><span class="sxs-lookup"><span data-stu-id="37214-281">It enables us to do amazing things such as factor numbers exponentially faster than the best known classical algorithms, or efficiently simulate correlated electron systems that classically require exponential cost to simulate accurately.</span></span>
<span data-ttu-id="37214-282">但对量程计算的强大功能有一些限制。</span><span class="sxs-lookup"><span data-stu-id="37214-282">However, there are limitations to the power of quantum computing.</span></span>
<span data-ttu-id="37214-283">这种限制是由 *无克隆定理*提供的。</span><span class="sxs-lookup"><span data-stu-id="37214-283">One such limitation is given by the *No-Cloning Theorem*.</span></span>

<span data-ttu-id="37214-284">不克隆的定理为名称正好。</span><span class="sxs-lookup"><span data-stu-id="37214-284">The No-Cloning Theorem is aptly named.</span></span>
<span data-ttu-id="37214-285">它不允许量程计算机克隆通用量程状态。</span><span class="sxs-lookup"><span data-stu-id="37214-285">It disallows cloning of generic quantum states by a quantum computer.</span></span>
<span data-ttu-id="37214-286">定理的证明非常简单。</span><span class="sxs-lookup"><span data-stu-id="37214-286">The proof of the theorem is remarkably straightforward.</span></span>
<span data-ttu-id="37214-287">虽然在这里我们的讨论中，无克隆定理的完整证明是一项很少的技术，但是，在我们的 (范围内，无需额外的辅助 qubits 的证明可用于计算中的草稿空间，并可以在中轻松地使用和管理 Q# ，请参阅 [借用 qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)) 。</span><span class="sxs-lookup"><span data-stu-id="37214-287">While a full proof of the no-cloning theorem is a little too technical for our discussion here, the proof in the case of no additional auxiliary qubits is within our scope (auxiliary qubits are qubits used for scratch space during a computation and are easily used and managed in Q#, see [borrowed qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).</span></span>

<span data-ttu-id="37214-288">对于此类量程计算机，克隆操作必须由单一矩阵进行描述。</span><span class="sxs-lookup"><span data-stu-id="37214-288">For such a quantum computer, the cloning operation must be described by a unitary matrix.</span></span>
<span data-ttu-id="37214-289">我们不允许进行度量，因为它会损坏我们尝试克隆的量程状态。</span><span class="sxs-lookup"><span data-stu-id="37214-289">We disallow measurement, since it would corrupt the quantum state we are trying to clone.</span></span>
<span data-ttu-id="37214-290">要模拟克隆操作，我们希望使用单一矩阵来使 $$</span><span class="sxs-lookup"><span data-stu-id="37214-290">To simulate the cloning operation, we want the unitary matrix used to have the property that $$</span></span>
  <span data-ttu-id="37214-291">U \ket { \psi } \ket { 0 } = \ket { \psi }\ket{\psi}</span><span class="sxs-lookup"><span data-stu-id="37214-291">U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}</span></span>
$$
<span data-ttu-id="37214-292">适用于任何状态 $ \ket { \psi } $ 。</span><span class="sxs-lookup"><span data-stu-id="37214-292">for any state $\ket{\psi}$.</span></span>
<span data-ttu-id="37214-293">矩阵乘法的 "线性" 属性意味着，对于任何第二个量程状态 $ \ket { \phi } $ ，</span><span class="sxs-lookup"><span data-stu-id="37214-293">The linearity property of matrix multiplication then implies that for any second quantum state $\ket{\phi}$,</span></span>

$$
\begin{align}
    <span data-ttu-id="37214-294">U \left [ \frac { 1 } { \sqrt { 2 } } \left (\ket { \phi } + \ket { \psi } \right) \right ] \ket { 0}</span><span class="sxs-lookup"><span data-stu-id="37214-294">U \left[ \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right] \ket{0}</span></span>
    <span data-ttu-id="37214-295">&= \frac{1 } { \sqrt { 2 } } U \ket { \phi } \ket { 0}</span><span class="sxs-lookup"><span data-stu-id="37214-295">& = \frac{1}{\sqrt{2}} U\ket{\phi}\ket{0}</span></span>
      <span data-ttu-id="37214-296">+ \frac{1 } { \sqrt { 2 } } U \ket { \psi } \ket { 0 }\\\\</span><span class="sxs-lookup"><span data-stu-id="37214-296">+ \frac{1}{\sqrt{2}} U\ket{\psi}\ket{0} \\\\</span></span>
    <span data-ttu-id="37214-297">&= \frac{1 } { \sqrt { 2 } } \left ( \ket { \phi } \ket { \phi }  +  \ket { \psi }\ket{\psi}</span><span class="sxs-lookup"><span data-stu-id="37214-297">& = \frac{1}{\sqrt{2}} \left( \ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi}</span></span>
        <span data-ttu-id="37214-298">\right) \\\\</span><span class="sxs-lookup"><span data-stu-id="37214-298">\right) \\\\</span></span>
    <span data-ttu-id="37214-299">&\ne \left ( \frac { 1 } { \sqrt { 2 } } \left (\ket { \phi } + \ket { \psi } \right) \right) \otimes \left ( \frac { 1 } { \sqrt { 2 } } \left (\ket { \phi } + \ket { \psi } \right \right) ) 。</span><span class="sxs-lookup"><span data-stu-id="37214-299">& \ne \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right) \otimes \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right).</span></span>
\end{align}
$$

<span data-ttu-id="37214-300">这提供了不克隆定理背后的基本直觉：复制未知量程状态的任何设备必须至少在其复制的某些状态下引发错误。</span><span class="sxs-lookup"><span data-stu-id="37214-300">This provides the fundamental intuition behind the No-Cloning Theorem: any device that copies an unknown quantum state must induce errors on at least some of the states it copies.</span></span>
<span data-ttu-id="37214-301">虽然 cloner 在输入状态下线性处理的关键假设可以通过添加和度量辅助 qubits 来突破，此类交互还会通过测量统计信息泄漏有关系统的信息，并在这种情况下防止精确克隆。</span><span class="sxs-lookup"><span data-stu-id="37214-301">While the key assumption that the cloner acts linearly on the input state can be violated through the addition and measurement of auxiliary qubits, such interactions also leak information about the system through the measurement statistics and prevent exact cloning in such cases as well.</span></span>
<span data-ttu-id="37214-302">有关无克隆定理的更完整的证明，请参阅 [以获取详细信息](xref:microsoft.quantum.more-information)。</span><span class="sxs-lookup"><span data-stu-id="37214-302">For a more complete proof of the No-Cloning Theorem see [For more information](xref:microsoft.quantum.more-information).</span></span>

<span data-ttu-id="37214-303">无克隆定理对于定性了解量程计算非常重要，因为如果可以将量程状态重新克隆，则会被授予近乎神奇的功能，可以从量程状态中学习。</span><span class="sxs-lookup"><span data-stu-id="37214-303">The No-Cloning Theorem is important for qualitative understanding of quantum computing because if you could clone quantum states inexpensively then you would be granted a near-magical ability to learn from quantum states.</span></span>
<span data-ttu-id="37214-304">事实上，您可能违反了海森堡的 vaunted 不确定性原则。</span><span class="sxs-lookup"><span data-stu-id="37214-304">Indeed, you could violate Heisenberg's vaunted uncertainty principle.</span></span>
<span data-ttu-id="37214-305">或者，您可以使用最佳的 cloner 从复杂的量程分布中获取一个示例，并从一个示例中了解有关该分布的所有内容。</span><span class="sxs-lookup"><span data-stu-id="37214-305">Alternatively, you could use an optimal cloner to take a single sample from a complex quantum distribution and learn everything you could possibly learn about that distribution from just one sample.</span></span>
<span data-ttu-id="37214-306">这就像你翻转硬币和观察打印头，然后在告诉朋友，使其响应 "Ah，这一硬币的分布必须与 $ p = 0.512643 \ ldots $ ！"</span><span class="sxs-lookup"><span data-stu-id="37214-306">This would be like you flipping a coin and observing heads and then upon telling a friend about the result having them respond "Ah the distribution of that coin must be Bernoulli with $p=0.512643\ldots$!"</span></span>  <span data-ttu-id="37214-307">这种语句是不 sensical 的，因为有一小部分信息 (磁头结果) 只是不能提供编码分发所需的多个信息，而不是以前的信息。</span><span class="sxs-lookup"><span data-stu-id="37214-307">Such a statement would be non-sensical because one bit of information (the heads outcome) simply cannot provide the many bits of information needed to encode the distribution without substantial prior information.</span></span>
<span data-ttu-id="37214-308">同样，如果没有以前的信息，我们就不能完全克隆量程状态，因为我们不知道 p 就无法准备系综的 $ $ 。</span><span class="sxs-lookup"><span data-stu-id="37214-308">Similarly, without prior information we cannot perfectly clone a quantum state just as we cannot prepare an ensemble of such coins without knowing $p$.</span></span>

<span data-ttu-id="37214-309">信息在量程计算中不可用。</span><span class="sxs-lookup"><span data-stu-id="37214-309">Information is not free in quantum computing.</span></span>
<span data-ttu-id="37214-310">每个 qubit 都提供一项信息，而不克隆定理显示没有后门，可以利用它来解决有关系统所获得的信息与对其调用的干扰之间的基本平衡点。</span><span class="sxs-lookup"><span data-stu-id="37214-310">Each qubit measured gives a single bit of information, and the No-Cloning Theorem shows that there is no backdoor that can be exploited to get around the fundamental tradeoff between information gained about the system and the disturbance invoked upon it.</span></span>
