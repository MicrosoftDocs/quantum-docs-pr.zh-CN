---
<span data-ttu-id="b0dfe-101">title：量程 oracles 说明：了解如何使用和定义量程 oracles、用于作为其他算法的输入的黑色框操作。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-101">title: Quantum oracles description: Learn how to work with and define quantum oracles, black box operations that are used as input to another algorithm.</span></span>
<span data-ttu-id="b0dfe-102">author： cgranade uid： oracles： chgranad： ms. 日期： 07/11/2018 ms. 主题：概念非 loc：</span><span class="sxs-lookup"><span data-stu-id="b0dfe-102">author: cgranade uid: microsoft.quantum.concepts.oracles ms.author: chgranad ms.date: 07/11/2018 ms.topic: conceptual no-loc:</span></span>
- <span data-ttu-id="b0dfe-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-103">"Q#"</span></span>
- <span data-ttu-id="b0dfe-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-104">"$$v"</span></span>
- <span data-ttu-id="b0dfe-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-105">"$$"</span></span>
- <span data-ttu-id="b0dfe-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-106">"$$"</span></span>
- <span data-ttu-id="b0dfe-107">"$"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-107">"$"</span></span>
- <span data-ttu-id="b0dfe-108">"$"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-108">"$"</span></span>
- <span data-ttu-id="b0dfe-109">"$"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-109">"$"</span></span>
- <span data-ttu-id="b0dfe-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-110">"$$"</span></span>
- <span data-ttu-id="b0dfe-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-111">"\cdots"</span></span>
- <span data-ttu-id="b0dfe-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-112">"bmatrix"</span></span>
- <span data-ttu-id="b0dfe-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-113">"\ddots"</span></span>
- <span data-ttu-id="b0dfe-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-114">"\equiv"</span></span>
- <span data-ttu-id="b0dfe-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-115">"\sum"</span></span>
- <span data-ttu-id="b0dfe-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-116">"\begin"</span></span>
- <span data-ttu-id="b0dfe-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-117">"\end"</span></span>
- <span data-ttu-id="b0dfe-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-118">"\sqrt"</span></span>
- <span data-ttu-id="b0dfe-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-119">"\otimes"</span></span>
- <span data-ttu-id="b0dfe-120">"{"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-120">"{"</span></span>
- <span data-ttu-id="b0dfe-121">"}"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-121">"}"</span></span>
- <span data-ttu-id="b0dfe-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-122">"\text"</span></span>
- <span data-ttu-id="b0dfe-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-123">"\phi"</span></span>
- <span data-ttu-id="b0dfe-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-124">"\kappa"</span></span>
- <span data-ttu-id="b0dfe-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-125">"\psi"</span></span>
- <span data-ttu-id="b0dfe-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-126">"\alpha"</span></span>
- <span data-ttu-id="b0dfe-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-127">"\beta"</span></span>
- <span data-ttu-id="b0dfe-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-128">"\gamma"</span></span>
- <span data-ttu-id="b0dfe-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-129">"\delta"</span></span>
- <span data-ttu-id="b0dfe-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-130">"\omega"</span></span>
- <span data-ttu-id="b0dfe-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-131">"\bra"</span></span>
- <span data-ttu-id="b0dfe-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-132">"\ket"</span></span>
- <span data-ttu-id="b0dfe-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-133">"\boldone"</span></span>
- <span data-ttu-id="b0dfe-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-134">"\\\\"</span></span>
- <span data-ttu-id="b0dfe-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-135">"\\"</span></span>
- <span data-ttu-id="b0dfe-136">"="</span><span class="sxs-lookup"><span data-stu-id="b0dfe-136">"="</span></span>
- <span data-ttu-id="b0dfe-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-137">"\frac"</span></span>
- <span data-ttu-id="b0dfe-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-138">"\text"</span></span>
- <span data-ttu-id="b0dfe-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-139">"\mapsto"</span></span>
- <span data-ttu-id="b0dfe-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-140">"\dagger"</span></span>
- <span data-ttu-id="b0dfe-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-141">"\to"</span></span>
- <span data-ttu-id="b0dfe-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-142">"\begin{cases}"</span></span>
- <span data-ttu-id="b0dfe-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-143">"\end{cases}"</span></span>
- <span data-ttu-id="b0dfe-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-144">"\operatorname"</span></span>
- <span data-ttu-id="b0dfe-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-145">"\braket"</span></span>
- <span data-ttu-id="b0dfe-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-146">"\id"</span></span>
- <span data-ttu-id="b0dfe-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-147">"\expect"</span></span>
- <span data-ttu-id="b0dfe-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-148">"\defeq"</span></span>
- <span data-ttu-id="b0dfe-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-149">"\variance"</span></span>
- <span data-ttu-id="b0dfe-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-150">"\dd"</span></span>
- <span data-ttu-id="b0dfe-151">"&"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-151">"&"</span></span>
- <span data-ttu-id="b0dfe-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-152">"\begin{align}"</span></span>
- <span data-ttu-id="b0dfe-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-153">"\end{align}"</span></span>
- <span data-ttu-id="b0dfe-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-154">"\Lambda"</span></span>
- <span data-ttu-id="b0dfe-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-155">"\lambda"</span></span>
- <span data-ttu-id="b0dfe-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-156">"\Omega"</span></span>
- <span data-ttu-id="b0dfe-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-157">"\mathrm"</span></span>
- <span data-ttu-id="b0dfe-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-158">"\left"</span></span>
- <span data-ttu-id="b0dfe-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-159">"\right"</span></span>
- <span data-ttu-id="b0dfe-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-160">"\qquad"</span></span>
- <span data-ttu-id="b0dfe-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-161">"\times"</span></span>
- <span data-ttu-id="b0dfe-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-162">"\big"</span></span>
- <span data-ttu-id="b0dfe-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-163">"\langle"</span></span>
- <span data-ttu-id="b0dfe-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-164">"\rangle"</span></span>
- <span data-ttu-id="b0dfe-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-165">"\bigg"</span></span>
- <span data-ttu-id="b0dfe-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-166">"\Big"</span></span>
- <span data-ttu-id="b0dfe-167">"|"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-167">"|"</span></span>
- <span data-ttu-id="b0dfe-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-168">"\mathbb"</span></span>
- <span data-ttu-id="b0dfe-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-169">"\vec"</span></span>
- <span data-ttu-id="b0dfe-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-170">"\in"</span></span>
- <span data-ttu-id="b0dfe-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-171">"\texttt"</span></span>
- <span data-ttu-id="b0dfe-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-172">"\ne"</span></span>
- <span data-ttu-id="b0dfe-173">"<"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-173">"<"</span></span>
- <span data-ttu-id="b0dfe-174">">"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-174">">"</span></span>
- <span data-ttu-id="b0dfe-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-175">"\leq"</span></span>
- <span data-ttu-id="b0dfe-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-176">"\geq"</span></span>
- <span data-ttu-id="b0dfe-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-177">"~~"</span></span>
- <span data-ttu-id="b0dfe-178">"~"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-178">"~"</span></span>
- <span data-ttu-id="b0dfe-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="b0dfe-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="b0dfe-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="b0dfe-181">"\_"</span></span>

---
# <a name="quantum-oracles"></a><span data-ttu-id="b0dfe-182">量程 Oracles</span><span class="sxs-lookup"><span data-stu-id="b0dfe-182">Quantum Oracles</span></span>

<span data-ttu-id="b0dfe-183">Oracle $ O $ 是一个 "黑色框" 操作，用于作为其他算法的输入。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-183">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="b0dfe-184">通常，此类操作使用传统函数 $ f： \\ { 0、1 \\ } ^ n \to \\ { 0、1 ^ m 进行定义， \\ } $ 该函数采用 $ n $ 位二进制输入并生成一个 $ m $ 位二进制输出。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-184">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="b0dfe-185">为此，请考虑使用特定的二进制输入 $ x = (x_ { 0 } ，x_ { 1 } ，\dots ..，x_ { n-1 }) $ 。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-185">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="b0dfe-186">我们可以将 qubit 状态标记为 $ \ket { \vec { x } } = \ket { x_ { 0 } } \otimes \ket { x_ { 1 } } \otimes \cdots \otimes \ket { x_ { n-1 } } $ 。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-186">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="b0dfe-187">我们可能首先尝试定义 $ o， $ 使 $ o \ket { x } = \ket { f (x) } $ ，但这有一些问题。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-187">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="b0dfe-188">首先， $ f 的 $ 输入和输出大小可能不同 ($ n \ne m $) ，因此，应用 $ O $ 将更改寄存器中的 qubits 数目。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-188">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="b0dfe-189">其次，即使 $ n = m $ ，函数也不能可逆：如果 $ f (x) = f (y) $ 对于某些 $ x \ne y $ ，则为 $ o \ket { x } = o \ket { y } $ 但 $ o ^ \dagger O \ket { x o x o x o x o x o x o x o x o x o } \ne \dagger \ket { y } $ 。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-189">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="b0dfe-190">这意味着我们无法构造 adjoint 操作 $ O ^ \dagger $ ，oracles 必须为其定义 adjoint。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-190">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="b0dfe-191">通过其对计算基础状态的影响来定义 oracle</span><span class="sxs-lookup"><span data-stu-id="b0dfe-191">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="b0dfe-192">我们可以通过引入另一个 $ m qubits 注册来解决这两个问题 $ 。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-192">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="b0dfe-193">然后，将为所有计算基础状态定义 oracle 的效果：对于所有 $ x \in \\ { 0、1 \\ } ^ n $ 和 $ y \in \\ { 0，1 \\ } ^ m $ ，</span><span class="sxs-lookup"><span data-stu-id="b0dfe-193">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

$$
\begin{align}
    <span data-ttu-id="b0dfe-194">O (\ket { x } \otimes \ket { y }) = \ket { x } \otimes \ket { y \oplus f (x) } 。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-194">O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

<span data-ttu-id="b0dfe-195">现在 $ = \dagger $ ，我们已解决了这两个以前的问题。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-195">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
<span data-ttu-id="b0dfe-196">>若要查看 $ o = o ^ { \dagger } $ ，请注意 $ o ^ 2， = \boldone $ 因为 $ \oplus b \oplus b = a $ for all $ a，b \in \: ：： no-loc ( {) ：：：0，1 \: ：： no loc (} ) ：：： $ 。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-196">> To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
<span data-ttu-id="b0dfe-197">>因此， $ O \ket { x } \ket { y \oplus f (x) } = \ket { x } \ket { y \oplus f (x) \oplus f (x) x } = \ket { } \ket { y } $ 。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-197">> As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="b0dfe-198">重要的是，以这种方式为每个计算基础状态 $ \ket { x y 定义 oracle } \ket { } $ 也定义了 O 如何处理 $ $ 任何其他状态。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-198">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="b0dfe-199">这 $ 是因为 O $ （与所有量程操作一样）在其作用于的状态下是线性的。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-199">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="b0dfe-200">例如，假设 Hadamard 操作由 $ h \ket { 0 } = \ket { + } $ 和 $ h \ket { 1 定义 } = \ket { - } $ 。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-200">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="b0dfe-201">如果我们想要了解 $ h 如何 $ $ \ket { + } $ 操作，可以使用 $ h 作为 $ 线性，</span><span class="sxs-lookup"><span data-stu-id="b0dfe-201">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

$$
\begin{align}
<span data-ttu-id="b0dfe-202">H \ket { + } & = \frac { 1 } { \sqrt { 2 } } H (\ket { 0 }  +  \ket { 1 }) = \frac { 1 } { \sqrt { 2 } } (h \ket { 0 } + h \ket { 1 }) \\\\</span><span class="sxs-lookup"><span data-stu-id="b0dfe-202">H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\</span></span>
           <span data-ttu-id="b0dfe-203">&= \frac{1 } { \sqrt { 2 } } (\ket { + }  +  \ket { - }) = \frac 12 (\ket { 0 }  +  \ket { 1 }  +  \ket { 0 }  -  \ket { 1 }) = \ket { 0 } 。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-203">& = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
\end{align}
$$

<span data-ttu-id="b0dfe-204">在定义 oracle O 的情况下 $ $ ，我们可以同样使用 $ \ket { \psi } $ $ n + m qubits 上的任何状态都 $ 可以编写为</span><span class="sxs-lookup"><span data-stu-id="b0dfe-204">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

$$
\begin{align}
<span data-ttu-id="b0dfe-205">\ket{\psi}& = \sum_ { x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha (x、y) \ket { x } \ket { y}</span><span class="sxs-lookup"><span data-stu-id="b0dfe-205">\ket{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y}</span></span>
\end{align}
$$

<span data-ttu-id="b0dfe-206">其中 $ \alpha ： \\ { 0，1 \\ } ^ n \times \\ { 0，1 \\ } ^ m \to \mathbb { C } $ 表示状态的系数 $ \ket { \psi } $ 。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-206">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="b0dfe-207">因此，</span><span class="sxs-lookup"><span data-stu-id="b0dfe-207">Thus,</span></span>

$$
\begin{align}
<span data-ttu-id="b0dfe-208">O \ket { \psi } & = o \sum _{ x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha (x、y) \ket { x } \ket { y } x \\\\ 0 & 、 = 1 ^ n、y 0、1 ^ m (x、y) O \sum_ { \in \\ { \\ } \in \\ { \\ } } \alpha \ket { x } \ket { y }\\\\</span><span class="sxs-lookup"><span data-stu-id="b0dfe-208">O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\</span></span>
             <span data-ttu-id="b0dfe-209">&= \sum _ { x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha (x、y) \ket { x } \ket { y \oplus f (x) } 。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-209">& = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

## <a name="phase-oracles"></a><span data-ttu-id="b0dfe-210">阶段 oracles</span><span class="sxs-lookup"><span data-stu-id="b0dfe-210">Phase oracles</span></span>
<span data-ttu-id="b0dfe-211">此外，我们还可以 $ $ $ $ 通过基于到 O 的输入应用 _阶段_ ，将 f 编码为 oracle $ O $ 。例如，我们可以定义 $ O $ ，使 $$</span><span class="sxs-lookup"><span data-stu-id="b0dfe-211">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$. For instance, we might define $O$ such that $$</span></span>
\begin{align}
    <span data-ttu-id="b0dfe-212">O \ket { x } = (-1) ^ { f (x) } \ket { x } 。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-212">O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
\end{align}
$$
<span data-ttu-id="b0dfe-213">如果 oracle 最初在计算基础状态 x 中对寄存器 $ \ket { } $ 进行操作，则此阶段为全局阶段，因此无法观察。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-213">If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="b0dfe-214">但如果应用于 superposition 或作为受控操作，此类 oracle 可能是非常强大的资源。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-214">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="b0dfe-215">例如，请考虑一个阶段 $ $ 为 qubit 函数 $ f O_f $ 。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-215">For example, consider a phase oracle $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="b0dfe-216">接着 $$</span><span class="sxs-lookup"><span data-stu-id="b0dfe-216">Then, $$</span></span>
\begin{align}
    <span data-ttu-id="b0dfe-217">O_f \ket{+}</span><span class="sxs-lookup"><span data-stu-id="b0dfe-217">O_f \ket{+}</span></span>
        <span data-ttu-id="b0dfe-218">&=O_f (\ket {0 }  +  \ket { 1 }) / \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="b0dfe-218">& = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="b0dfe-219">&= ( # A1-1) ^ { f (0) } \ket { 0 } + () ^ { f (1) } \ket { 1 }) / \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="b0dfe-219">& = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="b0dfe-220">&= (-1) ^ { f (0) } (\ket { 0 } + () ^ { f (1)  (} \ket { } \sqrt { } 1) \\\\</span><span class="sxs-lookup"><span data-stu-id="b0dfe-220">& = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="b0dfe-221">&= (-1) ^ { f (0) } Z ^ { f (0)  (1) } \ket { + } 。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-221">& = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
\end{align}
$$

> [!NOTE]
<span data-ttu-id="b0dfe-222">>请注意， $ z ^ { -1 } = z ^ { \dagger } = z $ 和 $ z ^ { f (0) -f (1) } = Z ^ { f (1) -f (0) } 。$</span><span class="sxs-lookup"><span data-stu-id="b0dfe-222">> Note that $Z^{-1}=Z^{\dagger}=Z$ and therefore $Z^{f(0)-f(1)}=Z^{f(1)-f(0)}.$</span></span>

<span data-ttu-id="b0dfe-223">更常见的情况是，oracles 的两个视图都可以扩大了，以表示返回实数而不只是一位的传统函数。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-223">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="b0dfe-224">选择实现 oracle 的最佳方式很大程度上取决于 oracle 在给定算法中的使用方式。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-224">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="b0dfe-225">例如， [Deutsch-Jozsa 算法](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) 依赖于第一种方式实现的 oracle，而 [Grover 的算法](https://en.wikipedia.org/wiki/Grover's_algorithm) 依赖于第二个方法实现的 oracle。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-225">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="b0dfe-226">有关更多详细信息，我们建议在 [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465)中进行讨论。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-226">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
