---
<span data-ttu-id="c5ded-101">标题：量程线路说明：了解如何以视觉方式表示具有量程线路的简单和复杂的量程操作。</span><span class="sxs-lookup"><span data-stu-id="c5ded-101">title: Quantum circuits description: Learn how to visually represent simple and complex quantum operations with quantum circuit diagrams.</span></span>
<span data-ttu-id="c5ded-102">author： QuantumWriter uid：12/11/2017 毫秒。作者： nawiebe@microsoft.com ms. 日期： ms. 主题：项目不相关：</span><span class="sxs-lookup"><span data-stu-id="c5ded-102">author: QuantumWriter uid: microsoft.quantum.concepts.circuits ms.author: nawiebe@microsoft.com ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="c5ded-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="c5ded-103">"Q#"</span></span>
- <span data-ttu-id="c5ded-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="c5ded-104">"$$v"</span></span>
- <span data-ttu-id="c5ded-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="c5ded-105">"$$"</span></span>
- <span data-ttu-id="c5ded-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="c5ded-106">"$$"</span></span>
- <span data-ttu-id="c5ded-107">"$"</span><span class="sxs-lookup"><span data-stu-id="c5ded-107">"$"</span></span>
- <span data-ttu-id="c5ded-108">"$"</span><span class="sxs-lookup"><span data-stu-id="c5ded-108">"$"</span></span>
- <span data-ttu-id="c5ded-109">"$"</span><span class="sxs-lookup"><span data-stu-id="c5ded-109">"$"</span></span>
- <span data-ttu-id="c5ded-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="c5ded-110">"$$"</span></span>
- <span data-ttu-id="c5ded-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="c5ded-111">"\cdots"</span></span>
- <span data-ttu-id="c5ded-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="c5ded-112">"bmatrix"</span></span>
- <span data-ttu-id="c5ded-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="c5ded-113">"\ddots"</span></span>
- <span data-ttu-id="c5ded-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="c5ded-114">"\equiv"</span></span>
- <span data-ttu-id="c5ded-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="c5ded-115">"\sum"</span></span>
- <span data-ttu-id="c5ded-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="c5ded-116">"\begin"</span></span>
- <span data-ttu-id="c5ded-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="c5ded-117">"\end"</span></span>
- <span data-ttu-id="c5ded-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="c5ded-118">"\sqrt"</span></span>
- <span data-ttu-id="c5ded-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="c5ded-119">"\otimes"</span></span>
- <span data-ttu-id="c5ded-120">"{"</span><span class="sxs-lookup"><span data-stu-id="c5ded-120">"{"</span></span>
- <span data-ttu-id="c5ded-121">"}"</span><span class="sxs-lookup"><span data-stu-id="c5ded-121">"}"</span></span>
- <span data-ttu-id="c5ded-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="c5ded-122">"\text"</span></span>
- <span data-ttu-id="c5ded-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="c5ded-123">"\phi"</span></span>
- <span data-ttu-id="c5ded-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="c5ded-124">"\kappa"</span></span>
- <span data-ttu-id="c5ded-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="c5ded-125">"\psi"</span></span>
- <span data-ttu-id="c5ded-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="c5ded-126">"\alpha"</span></span>
- <span data-ttu-id="c5ded-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="c5ded-127">"\beta"</span></span>
- <span data-ttu-id="c5ded-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="c5ded-128">"\gamma"</span></span>
- <span data-ttu-id="c5ded-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="c5ded-129">"\delta"</span></span>
- <span data-ttu-id="c5ded-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="c5ded-130">"\omega"</span></span>
- <span data-ttu-id="c5ded-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="c5ded-131">"\bra"</span></span>
- <span data-ttu-id="c5ded-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="c5ded-132">"\ket"</span></span>
- <span data-ttu-id="c5ded-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="c5ded-133">"\boldone"</span></span>
- <span data-ttu-id="c5ded-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="c5ded-134">"\\\\"</span></span>
- <span data-ttu-id="c5ded-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="c5ded-135">"\\"</span></span>
- <span data-ttu-id="c5ded-136">"="</span><span class="sxs-lookup"><span data-stu-id="c5ded-136">"="</span></span>
- <span data-ttu-id="c5ded-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="c5ded-137">"\frac"</span></span>
- <span data-ttu-id="c5ded-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="c5ded-138">"\text"</span></span>
- <span data-ttu-id="c5ded-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="c5ded-139">"\mapsto"</span></span>
- <span data-ttu-id="c5ded-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="c5ded-140">"\dagger"</span></span>
- <span data-ttu-id="c5ded-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="c5ded-141">"\to"</span></span>
- <span data-ttu-id="c5ded-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="c5ded-142">"\begin{cases}"</span></span>
- <span data-ttu-id="c5ded-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="c5ded-143">"\end{cases}"</span></span>
- <span data-ttu-id="c5ded-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="c5ded-144">"\operatorname"</span></span>
- <span data-ttu-id="c5ded-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="c5ded-145">"\braket"</span></span>
- <span data-ttu-id="c5ded-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="c5ded-146">"\id"</span></span>
- <span data-ttu-id="c5ded-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="c5ded-147">"\expect"</span></span>
- <span data-ttu-id="c5ded-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="c5ded-148">"\defeq"</span></span>
- <span data-ttu-id="c5ded-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="c5ded-149">"\variance"</span></span>
- <span data-ttu-id="c5ded-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="c5ded-150">"\dd"</span></span>
- <span data-ttu-id="c5ded-151">"&"</span><span class="sxs-lookup"><span data-stu-id="c5ded-151">"&"</span></span>
- <span data-ttu-id="c5ded-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="c5ded-152">"\begin{align}"</span></span>
- <span data-ttu-id="c5ded-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="c5ded-153">"\end{align}"</span></span>
- <span data-ttu-id="c5ded-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="c5ded-154">"\Lambda"</span></span>
- <span data-ttu-id="c5ded-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="c5ded-155">"\lambda"</span></span>
- <span data-ttu-id="c5ded-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="c5ded-156">"\Omega"</span></span>
- <span data-ttu-id="c5ded-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="c5ded-157">"\mathrm"</span></span>
- <span data-ttu-id="c5ded-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="c5ded-158">"\left"</span></span>
- <span data-ttu-id="c5ded-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="c5ded-159">"\right"</span></span>
- <span data-ttu-id="c5ded-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="c5ded-160">"\qquad"</span></span>
- <span data-ttu-id="c5ded-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="c5ded-161">"\times"</span></span>
- <span data-ttu-id="c5ded-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="c5ded-162">"\big"</span></span>
- <span data-ttu-id="c5ded-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="c5ded-163">"\langle"</span></span>
- <span data-ttu-id="c5ded-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="c5ded-164">"\rangle"</span></span>
- <span data-ttu-id="c5ded-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="c5ded-165">"\bigg"</span></span>
- <span data-ttu-id="c5ded-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="c5ded-166">"\Big"</span></span>
- <span data-ttu-id="c5ded-167">"|"</span><span class="sxs-lookup"><span data-stu-id="c5ded-167">"|"</span></span>
- <span data-ttu-id="c5ded-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="c5ded-168">"\mathbb"</span></span>
- <span data-ttu-id="c5ded-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="c5ded-169">"\vec"</span></span>
- <span data-ttu-id="c5ded-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="c5ded-170">"\in"</span></span>
- <span data-ttu-id="c5ded-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="c5ded-171">"\texttt"</span></span>
- <span data-ttu-id="c5ded-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="c5ded-172">"\ne"</span></span>
- <span data-ttu-id="c5ded-173">"<"</span><span class="sxs-lookup"><span data-stu-id="c5ded-173">"<"</span></span>
- <span data-ttu-id="c5ded-174">">"</span><span class="sxs-lookup"><span data-stu-id="c5ded-174">">"</span></span>
- <span data-ttu-id="c5ded-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="c5ded-175">"\leq"</span></span>
- <span data-ttu-id="c5ded-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="c5ded-176">"\geq"</span></span>
- <span data-ttu-id="c5ded-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="c5ded-177">"~~"</span></span>
- <span data-ttu-id="c5ded-178">"~"</span><span class="sxs-lookup"><span data-stu-id="c5ded-178">"~"</span></span>
- <span data-ttu-id="c5ded-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="c5ded-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="c5ded-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="c5ded-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="c5ded-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="c5ded-181">"\_"</span></span>

---

# <a name="quantum-circuits"></a><span data-ttu-id="c5ded-182">量程线路</span><span class="sxs-lookup"><span data-stu-id="c5ded-182">Quantum Circuits</span></span>
<span data-ttu-id="c5ded-183">请考虑一下单一转换 $ \text { cnot-contains } _ { 01 } (H \otimes 1) $ 的时刻。</span><span class="sxs-lookup"><span data-stu-id="c5ded-183">Consider for a moment the unitary transformation $\text{ CNOT}_{01}(H\otimes 1)$.</span></span>
<span data-ttu-id="c5ded-184">此入口序列对量程计算至关重要，因为它创建最大化放大二 qubit 状态：</span><span class="sxs-lookup"><span data-stu-id="c5ded-184">This gate sequence is of fundamental significance to quantum computing because it creates a maximally entangled two-qubit state:</span></span>

<span data-ttu-id="c5ded-185">$$\mathrm{Cnot-contains } _ { 01 } (H \otimes 1) \ket { 00 } = \frac { 1 } { \sqrt { 2 } } \left (\ket { 00 }  +  \ket { 11 } \right) ，$$</span><span class="sxs-lookup"><span data-stu-id="c5ded-185">$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right),$$</span></span>

<span data-ttu-id="c5ded-186">具有这种或更大复杂性的操作在量程算法和量程错误更正中无处不在，因此它应该会很好地降低，其中有一种简单的方法可以将其可视化称为 "*量程*"。</span><span class="sxs-lookup"><span data-stu-id="c5ded-186">Operations with this or greater complexity are ubiquitous in quantum algorithms and quantum error correction, so it should come as a great relief that there is a simple method for their visualization called a *quantum circuit diagram*.</span></span>
<span data-ttu-id="c5ded-187">准备此最大化放大量程状态的线路关系图为：</span><span class="sxs-lookup"><span data-stu-id="c5ded-187">The circuit diagram for preparing this maximally entangled quantum state is:</span></span>

<span data-ttu-id="c5ded-188"><!--- ![](.\media\1.svg) ---></span><span class="sxs-lookup"><span data-stu-id="c5ded-188"><!--- ![](.\media\1.svg) ---></span></span>
<span data-ttu-id="c5ded-189"><!--找不到一种轻松地将此 .。。可能需要扩展：--></span><span class="sxs-lookup"><span data-stu-id="c5ded-189"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="c5ded-190">![最大化放大双 qubit 状态的布线图](~/media/1.svg)</span><span class="sxs-lookup"><span data-stu-id="c5ded-190">![Circuit diagram for a maximally entangled two-qubit state](~/media/1.svg)</span></span>

## <a name="quantum-circuit-diagram-conventions"></a><span data-ttu-id="c5ded-191">量程线路约定</span><span class="sxs-lookup"><span data-stu-id="c5ded-191">Quantum circuit diagram conventions</span></span>
<span data-ttu-id="c5ded-192">当你了解表示量子线路的约定后，这种适用于量程操作的视觉语言比写下其等效矩阵更容易理解。</span><span class="sxs-lookup"><span data-stu-id="c5ded-192">This visual language for quantum operations can be more readily digestible than writing down its equivalent matrix once you understand the conventions for expressing a quantum circuit.</span></span>
<span data-ttu-id="c5ded-193">我们将在下面查看这些约定。</span><span class="sxs-lookup"><span data-stu-id="c5ded-193">We review these conventions below.</span></span>

<span data-ttu-id="c5ded-194">在电路图中，每个实线都描述了 qubit 或更常见的 qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="c5ded-194">In a circuit diagram, each solid line depicts a qubit or more generally a qubit register.</span></span>
<span data-ttu-id="c5ded-195">按照约定，顶行是 qubit register $ 0 $ ，余数按顺序标记。</span><span class="sxs-lookup"><span data-stu-id="c5ded-195">By convention, the top line is qubit register $0$ and the remainder are labeled sequentially.</span></span> <span data-ttu-id="c5ded-196">上面的示例线路描述为在两个 qubits (上操作，或等效两个寄存器，其中包含一个 qubit) 。</span><span class="sxs-lookup"><span data-stu-id="c5ded-196">The above example circuit is depicted as acting on two qubits (or equivalently two registers consisting of one qubit).</span></span>
<span data-ttu-id="c5ded-197">在一个或多个 qubit 寄存器上操作的入口表示为一个框。</span><span class="sxs-lookup"><span data-stu-id="c5ded-197">Gates acting on one or more qubit registers are denoted as a box.</span></span>
<span data-ttu-id="c5ded-198">例如，符号</span><span class="sxs-lookup"><span data-stu-id="c5ded-198">For example, the symbol</span></span>

<span data-ttu-id="c5ded-199"><!--- ![](.\media\2.svg) ---></span><span class="sxs-lookup"><span data-stu-id="c5ded-199"><!--- ![](.\media\2.svg) ---></span></span>
<span data-ttu-id="c5ded-200"><!--找不到一种轻松地将此 .。。可能需要扩展：--></span><span class="sxs-lookup"><span data-stu-id="c5ded-200"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="c5ded-201">![对 qubit 寄存器执行的 Hadamard 操作的符号](~/media/2.svg)</span><span class="sxs-lookup"><span data-stu-id="c5ded-201">![Symbol for a Hadamard operation acting on a single-qubit register](~/media/2.svg)</span></span>

<span data-ttu-id="c5ded-202">是对 qubit 寄存器进行的[Hadamard](xref:microsoft.quantum.intrinsic.h)操作。</span><span class="sxs-lookup"><span data-stu-id="c5ded-202">is a [Hadamard](xref:microsoft.quantum.intrinsic.h) operation acting on a single-qubit register.</span></span>

<span data-ttu-id="c5ded-203">量程入口按时间顺序排列，并将最左侧的入口排列为第一个应用到 qubits 的入口。</span><span class="sxs-lookup"><span data-stu-id="c5ded-203">Quantum gates are ordered in chronological order with the left-most gate as the gate first applied to the qubits.</span></span>
<span data-ttu-id="c5ded-204">换而言之，如果将电缆画为包含量程状态，则电缆会从左到右从图中的每个入口开始显示量程状态。</span><span class="sxs-lookup"><span data-stu-id="c5ded-204">In other words, if you picture the wires as holding the quantum state, the wires bring the quantum state through each of the gates in the diagram from left to right.</span></span>
<span data-ttu-id="c5ded-205">这就是说</span><span class="sxs-lookup"><span data-stu-id="c5ded-205">That is to say</span></span> 

<span data-ttu-id="c5ded-206"><!--- ![](.\media\3.svg) ---></span><span class="sxs-lookup"><span data-stu-id="c5ded-206"><!--- ![](.\media\3.svg) ---></span></span>
<span data-ttu-id="c5ded-207"><!--找不到一种轻松地将此 .。。可能需要扩展：--></span><span class="sxs-lookup"><span data-stu-id="c5ded-207"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="c5ded-208">![从左向右应用的量程入口示意图](~/media/3.svg)</span><span class="sxs-lookup"><span data-stu-id="c5ded-208">![Diagram of quantum gates being applied left-to-right](~/media/3.svg)</span></span>

<span data-ttu-id="c5ded-209">是单一矩阵 $ CBA $ 。</span><span class="sxs-lookup"><span data-stu-id="c5ded-209">is the unitary matrix $CBA$.</span></span>
<span data-ttu-id="c5ded-210">矩阵相乘服从相反的约定：首先应用最右侧的矩阵。</span><span class="sxs-lookup"><span data-stu-id="c5ded-210">Matrix multiplication obeys the opposite convention: the right-most matrix is applied first.</span></span> <span data-ttu-id="c5ded-211">但在量程电路关系图中，首先应用最左侧的入口。</span><span class="sxs-lookup"><span data-stu-id="c5ded-211">In quantum circuit diagrams, however, the left-most gate is applied first.</span></span>
<span data-ttu-id="c5ded-212">这种差异可能会导致混淆，因此请务必注意线性代数表示法和量子电路关系图之间的明显差异。</span><span class="sxs-lookup"><span data-stu-id="c5ded-212">This difference can at times lead to confusion, so it is important to note this significant difference between the linear algebraic notation and quantum circuit diagrams.</span></span>

## <a name="inputs-and-outputs-of-quantum-circuits"></a><span data-ttu-id="c5ded-213">量程线路的输入和输出</span><span class="sxs-lookup"><span data-stu-id="c5ded-213">Inputs and outputs of quantum circuits</span></span>
<span data-ttu-id="c5ded-214">前面给出的所有示例都具有相同数量的线路 (qubits) 输入，作为从量子入口传出的线路的数目。</span><span class="sxs-lookup"><span data-stu-id="c5ded-214">All previous examples given have had precisely the same number of wires (qubits) input to a quantum gate as the number of wires out from the quantum gate.</span></span>
<span data-ttu-id="c5ded-215">这种情况可能会在一开始就显得合理，一般情况下，量程线路可能比输入更多或更少的输出。</span><span class="sxs-lookup"><span data-stu-id="c5ded-215">It may at first seem reasonable that quantum circuits could have more, or fewer, outputs than inputs in general.</span></span>
<span data-ttu-id="c5ded-216">但是，这是不可能的，因为所有的量程操作（节省度量值）都是单一的，因此是可逆的。</span><span class="sxs-lookup"><span data-stu-id="c5ded-216">This is impossible, however, because all quantum operations, save measurement, are unitary and hence reversible.</span></span>
<span data-ttu-id="c5ded-217">如果它们没有与输入相同的输出数，则它们不是可逆的，因而不是一个冲突。</span><span class="sxs-lookup"><span data-stu-id="c5ded-217">If they did not have the same number of outputs as inputs they would not be reversible and hence not unitary, which is a contradiction.</span></span>
<span data-ttu-id="c5ded-218">出于此原因，在线路图中绘制的任何一个框必须与输入它的线路完全相同。</span><span class="sxs-lookup"><span data-stu-id="c5ded-218">For this reason any box drawn in a circuit diagram must have precisely the same number of wires entering it as exiting it.</span></span>

<span data-ttu-id="c5ded-219">多 qubit 线路关系图遵循类似的约定来 qubit。</span><span class="sxs-lookup"><span data-stu-id="c5ded-219">Multi-qubit circuit diagrams follow similar conventions to single-qubit ones.</span></span>
<span data-ttu-id="c5ded-220">作为一个示例，我们可以定义一个由两个 qubit 的单一操作 $ B $ $ (H S \otimes X) 并将 $ 该线路表示为与</span><span class="sxs-lookup"><span data-stu-id="c5ded-220">As a clarifying example, we can define a two-qubit unitary operation $B$ to be $(H S\otimes X)$ and express the circuit equivalently as</span></span>

<span data-ttu-id="c5ded-221"><!--- ![](.\media\4.svg) ---></span><span class="sxs-lookup"><span data-stu-id="c5ded-221"><!--- ![](.\media\4.svg) ---></span></span>
<span data-ttu-id="c5ded-222"><!--找不到一种轻松地将此 .。。可能需要扩展：--></span><span class="sxs-lookup"><span data-stu-id="c5ded-222"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="c5ded-223">![Qubit 单一操作的线路关系图](~/media/4.svg)</span><span class="sxs-lookup"><span data-stu-id="c5ded-223">![Circuit diagram of a two-qubit unitary operation](~/media/4.svg)</span></span>

<span data-ttu-id="c5ded-224">我们还可以查看 $ B $ ，使其在单个双 qubit 寄存器上进行操作，而不是在 2 1-qubit 寄存器上，具体取决于使用该线路的上下文。</span><span class="sxs-lookup"><span data-stu-id="c5ded-224">We can also view $B$ as having an action on a single two-qubit register rather than two one-qubit registers depending on the context in which the circuit is used.</span></span> <span data-ttu-id="c5ded-225">此类抽象线路的最有用的属性可能是，它们允许在较高级别对复杂的量程算法进行描述，而不必将它们编译为基本入口。</span><span class="sxs-lookup"><span data-stu-id="c5ded-225">Perhaps the most useful property of such abstract circuit diagrams is that they allow complicated quantum algorithms to be described at a high level without having to compile them down to fundamental gates.</span></span>
<span data-ttu-id="c5ded-226">这意味着，你可以获取有关大型量程算法的数据流的直觉，而无需了解算法中每个子例程的工作方式的所有详细信息。</span><span class="sxs-lookup"><span data-stu-id="c5ded-226">This means that you can get an intuition about the data flow for a large quantum algorithm without needing to understand all the details of how each of the subroutines within the algorithm work.</span></span>

## <a name="controlled-gates"></a><span data-ttu-id="c5ded-227">受控入口</span><span class="sxs-lookup"><span data-stu-id="c5ded-227">Controlled gates</span></span>
<span data-ttu-id="c5ded-228">内置于 qubit 量程线路关系图的另一种构造是控件。</span><span class="sxs-lookup"><span data-stu-id="c5ded-228">The other construct that is built into multi-qubit quantum circuit diagrams is control.</span></span>
<span data-ttu-id="c5ded-229">量程单向控制入口的操作（表示 $ \Lambda (g) $ ，其中，单个 qubit 的值控制 g 的应用）， $ $ 可通过查看下面的产品状态输入示例来了解， $ \Lambda (G)  (0 1 \alpha \ket { }  +  \beta \ket { }) \ket { \psi } = \alpha \ket { 0 } \ket { \psi }  +  \beta \ket { 1 } g \ket { \psi } $ 。也就是说， $ $ $ \psi $ 当且仅当控件 qubit 采用值 $ 1 $ 时，受控的入口才会将 G 应用到包含的。</span><span class="sxs-lookup"><span data-stu-id="c5ded-229">The action of a quantum singly controlled gate, denoted $\Lambda(G)$, where a single qubit's value controls the application of $G$, can be understood by looking at the following example of a product state input $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket{\psi}$. That is to say, the controlled gate applies $G$ to the register containing $\psi$ if and only if the control qubit takes the value $1$.</span></span>
<span data-ttu-id="c5ded-230">通常，我们会将这些受控操作介绍为</span><span class="sxs-lookup"><span data-stu-id="c5ded-230">In general, we describe such controlled operations in circuit diagrams as</span></span>

<span data-ttu-id="c5ded-231"><!--- ![](.\media\5.svg) ---></span><span class="sxs-lookup"><span data-stu-id="c5ded-231"><!--- ![](.\media\5.svg) ---></span></span>
<span data-ttu-id="c5ded-232"><!--找不到一种轻松地将此 .。。可能需要扩展：--></span><span class="sxs-lookup"><span data-stu-id="c5ded-232"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="c5ded-233">![单个受控入口的回路图](~/media/5.svg)</span><span class="sxs-lookup"><span data-stu-id="c5ded-233">![Circuit diagram of a singly controlled gate](~/media/5.svg)</span></span>

<span data-ttu-id="c5ded-234">此时，黑色圆圈表示控制门的量程位，垂直线表示在控件 qubit 采用值1时应用的单一 $ $ 。</span><span class="sxs-lookup"><span data-stu-id="c5ded-234">Here the black circle denotes the quantum bit on which the gate is controlled and a vertical wire denotes the unitary that is applied when the control qubit takes the value $1$.</span></span>
<span data-ttu-id="c5ded-235">对于 $ g = X 和 g Z 的特殊情况， $ $ = $ 我们引入了以下表示法，用于描述控制的入口版本 (请注意，受控-X 入口) ： [ $ $ ](xref:microsoft.quantum.intrinsic.cnot)</span><span class="sxs-lookup"><span data-stu-id="c5ded-235">For the special cases where $G=X$ and $G=Z$ we introduce the following notation to describe the controlled version of the gates (note that the controlled-X gate is the [$CNOT$ gate](xref:microsoft.quantum.intrinsic.cnot)):</span></span>

<span data-ttu-id="c5ded-236"><!--- ![](.\media\6.svg) ---></span><span class="sxs-lookup"><span data-stu-id="c5ded-236"><!--- ![](.\media\6.svg) ---></span></span>
<span data-ttu-id="c5ded-237"><!--找不到一种轻松地将此 .。。可能需要扩展：--></span><span class="sxs-lookup"><span data-stu-id="c5ded-237"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="c5ded-238">![受控入口的特殊情况的电路图](~/media/6.svg)</span><span class="sxs-lookup"><span data-stu-id="c5ded-238">![Circuit diagram for special cases of controlled gates](~/media/6.svg)</span></span>

<span data-ttu-id="c5ded-239">Q#提供自动生成控制版本的操作的方法，此操作使程序员不必为这些操作编写代码。</span><span class="sxs-lookup"><span data-stu-id="c5ded-239">Q# provides methods to automatically generate the controlled version of an operation, which saves the programmer from having to hand code these operations.</span></span> <span data-ttu-id="c5ded-240">下面显示了一个示例：</span><span class="sxs-lookup"><span data-stu-id="c5ded-240">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a><span data-ttu-id="c5ded-241">度量运算符</span><span class="sxs-lookup"><span data-stu-id="c5ded-241">Measurement operator</span></span>
<span data-ttu-id="c5ded-242">在 "电路图" 中显示的剩余操作是度量值。</span><span class="sxs-lookup"><span data-stu-id="c5ded-242">The remaining operation to visualize in circuit diagrams is measurement.</span></span>
<span data-ttu-id="c5ded-243">度量采用 qubit 注册，对其进行度量，并将结果输出为传统信息。</span><span class="sxs-lookup"><span data-stu-id="c5ded-243">Measurement takes a qubit register, measures it, and outputs the result as classical information.</span></span>
<span data-ttu-id="c5ded-244">度量运算由计量符号表示，并且始终将 qubit 注册 (由实线表示) 并输出传统信息 (由双线) 表示。</span><span class="sxs-lookup"><span data-stu-id="c5ded-244">A measurement operation is denoted by a meter symbol and always takes as input a qubit register (denoted by a solid line) and outputs classical information (denoted by a double line).</span></span>
<span data-ttu-id="c5ded-245">具体而言，此类 subcircuit 如下所示：</span><span class="sxs-lookup"><span data-stu-id="c5ded-245">Specifically, such a subcircuit looks like:</span></span>

<span data-ttu-id="c5ded-246"><!--- ![](.\media\7.svg) ----></span><span class="sxs-lookup"><span data-stu-id="c5ded-246"><!--- ![](.\media\7.svg) ----></span></span>
<span data-ttu-id="c5ded-247"><!--找不到一种轻松地将此 .。。可能需要扩展：--></span><span class="sxs-lookup"><span data-stu-id="c5ded-247"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="c5ded-248">![表示度量操作的符号](~/media/7.svg)</span><span class="sxs-lookup"><span data-stu-id="c5ded-248">![Symbol representing a measurement operation](~/media/7.svg)</span></span>

<span data-ttu-id="c5ded-249">Q#实现一个[度量运算符](xref:microsoft.quantum.intrinsic.measure)用于实现此目的。</span><span class="sxs-lookup"><span data-stu-id="c5ded-249">Q# implements a [Measure operator](xref:microsoft.quantum.intrinsic.measure) for this purpose.</span></span>
<span data-ttu-id="c5ded-250">有关详细信息，请参阅[有关度量值的部分](xref:microsoft.quantum.libraries.standard.prelude#measurements)。</span><span class="sxs-lookup"><span data-stu-id="c5ded-250">See the [section on measurements](xref:microsoft.quantum.libraries.standard.prelude#measurements) for more information.</span></span>

<span data-ttu-id="c5ded-251">同样，subcircuit</span><span class="sxs-lookup"><span data-stu-id="c5ded-251">Similarly, the subcircuit</span></span>

<span data-ttu-id="c5ded-252"><!--- ![](.\media\8.svg) ---></span><span class="sxs-lookup"><span data-stu-id="c5ded-252"><!--- ![](.\media\8.svg) ---></span></span>
<span data-ttu-id="c5ded-253"><!--找不到一种轻松地将此 .。。可能需要扩展：--></span><span class="sxs-lookup"><span data-stu-id="c5ded-253"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="c5ded-254">![表示受控操作的线路关系图](~/media/8.svg)</span><span class="sxs-lookup"><span data-stu-id="c5ded-254">![Circuit diagram representing a controlled operation](~/media/8.svg)</span></span>

<span data-ttu-id="c5ded-255">提供一个经典控制的入口，其中 $ G $ 适用于经典控件位上的值为 $ 1 $ 。</span><span class="sxs-lookup"><span data-stu-id="c5ded-255">gives a classically controlled gate, where $G$ is applied conditioned on the classical control bit being value $1$.</span></span>

## <a name="teleportation-circuit-diagram"></a><span data-ttu-id="c5ded-256">Teleportation 线路图</span><span class="sxs-lookup"><span data-stu-id="c5ded-256">Teleportation circuit diagram</span></span>
<span data-ttu-id="c5ded-257">量程 teleportation 可能是用于阐释这些组件的最佳量程算法。</span><span class="sxs-lookup"><span data-stu-id="c5ded-257">Quantum teleportation is perhaps the best quantum algorithm for illustrating these components.</span></span>
<span data-ttu-id="c5ded-258">你可以使用相应的[量程 Kata](xref:microsoft.quantum.overview.katas)量子 teleportation 来了解如何在量子计算机中移动数据 (甚至是在量程网络) 使用牵连和度量的远程量程计算机之间移动数据。</span><span class="sxs-lookup"><span data-stu-id="c5ded-258">You can learn hands-on with the corresponding [Quantum Kata](xref:microsoft.quantum.overview.katas) Quantum teleportation is a method for moving data within a quantum computer (or even between distant quantum computers in a quantum network) through the use of entanglement and measurement.</span></span>
<span data-ttu-id="c5ded-259">有趣的是，实际上可以将给定 qubit 中的值表示为从一个 qubit 移动到另一个，而无需了解 qubit 的值！</span><span class="sxs-lookup"><span data-stu-id="c5ded-259">Interestingly, it is actually capable of moving a quantum state, say the value in a given qubit, from one qubit to another, without even knowing what the qubit's value is!</span></span>
<span data-ttu-id="c5ded-260">这是协议根据量程机制的法律工作所必需的。</span><span class="sxs-lookup"><span data-stu-id="c5ded-260">This is necessary for the protocol to work according to the laws of quantum mechanics.</span></span>
<span data-ttu-id="c5ded-261">下面给出了量子 teleportation 线路;我们还提供了一条带批注的线路，用于说明如何读取量程线路。</span><span class="sxs-lookup"><span data-stu-id="c5ded-261">The quantum teleportation circuit is given below; we also provide an annotated version of the circuit to illustrate how to read the quantum circuit.</span></span>

<span data-ttu-id="c5ded-262"><!--- ![](.\media\tp2.svg) { width = 50%} ---></span><span class="sxs-lookup"><span data-stu-id="c5ded-262"><!--- ![](.\media\tp2.svg){ width=50% } ---></span></span>
<span data-ttu-id="c5ded-263">![量程 teleportation 线路](~/media/tp2.svg)</span><span class="sxs-lookup"><span data-stu-id="c5ded-263">![Quantum teleportation circuit](~/media/tp2.svg)</span></span>
