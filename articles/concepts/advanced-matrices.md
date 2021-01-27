---
<span data-ttu-id="886a7-101">标题：高级矩阵概念说明：了解本征向量、本征值和 matrix 指数，这是用于描述和模拟量程算法的基本工具。</span><span class="sxs-lookup"><span data-stu-id="886a7-101">title: Advanced matrix concepts description: Learn about eigenvectors, eigenvalues, and matrix exponentials, the fundamental tools used to describe and simulate quantum algorithms.</span></span>
<span data-ttu-id="886a7-102">author： QuantumWriter uid： benbra-advanced： v-ms。 date： 12/11/2017 ms. 主题：概念非 loc：</span><span class="sxs-lookup"><span data-stu-id="886a7-102">author: QuantumWriter uid: microsoft.quantum.concepts.matrix-advanced ms.author: v-benbra ms.date: 12/11/2017 ms.topic: conceptual no-loc:</span></span>
- <span data-ttu-id="886a7-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="886a7-103">"Q#"</span></span>
- <span data-ttu-id="886a7-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="886a7-104">"$$v"</span></span>
- <span data-ttu-id="886a7-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="886a7-105">"$$"</span></span>
- <span data-ttu-id="886a7-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="886a7-106">"$$"</span></span>
- <span data-ttu-id="886a7-107">"$"</span><span class="sxs-lookup"><span data-stu-id="886a7-107">"$"</span></span>
- <span data-ttu-id="886a7-108">"$"</span><span class="sxs-lookup"><span data-stu-id="886a7-108">"$"</span></span>
- <span data-ttu-id="886a7-109">"$"</span><span class="sxs-lookup"><span data-stu-id="886a7-109">"$"</span></span>
- <span data-ttu-id="886a7-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="886a7-110">"$$"</span></span>
- <span data-ttu-id="886a7-111">"$$$"</span><span class="sxs-lookup"><span data-stu-id="886a7-111">"$$$"</span></span>
- <span data-ttu-id="886a7-112">"$$$"</span><span class="sxs-lookup"><span data-stu-id="886a7-112">"$$$"</span></span>
- <span data-ttu-id="886a7-113">"$$$"</span><span class="sxs-lookup"><span data-stu-id="886a7-113">"$$$"</span></span>
- <span data-ttu-id="886a7-114">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="886a7-114">"\cdots"</span></span>
- <span data-ttu-id="886a7-115">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="886a7-115">"bmatrix"</span></span>
- <span data-ttu-id="886a7-116">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="886a7-116">"\ddots"</span></span>
- <span data-ttu-id="886a7-117">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="886a7-117">"\equiv"</span></span>
- <span data-ttu-id="886a7-118">"\sum"</span><span class="sxs-lookup"><span data-stu-id="886a7-118">"\sum"</span></span>
- <span data-ttu-id="886a7-119">"\begin"</span><span class="sxs-lookup"><span data-stu-id="886a7-119">"\begin"</span></span>
- <span data-ttu-id="886a7-120">"\end"</span><span class="sxs-lookup"><span data-stu-id="886a7-120">"\end"</span></span>
- <span data-ttu-id="886a7-121">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="886a7-121">"\sqrt"</span></span>
- <span data-ttu-id="886a7-122">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="886a7-122">"\otimes"</span></span>
- <span data-ttu-id="886a7-123">"{"</span><span class="sxs-lookup"><span data-stu-id="886a7-123">"{"</span></span>
- <span data-ttu-id="886a7-124">"}"</span><span class="sxs-lookup"><span data-stu-id="886a7-124">"}"</span></span>
- <span data-ttu-id="886a7-125">"\text"</span><span class="sxs-lookup"><span data-stu-id="886a7-125">"\text"</span></span>
- <span data-ttu-id="886a7-126">"\phi"</span><span class="sxs-lookup"><span data-stu-id="886a7-126">"\phi"</span></span>
- <span data-ttu-id="886a7-127">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="886a7-127">"\kappa"</span></span>
- <span data-ttu-id="886a7-128">"\psi"</span><span class="sxs-lookup"><span data-stu-id="886a7-128">"\psi"</span></span>
- <span data-ttu-id="886a7-129">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="886a7-129">"\alpha"</span></span>
- <span data-ttu-id="886a7-130">"\beta"</span><span class="sxs-lookup"><span data-stu-id="886a7-130">"\beta"</span></span>
- <span data-ttu-id="886a7-131">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="886a7-131">"\gamma"</span></span>
- <span data-ttu-id="886a7-132">"\delta"</span><span class="sxs-lookup"><span data-stu-id="886a7-132">"\delta"</span></span>
- <span data-ttu-id="886a7-133">"\omega"</span><span class="sxs-lookup"><span data-stu-id="886a7-133">"\omega"</span></span>
- <span data-ttu-id="886a7-134">"\bra"</span><span class="sxs-lookup"><span data-stu-id="886a7-134">"\bra"</span></span>
- <span data-ttu-id="886a7-135">"\ket"</span><span class="sxs-lookup"><span data-stu-id="886a7-135">"\ket"</span></span>
- <span data-ttu-id="886a7-136">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="886a7-136">"\boldone"</span></span>
- <span data-ttu-id="886a7-137">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="886a7-137">"\\\\"</span></span>
- <span data-ttu-id="886a7-138">"\\"</span><span class="sxs-lookup"><span data-stu-id="886a7-138">"\\"</span></span>
- <span data-ttu-id="886a7-139">"="</span><span class="sxs-lookup"><span data-stu-id="886a7-139">"="</span></span>
- <span data-ttu-id="886a7-140">"\frac"</span><span class="sxs-lookup"><span data-stu-id="886a7-140">"\frac"</span></span>
- <span data-ttu-id="886a7-141">"\text"</span><span class="sxs-lookup"><span data-stu-id="886a7-141">"\text"</span></span>
- <span data-ttu-id="886a7-142">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="886a7-142">"\mapsto"</span></span>
- <span data-ttu-id="886a7-143">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="886a7-143">"\dagger"</span></span>
- <span data-ttu-id="886a7-144">"\to"</span><span class="sxs-lookup"><span data-stu-id="886a7-144">"\to"</span></span>
- <span data-ttu-id="886a7-145">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="886a7-145">"\begin{cases}"</span></span>
- <span data-ttu-id="886a7-146">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="886a7-146">"\end{cases}"</span></span>
- <span data-ttu-id="886a7-147">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="886a7-147">"\operatorname"</span></span>
- <span data-ttu-id="886a7-148">"\braket"</span><span class="sxs-lookup"><span data-stu-id="886a7-148">"\braket"</span></span>
- <span data-ttu-id="886a7-149">"\id"</span><span class="sxs-lookup"><span data-stu-id="886a7-149">"\id"</span></span>
- <span data-ttu-id="886a7-150">"\expect"</span><span class="sxs-lookup"><span data-stu-id="886a7-150">"\expect"</span></span>
- <span data-ttu-id="886a7-151">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="886a7-151">"\defeq"</span></span>
- <span data-ttu-id="886a7-152">"\variance"</span><span class="sxs-lookup"><span data-stu-id="886a7-152">"\variance"</span></span>
- <span data-ttu-id="886a7-153">"\dd"</span><span class="sxs-lookup"><span data-stu-id="886a7-153">"\dd"</span></span>
- <span data-ttu-id="886a7-154">"&"</span><span class="sxs-lookup"><span data-stu-id="886a7-154">"&"</span></span>
- <span data-ttu-id="886a7-155">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="886a7-155">"\begin{align}"</span></span>
- <span data-ttu-id="886a7-156">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="886a7-156">"\end{align}"</span></span>
- <span data-ttu-id="886a7-157">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="886a7-157">"\Lambda"</span></span>
- <span data-ttu-id="886a7-158">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="886a7-158">"\lambda"</span></span>
- <span data-ttu-id="886a7-159">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="886a7-159">"\Omega"</span></span>
- <span data-ttu-id="886a7-160">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="886a7-160">"\mathrm"</span></span>
- <span data-ttu-id="886a7-161">"\left"</span><span class="sxs-lookup"><span data-stu-id="886a7-161">"\left"</span></span>
- <span data-ttu-id="886a7-162">"\right"</span><span class="sxs-lookup"><span data-stu-id="886a7-162">"\right"</span></span>
- <span data-ttu-id="886a7-163">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="886a7-163">"\qquad"</span></span>
- <span data-ttu-id="886a7-164">"\times"</span><span class="sxs-lookup"><span data-stu-id="886a7-164">"\times"</span></span>
- <span data-ttu-id="886a7-165">"\big"</span><span class="sxs-lookup"><span data-stu-id="886a7-165">"\big"</span></span>
- <span data-ttu-id="886a7-166">"\langle"</span><span class="sxs-lookup"><span data-stu-id="886a7-166">"\langle"</span></span>
- <span data-ttu-id="886a7-167">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="886a7-167">"\rangle"</span></span>
- <span data-ttu-id="886a7-168">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="886a7-168">"\bigg"</span></span>
- <span data-ttu-id="886a7-169">"\Big"</span><span class="sxs-lookup"><span data-stu-id="886a7-169">"\Big"</span></span>
- <span data-ttu-id="886a7-170">"|"</span><span class="sxs-lookup"><span data-stu-id="886a7-170">"|"</span></span>
- <span data-ttu-id="886a7-171">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="886a7-171">"\mathbb"</span></span>
- <span data-ttu-id="886a7-172">"\vec"</span><span class="sxs-lookup"><span data-stu-id="886a7-172">"\vec"</span></span>
- <span data-ttu-id="886a7-173">"\in"</span><span class="sxs-lookup"><span data-stu-id="886a7-173">"\in"</span></span>
- <span data-ttu-id="886a7-174">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="886a7-174">"\texttt"</span></span>
- <span data-ttu-id="886a7-175">"\ne"</span><span class="sxs-lookup"><span data-stu-id="886a7-175">"\ne"</span></span>
- <span data-ttu-id="886a7-176">"<"</span><span class="sxs-lookup"><span data-stu-id="886a7-176">"<"</span></span>
- <span data-ttu-id="886a7-177">">"</span><span class="sxs-lookup"><span data-stu-id="886a7-177">">"</span></span>
- <span data-ttu-id="886a7-178">"\leq"</span><span class="sxs-lookup"><span data-stu-id="886a7-178">"\leq"</span></span>
- <span data-ttu-id="886a7-179">"\geq"</span><span class="sxs-lookup"><span data-stu-id="886a7-179">"\geq"</span></span>
- <span data-ttu-id="886a7-180">"~~"</span><span class="sxs-lookup"><span data-stu-id="886a7-180">"~~"</span></span>
- <span data-ttu-id="886a7-181">"~"</span><span class="sxs-lookup"><span data-stu-id="886a7-181">"~"</span></span>
- <span data-ttu-id="886a7-182">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="886a7-182">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="886a7-183">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="886a7-183">"\end{bmatrix}"</span></span>
- <span data-ttu-id="886a7-184">"\_"</span><span class="sxs-lookup"><span data-stu-id="886a7-184">"\_"</span></span>

---
# <a name="advanced-matrix-concepts"></a><span data-ttu-id="886a7-185">高级矩阵概念</span><span class="sxs-lookup"><span data-stu-id="886a7-185">Advanced Matrix Concepts</span></span> #

<span data-ttu-id="886a7-186">现在，我们将矩阵操作扩展到 [*本征值、本征向量*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) 和 [*指数*](https://en.wikipedia.org/wiki/Matrix_exponential) ，这构成了我们需要描述和实现量程算法的一组基本工具。</span><span class="sxs-lookup"><span data-stu-id="886a7-186">We now extend our manipulation of Matrices to [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) and [*Exponentials*](https://en.wikipedia.org/wiki/Matrix_exponential) which form a fundamental set of tools we need to describe and implement quantum algorithms.</span></span>

## <a name="eigenvalues-and-eigenvectors"></a><span data-ttu-id="886a7-187">本征值和本征向量</span><span class="sxs-lookup"><span data-stu-id="886a7-187">Eigenvalues and Eigenvectors</span></span> ##

<span data-ttu-id="886a7-188">假设 $ M 是 $ 正方形矩阵， $ v 是 $ 不是全零向量的向量 (即，其所有条目都等于 $ 0) 的矢量 $ 。</span><span class="sxs-lookup"><span data-stu-id="886a7-188">Let $M$ be a square matrix and $v$ be a vector that is not the all zeros vector (i.e., the vector with all entries equal to $0$).</span></span>

<span data-ttu-id="886a7-189">假设 $ v $ 是 M 的 [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) ，  $ 如果 $ 将 $ Mv = cv $ 用于某个数字 $ c $ 。</span><span class="sxs-lookup"><span data-stu-id="886a7-189">We say $v$ is an [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) of  $M$ if $Mv = cv$ for some number $c$.</span></span> <span data-ttu-id="886a7-190">我们说 $ c $ 是对应[](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors)于 eigenvector v 的 eigenvalue $ $ 。</span><span class="sxs-lookup"><span data-stu-id="886a7-190">We say $c$ is the [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) corresponding to the eigenvector $v$.</span></span> <span data-ttu-id="886a7-191">通常 $ ，矩阵 M $ 可以将矢量转换为任何其他向量，但 eigenvector 是特殊的，因为它会保持不变，但会乘以数字。</span><span class="sxs-lookup"><span data-stu-id="886a7-191">In general a matrix $M$ may transform a vector into any other vector, but an eigenvector is special because it is left unchanged except for being multiplied by a number.</span></span> <span data-ttu-id="886a7-192">请注意，如果 $ v $ 是带有 eigenvalue c 的 eigenvector $ $ ，则 $ av $ 也是 $ $ 具有相同 eigenvalue 的任何非零) 的 eigenvector (。</span><span class="sxs-lookup"><span data-stu-id="886a7-192">Note that if $v$ is an eigenvector with eigenvalue $c$, then $av$ is also an eigenvector (for any nonzero $a$) with the same eigenvalue.</span></span>

<span data-ttu-id="886a7-193">例如，对于恒等矩阵，每个向量 $ v $ 均为 eigenvalue 1 的 $ eigenvector $ 。</span><span class="sxs-lookup"><span data-stu-id="886a7-193">For example, for the identity matrix, every vector $v$ is an eigenvector with eigenvalue $1$.</span></span>

<span data-ttu-id="886a7-194">作为另一个示例，请考虑这样一种 [*对角矩阵*](https://en.wikipedia.org/wiki/Diagonal_matrix) $ D $ ：</span><span class="sxs-lookup"><span data-stu-id="886a7-194">As another example, consider a [*diagonal matrix*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D$ which only has nonzero entries on the diagonal:</span></span>

$$
\begin{bmatrix}
<span data-ttu-id="886a7-195">d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="886a7-195">d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="886a7-196">矢量</span><span class="sxs-lookup"><span data-stu-id="886a7-196">The vectors</span></span>

<span data-ttu-id="886a7-197">$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix} ， \begin{bmatrix} 0 \\\\ 1 \\\\ 0 \end{bmatrix} ， \begin{bmatrix} 0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="886a7-197">$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}, \begin{bmatrix}0 \\\\ 1 \\\\ 0\end{bmatrix} and \begin{bmatrix}0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span></span>

<span data-ttu-id="886a7-198">是此矩阵的本征向量，分别为本征值  $ d_1 $ 、 $ d_2 $ 和 $ d_3 $ 。</span><span class="sxs-lookup"><span data-stu-id="886a7-198">are eigenvectors of this matrix with eigenvalues  $d_1$, $d_2$, and $d_3$, respectively.</span></span> <span data-ttu-id="886a7-199">如果 $ d_1 $ 、 $ d_2 $ 和 $ d_3 $ 都是不同的数字，则这些向量 (，它们的序列号) 是 matrix d 的唯一本征向量 $ $ 。通常，对于对角矩阵，可以轻松地将本征值和本征向量读取。</span><span class="sxs-lookup"><span data-stu-id="886a7-199">If $d_1$, $d_2$, and $d_3$ are distinct numbers, then these vectors (and their multiples) are the only eigenvectors of the matrix $D$. In general, for a diagonal matrix it is easy to read off the eigenvalues and eigenvectors.</span></span> <span data-ttu-id="886a7-200">本征值是显示在对角线上的所有数字，其各自的本征向量是单位矢量，其中一项等于 $ 1 $ ，剩余项等于 $ 0 $ 。</span><span class="sxs-lookup"><span data-stu-id="886a7-200">The eigenvalues are all the numbers appearing on the diagonal, and their respective eigenvectors are the unit vectors with one entry equal to $1$ and the remaining entries equal to $0$.</span></span>

<span data-ttu-id="886a7-201">请注意，在上面的示例中，本征向量的 $ D $ 构成三维 $ 向量的基础 $ 。</span><span class="sxs-lookup"><span data-stu-id="886a7-201">Note in the above example that the eigenvectors of $D$ form a basis for $3$-dimensional vectors.</span></span> <span data-ttu-id="886a7-202">基础是一组矢量，以便可以将任何矢量编写为它们的线性组合。</span><span class="sxs-lookup"><span data-stu-id="886a7-202">A basis is a set of vectors such that any vector can be written as a linear combination of them.</span></span> <span data-ttu-id="886a7-203">更明确、 $ v_1 $ 、 $ v_2 $ 和 $ v_3， $ 如果任何向量 $ v $ 可以编写为 $ v a_1 v_1 + a_2 + v_2 a_3 = $ $ $ 、 $ v_3 $ 和 $ a_1 $ a_2 + a_3 +。</span><span class="sxs-lookup"><span data-stu-id="886a7-203">More explicitly, $v_1$, $v_2$, and $v_3$ form a basis if any vector $v$ can be written as $v=a_1 v_1 + a_2 v_2 + a_3 v_3$ for some numbers $a_1$, $a_2$, and $a_3$.</span></span>

<span data-ttu-id="886a7-204">回忆一下，Hermitian 矩阵 (也称为 ") adjoint"，这是一个复杂的正方形矩阵，它相当于其自己的复杂共轭转置，而 "单一矩阵" 是一种复杂的正方形矩阵，其反转等于其 adjoint 或复数共轭转置。</span><span class="sxs-lookup"><span data-stu-id="886a7-204">Recall that a Hermitian matrix (also called self-adjoint) is a complex square matrix equal to its own complex conjugate transpose, while a unitary matrix is a complex square matrix whose inverse is equal to its adjoint or complex conjugate transpose.</span></span>
<span data-ttu-id="886a7-205">对于 Hermitian 和单一矩阵，它们实质上是在量程计算中遇到的唯一矩阵，一般的结果称为 [*spectral 定理*](https://en.wikipedia.org/wiki/Spectral_theorem)，这会断言以下内容：对于任何 Hermitian 或单一矩阵 $ m $ ，都存在一个单一 U，以便 $ $ $ = \dagger $ 对某些对角线矩阵 d 使用 M u ^ d $ U $ 。而且，D 的对角线条目 $ $ 将是本征值的 $ M $ 。</span><span class="sxs-lookup"><span data-stu-id="886a7-205">For Hermitian and unitary matrices, which are essentially the only matrices encountered in quantum computing, there is a general result known as the [*spectral theorem*](https://en.wikipedia.org/wiki/Spectral_theorem), which asserts the following: For any Hermitian or unitary matrix $M$, there exists a unitary $U$ such that $M=U^\dagger D U$ for some diagonal matrix $D$. Furthermore, the diagonal entries of $D$ will be the eigenvalues of $M$.</span></span>

<span data-ttu-id="886a7-206">我们已经知道如何计算对角矩阵的本征值和本征向量 $ $ 。使用此定理，我们知道，如果 $ v $ 是 $ $ 带有 eigenvalue $ c $ （即，Dv cv）的 D 的 eigenvector， $ = $ 则 $ U ^ \dagger v $ 将是 eigenvector $ M $ with eigenvalue $ c $ 。</span><span class="sxs-lookup"><span data-stu-id="886a7-206">We already know how to compute the eigenvalues and eigenvectors of a diagonal matrix $D$. Using this theorem we know that if $v$ is an eigenvector of $D$ with eigenvalue $c$, i.e., $Dv = cv$, then $U^\dagger v$ will be an eigenvector of $M$ with eigenvalue $c$.</span></span> <span data-ttu-id="886a7-207">这是因为</span><span class="sxs-lookup"><span data-stu-id="886a7-207">This is because</span></span>

<span data-ttu-id="886a7-208">$$M (U ^ \dagger v) = u ^ \dagger d u (u ^ \dagger v) = U ^ \dagger d (u u ^ \dagger) v = u ^ \dagger d v = c u ^ \dagger v。$$</span><span class="sxs-lookup"><span data-stu-id="886a7-208">$$M(U^\dagger v) = U^\dagger D U  (U^\dagger v) =U^\dagger D (U  U^\dagger) v = U^\dagger D v = c U^\dagger v.$$</span></span>

## <a name="matrix-exponentials"></a><span data-ttu-id="886a7-209">Matrix 指数</span><span class="sxs-lookup"><span data-stu-id="886a7-209">Matrix Exponentials</span></span>
<span data-ttu-id="886a7-210">[*矩阵指数*](https://en.wikipedia.org/wiki/Matrix_exponential)还可以精确地定义为指数函数。</span><span class="sxs-lookup"><span data-stu-id="886a7-210">A [*matrix exponential*](https://en.wikipedia.org/wiki/Matrix_exponential) can also be defined in exact analogy to the exponential function.</span></span>  <span data-ttu-id="886a7-211">矩阵 a 的矩阵指数 $ $ 可表示为</span><span class="sxs-lookup"><span data-stu-id="886a7-211">The matrix exponential of a matrix $A$ can be expressed as</span></span>

$$
<span data-ttu-id="886a7-212">e ^ A = \boldone + a + \frac { a ^ 2 } { 2！ } + \frac {^ 3 } { 3！}+\cdots</span><span class="sxs-lookup"><span data-stu-id="886a7-212">e^A=\boldone + A + \frac{A^2}{2!}+\frac{A^3}{3!}+\cdots</span></span>
$$

<span data-ttu-id="886a7-213">这一点很重要，因为 $ { } $ Hermitian matrix $ B 形式的单一矩阵（形式为 e ^ iB）描述了量子机械时间演变 $ 。 出于此原因，执行 matrix 指数是量程计算的基本组成部分，因此 Q# 提供了用于描述这些操作的内部例程。</span><span class="sxs-lookup"><span data-stu-id="886a7-213">This is important because quantum mechanical time evolution is described by a unitary matrix of the form $e^{iB}$ for Hermitian matrix $B$.  For this reason, performing matrix exponentials is a fundamental part of quantum computing and as such Q# offers intrinsic routines for describing these operations.</span></span>
<span data-ttu-id="886a7-214">有很多方法可用于计算传统计算机上的矩阵指数，一般为数值逼近，这类指数为充满 with 担风险。</span><span class="sxs-lookup"><span data-stu-id="886a7-214">There are many ways in practice to compute a matrix exponential on a classical computer, and in general numerically approximating such an exponential is fraught with peril.</span></span>  <span data-ttu-id="886a7-215">请参阅 [*Cleve Moler 和 Charles Van 贷款。"用于计算矩阵指数的可疑方法。"SIAM 评审 20.4 (1978) ： 801-836*](https://doi.org/10.1137/S00361445024180) ，详细了解涉及的挑战。</span><span class="sxs-lookup"><span data-stu-id="886a7-215">See [*Cleve Moler and Charles Van Loan. "Nineteen dubious ways to compute the exponential of a matrix." SIAM review 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) for more information about the challenges involved.</span></span>

<span data-ttu-id="886a7-216">了解如何计算矩阵指数的最简单方法是通过该矩阵的本征值和本征向量。</span><span class="sxs-lookup"><span data-stu-id="886a7-216">The easiest way to understand how to compute the exponential of a matrix is through the eigenvalues and eigenvectors of that matrix.</span></span>  <span data-ttu-id="886a7-217">具体而言，以上所述的 spectral 定理说明对于每个 Hermitian 或单一矩阵，都 $ $ 存在一个单一的矩阵 $ u $ 和一个对角矩阵 $ D $ ，这 $ 是 = u ^ \dagger d u $ 。 由于 unitarity 的属性，我们有 $ ^ 2 = u ^ \dagger D ^ 2 u $ ，同样适用于任何 power $ p $ $ A ^ p = u ^ \dagger D ^ p u $ 。 如果将此替换为我们获得的运算符指数的运算符定义：</span><span class="sxs-lookup"><span data-stu-id="886a7-217">Specifically, the spectral theorem discussed above says that for every Hermitian or unitary matrix $A$ there exists a unitary matrix $U$ and a diagonal matrix $D$ such that $A=U^\dagger D U$.  Because of the properties of unitarity we have that $A^2 = U^\dagger D^2 U$ and similarly for any power $p$ $A^p = U^\dagger D^p U$.  If we substitute this into the operator definition of the operator exponential we obtain:</span></span>

$$
<span data-ttu-id="886a7-218">e ^ A = U ^ \dagger \left (\boldone + d + \frac { d ^ 2 } { 2！ } + \cdots \right) U = u ^ \dagger \begin{bmatrix} \exp (D_ { 11 }) & 0 & \cdots & 0 \\\\ 0 & \exp (D_ { 22 }) & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0 & 0 & \cdots & \exp (D_ { NN }) \end{bmatrix} U。$$</span><span class="sxs-lookup"><span data-stu-id="886a7-218">e^A= U^\dagger \left(\boldone +D +\frac{D^2}{2!}+\cdots \right)U= U^\dagger \begin{bmatrix}\exp(D_{11}) & 0 &\cdots &0\\\\ 0 & \exp(D_{22})&\cdots& 0\\\\ \vdots &\vdots &\ddots &\vdots\\\\ 0&0&\cdots&\exp(D_{NN}) \end{bmatrix} U. $$</span></span>

<span data-ttu-id="886a7-219">换而言之，如果转换为矩阵 A 的 eigenbasis， $ $ 则矩阵指数等效于计算矩阵本征值的普通指数。</span><span class="sxs-lookup"><span data-stu-id="886a7-219">In other words, if you transform to the eigenbasis of the matrix $A$ then computing the matrix exponential is equivalent to computing the ordinary exponential of the eigenvalues of the matrix.</span></span>  <span data-ttu-id="886a7-220">由于量程计算中的许多操作都涉及到执行矩阵指数，因此，转换为矩阵的 eigenbasis 以简化执行运算符指数的这一技巧会经常出现，并且是本指南后面部分中讨论的 Trotter – Suzuki 样式的量程模拟方法的基础。</span><span class="sxs-lookup"><span data-stu-id="886a7-220">As many operations in quantum computing involve performing matrix exponentials, this trick of transforming into the eigenbasis of a matrix to simplify performing the operator exponential appears frequently and is the basis behind many quantum algorithms such as Trotter–Suzuki-style quantum simulation methods discussed later in this guide.</span></span>

<span data-ttu-id="886a7-221">另一种有用的属性是： $ b $ 既是单一的又是 Hermitian 的，即 $ b = b ^ { -1 } = b ^ \dagger $ then $ b ^ 2 = \boldone $ 。</span><span class="sxs-lookup"><span data-stu-id="886a7-221">Another useful property is if $B$ is both unitary and Hermitian, i.e., $B=B^{-1}=B^\dagger$ then $B^2=\boldone$.</span></span> <span data-ttu-id="886a7-222">通过将此规则应用于矩阵指数的以上扩展，并将 $ \boldone $ 和 $ B 项组合在 $ 一起，可以看到，对于任何实际值 $ x $ 标识</span><span class="sxs-lookup"><span data-stu-id="886a7-222">By applying this rule to the above expansion of the matrix exponential and by grouping the $\boldone$ and the $B$ terms together, it can be see that for any real value $x$ the identity</span></span>

<span data-ttu-id="886a7-223">$$e ^ { iBx } = \boldone \cos (x) + iB\sin (x) $$</span><span class="sxs-lookup"><span data-stu-id="886a7-223">$$e^{iBx}=\boldone \cos(x)+ iB\sin(x)$$</span></span>


<span data-ttu-id="886a7-224">保留.</span><span class="sxs-lookup"><span data-stu-id="886a7-224">holds.</span></span> <span data-ttu-id="886a7-225">这一技巧特别有用，因为它允许有关操作矩阵指数的原因，即使 b 的维度的 $ $ 大小呈指数大，在 $ b 既是单一的还是 Hermitian 的情况下，也是如此 $ 。</span><span class="sxs-lookup"><span data-stu-id="886a7-225">This trick is especially useful because it allows to reason about the actions matrix exponentials have, even if the dimension of $B$ is exponentially large, for the special case when $B$ is both unitary and Hermitian.</span></span>
