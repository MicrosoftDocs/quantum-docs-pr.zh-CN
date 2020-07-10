---
<span data-ttu-id="ca90a-101">标题：量程计算说明中的矢量和矩阵：了解有关如何使用向量和矩阵的基本知识。</span><span class="sxs-lookup"><span data-stu-id="ca90a-101">title: Vectors and matrices in quantum computing description: Learn the basics of how to work with vectors and matrices.</span></span>
<span data-ttu-id="ca90a-102">author： QuantumWriter uid：： nawiebe@microsoft.com ms. 日期：12/11/2017 毫秒。主题：项目不相关：</span><span class="sxs-lookup"><span data-stu-id="ca90a-102">author: QuantumWriter uid: microsoft.quantum.concepts.vectors ms.author: nawiebe@microsoft.com ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="ca90a-103">"$$"</span><span class="sxs-lookup"><span data-stu-id="ca90a-103">"$$"</span></span>
- <span data-ttu-id="ca90a-104">"$$"</span><span class="sxs-lookup"><span data-stu-id="ca90a-104">"$$"</span></span>
- <span data-ttu-id="ca90a-105">"$"</span><span class="sxs-lookup"><span data-stu-id="ca90a-105">"$"</span></span>
- <span data-ttu-id="ca90a-106">"$"</span><span class="sxs-lookup"><span data-stu-id="ca90a-106">"$"</span></span>
- <span data-ttu-id="ca90a-107">"$"</span><span class="sxs-lookup"><span data-stu-id="ca90a-107">"$"</span></span>
- <span data-ttu-id="ca90a-108">"$$"</span><span class="sxs-lookup"><span data-stu-id="ca90a-108">"$$"</span></span>
- <span data-ttu-id="ca90a-109">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="ca90a-109">"\cdots"</span></span>
- <span data-ttu-id="ca90a-110">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="ca90a-110">"bmatrix"</span></span>
- <span data-ttu-id="ca90a-111">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="ca90a-111">"\ddots"</span></span>
- <span data-ttu-id="ca90a-112">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="ca90a-112">"\equiv"</span></span>
- <span data-ttu-id="ca90a-113">"\sum"</span><span class="sxs-lookup"><span data-stu-id="ca90a-113">"\sum"</span></span>
- <span data-ttu-id="ca90a-114">"\begin"</span><span class="sxs-lookup"><span data-stu-id="ca90a-114">"\begin"</span></span>
- <span data-ttu-id="ca90a-115">"\end"</span><span class="sxs-lookup"><span data-stu-id="ca90a-115">"\end"</span></span>
- <span data-ttu-id="ca90a-116">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="ca90a-116">"\sqrt"</span></span>
- <span data-ttu-id="ca90a-117">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="ca90a-117">"\otimes"</span></span>
- <span data-ttu-id="ca90a-118">"{"</span><span class="sxs-lookup"><span data-stu-id="ca90a-118">"{"</span></span>
- <span data-ttu-id="ca90a-119">"}"</span><span class="sxs-lookup"><span data-stu-id="ca90a-119">"}"</span></span>
- <span data-ttu-id="ca90a-120">"\text"</span><span class="sxs-lookup"><span data-stu-id="ca90a-120">"\text"</span></span>
- <span data-ttu-id="ca90a-121">"\phi"</span><span class="sxs-lookup"><span data-stu-id="ca90a-121">"\phi"</span></span>
- <span data-ttu-id="ca90a-122">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="ca90a-122">"\kappa"</span></span>
- <span data-ttu-id="ca90a-123">"\psi"</span><span class="sxs-lookup"><span data-stu-id="ca90a-123">"\psi"</span></span>
- <span data-ttu-id="ca90a-124">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="ca90a-124">"\alpha"</span></span>
- <span data-ttu-id="ca90a-125">"\beta"</span><span class="sxs-lookup"><span data-stu-id="ca90a-125">"\beta"</span></span>
- <span data-ttu-id="ca90a-126">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="ca90a-126">"\gamma"</span></span>
- <span data-ttu-id="ca90a-127">"\delta"</span><span class="sxs-lookup"><span data-stu-id="ca90a-127">"\delta"</span></span>
- <span data-ttu-id="ca90a-128">"\omega"</span><span class="sxs-lookup"><span data-stu-id="ca90a-128">"\omega"</span></span>
- <span data-ttu-id="ca90a-129">"\bra"</span><span class="sxs-lookup"><span data-stu-id="ca90a-129">"\bra"</span></span>
- <span data-ttu-id="ca90a-130">"\ket"</span><span class="sxs-lookup"><span data-stu-id="ca90a-130">"\ket"</span></span>
- <span data-ttu-id="ca90a-131">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="ca90a-131">"\boldone"</span></span>
- <span data-ttu-id="ca90a-132">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="ca90a-132">"\\\\"</span></span>
- <span data-ttu-id="ca90a-133">"\\"</span><span class="sxs-lookup"><span data-stu-id="ca90a-133">"\\"</span></span>
- <span data-ttu-id="ca90a-134">"="</span><span class="sxs-lookup"><span data-stu-id="ca90a-134">"="</span></span>
- <span data-ttu-id="ca90a-135">"\frac"</span><span class="sxs-lookup"><span data-stu-id="ca90a-135">"\frac"</span></span>
- <span data-ttu-id="ca90a-136">"\text"</span><span class="sxs-lookup"><span data-stu-id="ca90a-136">"\text"</span></span>
- <span data-ttu-id="ca90a-137">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="ca90a-137">"\mapsto"</span></span>
- <span data-ttu-id="ca90a-138">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="ca90a-138">"\dagger"</span></span>
- <span data-ttu-id="ca90a-139">"\to"</span><span class="sxs-lookup"><span data-stu-id="ca90a-139">"\to"</span></span>
- <span data-ttu-id="ca90a-140">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="ca90a-140">"\begin{cases}"</span></span>
- <span data-ttu-id="ca90a-141">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="ca90a-141">"\end{cases}"</span></span>
- <span data-ttu-id="ca90a-142">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="ca90a-142">"\operatorname"</span></span>
- <span data-ttu-id="ca90a-143">"\braket"</span><span class="sxs-lookup"><span data-stu-id="ca90a-143">"\braket"</span></span>
- <span data-ttu-id="ca90a-144">"\id"</span><span class="sxs-lookup"><span data-stu-id="ca90a-144">"\id"</span></span>
- <span data-ttu-id="ca90a-145">"\expect"</span><span class="sxs-lookup"><span data-stu-id="ca90a-145">"\expect"</span></span>
- <span data-ttu-id="ca90a-146">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="ca90a-146">"\defeq"</span></span>
- <span data-ttu-id="ca90a-147">"\variance"</span><span class="sxs-lookup"><span data-stu-id="ca90a-147">"\variance"</span></span>
- <span data-ttu-id="ca90a-148">"\dd"</span><span class="sxs-lookup"><span data-stu-id="ca90a-148">"\dd"</span></span>
- <span data-ttu-id="ca90a-149">"&"</span><span class="sxs-lookup"><span data-stu-id="ca90a-149">"&"</span></span>
- <span data-ttu-id="ca90a-150">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="ca90a-150">"\begin{align}"</span></span>
- <span data-ttu-id="ca90a-151">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="ca90a-151">"\end{align}"</span></span>
- <span data-ttu-id="ca90a-152">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="ca90a-152">"\Lambda"</span></span>
- <span data-ttu-id="ca90a-153">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="ca90a-153">"\lambda"</span></span>
- <span data-ttu-id="ca90a-154">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="ca90a-154">"\Omega"</span></span>
- <span data-ttu-id="ca90a-155">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="ca90a-155">"\mathrm"</span></span>
- <span data-ttu-id="ca90a-156">"\left"</span><span class="sxs-lookup"><span data-stu-id="ca90a-156">"\left"</span></span>
- <span data-ttu-id="ca90a-157">"\right"</span><span class="sxs-lookup"><span data-stu-id="ca90a-157">"\right"</span></span>
- <span data-ttu-id="ca90a-158">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="ca90a-158">"\qquad"</span></span>
- <span data-ttu-id="ca90a-159">"\times"</span><span class="sxs-lookup"><span data-stu-id="ca90a-159">"\times"</span></span>
- <span data-ttu-id="ca90a-160">"\big"</span><span class="sxs-lookup"><span data-stu-id="ca90a-160">"\big"</span></span>
- <span data-ttu-id="ca90a-161">"\langle"</span><span class="sxs-lookup"><span data-stu-id="ca90a-161">"\langle"</span></span>
- <span data-ttu-id="ca90a-162">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="ca90a-162">"\rangle"</span></span>
- <span data-ttu-id="ca90a-163">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="ca90a-163">"\bigg"</span></span>
- <span data-ttu-id="ca90a-164">"\Big"</span><span class="sxs-lookup"><span data-stu-id="ca90a-164">"\Big"</span></span>
- <span data-ttu-id="ca90a-165">"|"</span><span class="sxs-lookup"><span data-stu-id="ca90a-165">"|"</span></span>
- <span data-ttu-id="ca90a-166">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="ca90a-166">"\mathbb"</span></span>
- <span data-ttu-id="ca90a-167">"\vec"</span><span class="sxs-lookup"><span data-stu-id="ca90a-167">"\vec"</span></span>
- <span data-ttu-id="ca90a-168">"\in"</span><span class="sxs-lookup"><span data-stu-id="ca90a-168">"\in"</span></span>
- <span data-ttu-id="ca90a-169">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="ca90a-169">"\texttt"</span></span>
- <span data-ttu-id="ca90a-170">"\ne"</span><span class="sxs-lookup"><span data-stu-id="ca90a-170">"\ne"</span></span>
- <span data-ttu-id="ca90a-171">"<"</span><span class="sxs-lookup"><span data-stu-id="ca90a-171">"<"</span></span>
- <span data-ttu-id="ca90a-172">">"</span><span class="sxs-lookup"><span data-stu-id="ca90a-172">">"</span></span>
- <span data-ttu-id="ca90a-173">"\leq"</span><span class="sxs-lookup"><span data-stu-id="ca90a-173">"\leq"</span></span>
- <span data-ttu-id="ca90a-174">"\geq"</span><span class="sxs-lookup"><span data-stu-id="ca90a-174">"\geq"</span></span>
- <span data-ttu-id="ca90a-175">"~~"</span><span class="sxs-lookup"><span data-stu-id="ca90a-175">"~~"</span></span>
- <span data-ttu-id="ca90a-176">"~"</span><span class="sxs-lookup"><span data-stu-id="ca90a-176">"~"</span></span>
- <span data-ttu-id="ca90a-177">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="ca90a-177">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="ca90a-178">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="ca90a-178">"\end{bmatrix}"</span></span>
- <span data-ttu-id="ca90a-179">"\_"</span><span class="sxs-lookup"><span data-stu-id="ca90a-179">"\_"</span></span>

---

# <a name="vectors-and-matrices"></a><span data-ttu-id="ca90a-180">向量和矩阵</span><span class="sxs-lookup"><span data-stu-id="ca90a-180">Vectors and Matrices</span></span>

<span data-ttu-id="ca90a-181">熟悉矢量和矩阵对于了解量程计算至关重要。</span><span class="sxs-lookup"><span data-stu-id="ca90a-181">Some familiarity with vectors and matrices is essential to understand quantum computing.</span></span> <span data-ttu-id="ca90a-182">我们提供了以下简短简介，并建议读者阅读有关线性代数（如*Strang、 (1993) 的标准引用。线性代数简介 () 。Wellesley、MA： Wellesley-剑桥按下*或联机引用，如[线性代数](http://joshua.smcvt.edu/linearalgebra/)。</span><span class="sxs-lookup"><span data-stu-id="ca90a-182">We provide a brief introduction below and interested readers are recommended to read a standard reference on linear algebra such as *Strang, G. (1993). Introduction to linear algebra (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* or an online reference such as [Linear Algebra](http://joshua.smcvt.edu/linearalgebra/).</span></span>

<span data-ttu-id="ca90a-183">列向量 (或只是[*矢量*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $ v of $ dimension (或 size) $ n $ 为 $ n 复数的集合 $ (v_1 $ 、v_2、\ldots、v_n) $ 排列为一列：</span><span class="sxs-lookup"><span data-stu-id="ca90a-183">A column vector (or simply [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v$ of dimension (or size) $n$ is a collection of $n$ complex numbers $(v_1,v_2,\ldots,v_n)$ arranged as a column:</span></span>

$$<span data-ttu-id="ca90a-184">向量=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="ca90a-184">v =\begin{bmatrix}</span></span>
<span data-ttu-id="ca90a-185">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-185">v_1\\\\</span></span>
<span data-ttu-id="ca90a-186">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-186">v_2\\\\</span></span>
<span data-ttu-id="ca90a-187">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-187">\vdots\\\\</span></span>
<span data-ttu-id="ca90a-188">v_n\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="ca90a-188">v_n \end{bmatrix}$$</span></span>

<span data-ttu-id="ca90a-189">向量 v 的标准 $ $ 定义为 $ \sqrt { \sum \_ i i | \_ i i | ^ 2 } $ 。</span><span class="sxs-lookup"><span data-stu-id="ca90a-189">The norm of a vector $v$ is defined as $\sqrt{\sum\_i |v\_i|^2}$.</span></span> <span data-ttu-id="ca90a-190">矢量称为单位规范 (或如果其标准为1，则称为[*单位矢量*](https://en.wikipedia.org/wiki/Unit_vector)) $ $ 。</span><span class="sxs-lookup"><span data-stu-id="ca90a-190">A vector is said to be of unit norm (or alternatively it is called a [*unit vector*](https://en.wikipedia.org/wiki/Unit_vector)) if its norm is $1$.</span></span> <span data-ttu-id="ca90a-191">向量 v 的[*adjoint*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ $ 表示 $ v ^ \dagger $ ，并定义为以下行向量 $ \* $ ，其中表示复数共轭。</span><span class="sxs-lookup"><span data-stu-id="ca90a-191">The [*adjoint of a vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v$ is denoted $v^\dagger$ and is defined to be the following row vector where $\*$ denotes the complex conjugate,</span></span>

$$<span data-ttu-id="ca90a-192">\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix} ^ \dagger = \begin{bmatrix} v_1 ^ \* & \cdots & v_n ^ \*\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="ca90a-192">\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix}^\dagger = \begin{bmatrix}v_1^\* & \cdots & v_n^\* \end{bmatrix}$$</span></span>

<span data-ttu-id="ca90a-193">将两个矢量相乘的最常见方法是通过[*内部产品*](https://en.wikipedia.org/wiki/Inner_product_space)（也称为点积）。</span><span class="sxs-lookup"><span data-stu-id="ca90a-193">The most common way to multiply two vectors together is through the [*inner product*](https://en.wikipedia.org/wiki/Inner_product_space), also known as a dot product.</span></span>  <span data-ttu-id="ca90a-194">内部产品提供了一个向量的投影到另一个向量，这在描述如何将一个向量表达为其他更简单的向量的总和方面非常有用。</span><span class="sxs-lookup"><span data-stu-id="ca90a-194">The inner product gives the projection of one vector onto another and is invaluable in describing how to express one vector as a sum of other simpler vectors.</span></span>  <span data-ttu-id="ca90a-195">U 和 v 之间的内部积 $ $ $ $ ，表示 $ \left \langle u，v \right \rangle $ 定义为</span><span class="sxs-lookup"><span data-stu-id="ca90a-195">The inner product between $u$ and $v$, denoted $\left\langle u, v\right\rangle$ is defined as</span></span>

$$
\langle<span data-ttu-id="ca90a-196">u，v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } v_1 + \cdots + u \_ n ^ { \* } v \_ n。</span><span class="sxs-lookup"><span data-stu-id="ca90a-196"> u, v\rangle = u^\dagger v=u\_1^{\*} v_1 + \cdots + u\_n^{\*} v\_n.</span></span>
$$

<span data-ttu-id="ca90a-197">此表示法还允许将 vector v 的 $ 标准 $ 编写为 $ \sqrt { \langle v，v \rangle } $ 。</span><span class="sxs-lookup"><span data-stu-id="ca90a-197">This notation also allows the norm of a vector $v$ to be written as $\sqrt{\langle v, v\rangle}$.</span></span>

<span data-ttu-id="ca90a-198">我们可以将一个向量与数字 $ c 相乘 $ ，以形成一个新向量，其项乘以 $ c $ 。</span><span class="sxs-lookup"><span data-stu-id="ca90a-198">We can multiply a vector with a number $c$ to form a new vector whose entries are multiplied by $c$.</span></span> <span data-ttu-id="ca90a-199">我们还可以添加两个向量 $ u $ 和 v， $ $ 以形成新的向量，其项是 $ u $ 和 v 项的 $ 总和 $ 。</span><span class="sxs-lookup"><span data-stu-id="ca90a-199">We can also add two vectors $u$ and $v$ to form a new vector whose entries are the sum of the entries of $u$ and $v$.</span></span> <span data-ttu-id="ca90a-200">这些操作如下所示：</span><span class="sxs-lookup"><span data-stu-id="ca90a-200">These operations are depicted below:</span></span>

$$<span data-ttu-id="ca90a-201">\mathrm{如果为 } ~ u=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="ca90a-201">\mathrm{If}~u =\begin{bmatrix}</span></span>
<span data-ttu-id="ca90a-202">u_1\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-202">u_1\\\\</span></span>
<span data-ttu-id="ca90a-203">u_2\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-203">u_2\\\\</span></span>
<span data-ttu-id="ca90a-204">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-204">\vdots\\\\</span></span>
<span data-ttu-id="ca90a-205">u_n \end{bmatrix} ~ \mathrm { 和}~</span><span class="sxs-lookup"><span data-stu-id="ca90a-205">u_n \end{bmatrix}~\mathrm{and}~</span></span>
<span data-ttu-id="ca90a-206">向量=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="ca90a-206">v =\begin{bmatrix}</span></span>
    <span data-ttu-id="ca90a-207">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-207">v_1\\\\</span></span>
    <span data-ttu-id="ca90a-208">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-208">v_2\\\\</span></span>
    <span data-ttu-id="ca90a-209">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-209">\vdots\\\\</span></span>
    <span data-ttu-id="ca90a-210">v_n \end{bmatrix} ， ~ \mathrm { 然后}~</span><span class="sxs-lookup"><span data-stu-id="ca90a-210">v_n \end{bmatrix},~\mathrm{then}~</span></span>
<span data-ttu-id="ca90a-211">au + bv=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="ca90a-211">au+bv =\begin{bmatrix}</span></span>
<span data-ttu-id="ca90a-212">au_1 + bv_1\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-212">au_1+bv_1\\\\</span></span>
<span data-ttu-id="ca90a-213">au_2 + bv_2\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-213">au_2+bv_2\\\\</span></span>
<span data-ttu-id="ca90a-214">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-214">\vdots\\\\</span></span>
<span data-ttu-id="ca90a-215">au_n + bv_n \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="ca90a-215">au_n+bv_n \end{bmatrix}.</span></span>
$$

<span data-ttu-id="ca90a-216">大小[*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics))为 $ m n 的 \times 矩阵 $ 是 $ $ 按 $ m 行和 n 列排列的 mn 复数的集合，如下 $ $ $ 所示：</span><span class="sxs-lookup"><span data-stu-id="ca90a-216">A [*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) of size $m \times n$ is a collection of $mn$ complex numbers arranged in $m$ rows and $n$ columns as shown below:</span></span>

$$<span data-ttu-id="ca90a-217">年=</span><span class="sxs-lookup"><span data-stu-id="ca90a-217">M =</span></span> 
\begin{bmatrix}
<span data-ttu-id="ca90a-218">M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1n}\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-218">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\</span></span>
<span data-ttu-id="ca90a-219">M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2n}\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-219">M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="ca90a-220">M_ { m1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { mn}\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-220">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}\\\\</span></span>
\end{bmatrix}<span data-ttu-id="ca90a-221">.$$</span><span class="sxs-lookup"><span data-stu-id="ca90a-221">.$$</span></span>

<span data-ttu-id="ca90a-222">请注意，维度 n 的 $ 矢量 $ 只是大小为 $ n 1 的 \times 矩阵 $ 。</span><span class="sxs-lookup"><span data-stu-id="ca90a-222">Note that a vector of dimension $n$ is simply a matrix of size $n \times 1$.</span></span> <span data-ttu-id="ca90a-223">对于向量，我们可以将矩阵与数字 c 相乘， $ $ 以获取一个新矩阵，其中每个条目都与 $ c 相乘 $ ，并且我们可以添加两个相同大小的矩阵，以生成一个新矩阵，其项是两个矩阵的相应项的总和。</span><span class="sxs-lookup"><span data-stu-id="ca90a-223">As with vectors, we can multiply a matrix with a number $c$ to obtain a new matrix where every entry is multiplied with $c$, and we can add two matrices of the same size to produce a new matrix whose entries are the sum of the respective entries of the two matrices.</span></span> 

## <a name="matrix-multiplication-and-tensor-products"></a><span data-ttu-id="ca90a-224">Matrix 乘法 and Tensor Products</span><span class="sxs-lookup"><span data-stu-id="ca90a-224">Matrix Multiplication and Tensor Products</span></span>

<span data-ttu-id="ca90a-225">我们还可以将 dimension m n 和 n 维度 n p 的两个矩阵相乘， $ $ $ \times $ $ $ $ \times $ 以获取 $ $ dimension m p 的新 matrix p， $ \times $ 如下所示：</span><span class="sxs-lookup"><span data-stu-id="ca90a-225">We can also multiply two matrices $M$ of dimension $m\times n$ and $N$ of dimension $n \times p$ to get a new matrix $P$ of dimension $m \times p$ as follows:</span></span>

\begin{align}
&\begin{bmatrix}
    <span data-ttu-id="ca90a-226">M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1n}\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-226">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\</span></span>
    <span data-ttu-id="ca90a-227">M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2n}\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-227">M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\</span></span>
    \ddots\\\\
    <span data-ttu-id="ca90a-228">M_ { m1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { mn}</span><span class="sxs-lookup"><span data-stu-id="ca90a-228">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}</span></span>
\end{bmatrix}
\begin{bmatrix}
<span data-ttu-id="ca90a-229">N_ { 11 } ~~ N_ { 12 } ~~ \cdots ~~ N_ { 1 p}\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-229">N_{11} ~~ N_{12} ~~ \cdots ~~ N_{1p}\\\\</span></span>
<span data-ttu-id="ca90a-230">N_ { 21 } ~~ N_ { 22 } ~~ \cdots ~~ N_ { 2 p}\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-230">N_{21} ~~ N_{22} ~~ \cdots ~~ N_{2p}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="ca90a-231">N_ { n1 } ~~ N_ { n2 } ~~ \cdots ~~ N_ { np}</span><span class="sxs-lookup"><span data-stu-id="ca90a-231">N_{n1} ~~ N_{n2} ~~ \cdots ~~ N_{np}</span></span>
\end{bmatrix}=\begin{bmatrix}
<span data-ttu-id="ca90a-232">P_ { 11 } ~~ P_ { 12 } ~~ \cdots ~~ P_ { 1 p}\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-232">P_{11} ~~ P_{12} ~~ \cdots ~~ P_{1p}\\\\</span></span>
<span data-ttu-id="ca90a-233">P_ { 21 } ~~ P_ { 22 } ~~ \cdots ~~ P_ { 2 p}\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-233">P_{21} ~~ P_{22} ~~ \cdots ~~ P_{2p}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="ca90a-234">P_ { m1 } ~~ P_ { m2 } ~~ \cdots ~~ P_ { mp}</span><span class="sxs-lookup"><span data-stu-id="ca90a-234">P_{m1} ~~ P_{m2} ~~ \cdots ~~ P_{mp}</span></span>
\end{bmatrix}
\end{align}

<span data-ttu-id="ca90a-235">其中，P 条目 $ $ $ P_ { ik } = \sum _j M_ { ij } N_ { jk } $ 。</span><span class="sxs-lookup"><span data-stu-id="ca90a-235">where the entries of $P$ are $P_{ik} = \sum_j M_{ij}N_{jk}$.</span></span> <span data-ttu-id="ca90a-236">例如，条目 $ P_ { 11 } $ 是 M 第一行的第一行的第一 $ 列， $ 第一列是 $ N $ 。请注意，由于矢量只是矩阵的一种特殊情况，因此此定义延伸到矩阵向量乘法。</span><span class="sxs-lookup"><span data-stu-id="ca90a-236">For example, the entry $P_{11}$ is the inner product of the first row of $M$ with the first column of $N$. Note that since a vector is simply a special case of a matrix, this definition extends to matrix-vector multiplication.</span></span> 

<span data-ttu-id="ca90a-237">我们考虑的所有矩阵均为方形矩阵，其中的行数和列数相等，或向量仅对应于 $ 1 $ 列。</span><span class="sxs-lookup"><span data-stu-id="ca90a-237">All the matrices we consider will either be square matrices, where the number of rows and columns are equal, or vectors, which corresponds to only $1$ column.</span></span> <span data-ttu-id="ca90a-238">一个特殊的正方形矩阵是表示的[*标识矩阵*](https://en.wikipedia.org/wiki/Identity_matrix)， $ \boldone $ 它的所有对角线元素都等于 $ 1， $ 剩余元素等于 $ 0 $ ：</span><span class="sxs-lookup"><span data-stu-id="ca90a-238">One special square matrix is the [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix), denoted $\boldone$, which has all its diagonal elements equal to $1$ and the remaining elements equal to $0$:</span></span>

$$\boldone=\begin{bmatrix}
<span data-ttu-id="ca90a-239">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-239">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="ca90a-240">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-240">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span></span>
~~<span data-ttu-id="ca90a-241"> \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-241"> \ddots\\\\</span></span>
<span data-ttu-id="ca90a-242">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix} 。$$</span><span class="sxs-lookup"><span data-stu-id="ca90a-242">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix}.$$</span></span>

<span data-ttu-id="ca90a-243">对于正方形矩阵 $ a $ ，我们说， $ $ 如果 AB BA，矩阵 B 是[*相反*](https://en.wikipedia.org/wiki/Invertible_matrix)的 $ = = \boldone $ 。</span><span class="sxs-lookup"><span data-stu-id="ca90a-243">For a square matrix $A$, we say a matrix $B$ is its [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) if $AB = BA = \boldone$.</span></span> <span data-ttu-id="ca90a-244">矩阵的逆矩阵不需要存在，但如果它存在，则它是唯一的，并 $ 将其表示为 ^ { -1 } $ 。</span><span class="sxs-lookup"><span data-stu-id="ca90a-244">The inverse of a matrix need not exist, but when it exists it is unique and we denote it $A^{-1}$.</span></span> 

<span data-ttu-id="ca90a-245">对于任何矩阵 $ m $ ，m 的 adjoint 或共轭转 $ 置 $ 为 matrix $ N， $ 以便 $ N_ { ij } = M_ { ji } ^ \* $ 。</span><span class="sxs-lookup"><span data-stu-id="ca90a-245">For any matrix $M$, the adjoint or conjugate transpose of $M$ is a matrix $N$ such that $N_{ij} = M_{ji}^\*$.</span></span> <span data-ttu-id="ca90a-246">M 的 adjoint $ $ 通常表示为 $ m ^ \dagger $ 。</span><span class="sxs-lookup"><span data-stu-id="ca90a-246">The adjoint of $M$ is usually denoted $M^\dagger$.</span></span> <span data-ttu-id="ca90a-247">$ $ 如果为[*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) $ UU ^ \dagger = u ^ \dagger u = \boldone $ 或等效 $ 项 u ^ { -1 } = u ^ \dagger $ ，则假设矩阵 U 为单一矩阵。</span><span class="sxs-lookup"><span data-stu-id="ca90a-247">We say a matrix $U$ is [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) if $UU^\dagger = U^\dagger U = \boldone$ or equivalently, $U^{-1} = U^\dagger$.</span></span>  <span data-ttu-id="ca90a-248">单一矩阵的最重要的属性可能是它们保留向量的标准。</span><span class="sxs-lookup"><span data-stu-id="ca90a-248">Perhaps the most important property of unitary matrices is that they preserve the norm of a vector.</span></span>  <span data-ttu-id="ca90a-249">出现这种情况的原因是</span><span class="sxs-lookup"><span data-stu-id="ca90a-249">This happens because</span></span> 

$$<span data-ttu-id="ca90a-250">\langlev、v \rangle = v ^ \dagger v = v ^ \dagger u ^ { -1 } U v = v ^ \dagger u ^ \dagger u v = \langle u v、u v \rangle 。$$</span><span class="sxs-lookup"><span data-stu-id="ca90a-250">\langle v,v \rangle=v^\dagger v = v^\dagger U^{-1} U v = v^\dagger U^\dagger U v = \langle U v, U v\rangle.$$</span></span>  

<span data-ttu-id="ca90a-251">$ $ 如果[*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) $ m m ^，则认为矩阵 M 是 Hermitian 的 = \dagger $ 。</span><span class="sxs-lookup"><span data-stu-id="ca90a-251">A matrix $M$ is said to be [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) if $M=M^\dagger$.</span></span>

<span data-ttu-id="ca90a-252">最后， [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (或 Kronecker product) 2 个2个矩阵，大小为 $ p q 的2个矩阵 $ $ \times $ ，第 n 个大小 $ $ 为 p q，为大小为 $ \times $ $ = \otimes $ 的 $ mp \times nq $ ， $ 并 $ $ 按如下所示从 M 和 n 获取 $ ：</span><span class="sxs-lookup"><span data-stu-id="ca90a-252">Finally, the [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (or Kronecker product) of two matrices $M$ of size $m\times n$ and $N$ of size $p \times q$ is a larger matrix $P=M\otimes N$ of size $mp \times nq$, and is obtained from $M$ and $N$ as follows:</span></span>

\begin{align}
    <span data-ttu-id="ca90a-253">M \otimes N&=</span><span class="sxs-lookup"><span data-stu-id="ca90a-253">M \otimes N &=</span></span>
    \begin{bmatrix}
        <span data-ttu-id="ca90a-254">M_ { 11 } ~~ \cdots ~~ M_ { 1n }\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-254">M_{11} ~~ \cdots ~~ M_{1n} \\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="ca90a-255">M_ { m1 } ~~ \cdots ~~ M_ { mn  }</span><span class="sxs-lookup"><span data-stu-id="ca90a-255">M_{m1}  ~~ \cdots ~~ M_{mn}</span></span>
    \end{bmatrix}
    \otimes
    \begin{bmatrix}
        <span data-ttu-id="ca90a-256">N_ { 11 } ~~ \cdots ~~ N_ { 1q  }\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-256">N_{11}  ~~ \cdots ~~ N_{1q}\\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="ca90a-257">N_ { p1 } ~~ \cdots ~~ N_ { pq}</span><span class="sxs-lookup"><span data-stu-id="ca90a-257">N_{p1} ~~ \cdots ~~ N_{pq}</span></span>
    \end{bmatrix}\\\\
    &=
    \begin{bmatrix}
        <span data-ttu-id="ca90a-258">M_ { 11 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq } \end{bmatrix} ~~ \cdots  ~~</span><span class="sxs-lookup"><span data-stu-id="ca90a-258">M_{11} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~</span></span> 
        <span data-ttu-id="ca90a-259">M_ { 1n } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq }  \end{bmatrix}\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-259">M_{1n} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}\\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="ca90a-260">M_ { m1 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq } \end{bmatrix} ~~ \cdots  ~~</span><span class="sxs-lookup"><span data-stu-id="ca90a-260">M_{m1} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~</span></span> 
        <span data-ttu-id="ca90a-261">M_ { mn } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq }  \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="ca90a-261">M_{mn} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}</span></span>
    \end{bmatrix}<span data-ttu-id="ca90a-262">.</span><span class="sxs-lookup"><span data-stu-id="ca90a-262">.</span></span>
\end{align}

<span data-ttu-id="ca90a-263">下面的示例对此进行了更好的演示：</span><span class="sxs-lookup"><span data-stu-id="ca90a-263">This is better demonstrated with some examples:</span></span>

$$
    \begin{bmatrix}
        <span data-ttu-id="ca90a-264">a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}=</span><span class="sxs-lookup"><span data-stu-id="ca90a-264">a \\\\ b  \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} =</span></span>
    \begin{bmatrix}
        <span data-ttu-id="ca90a-265">\begin{bmatrix}c \\\\ d \\\\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="ca90a-265">a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}</span></span>
        \\\\<span data-ttu-id="ca90a-266">[1.5 em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="ca90a-266">[1.5em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span></span>
    \end{bmatrix}
    =<span data-ttu-id="ca90a-267">\begin{bmatrix}a c a \\\\ d \\\\ a e \\\\ b c \\\\ b d \\\\\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="ca90a-267"> \begin{bmatrix} a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end{bmatrix}</span></span>
$$

<span data-ttu-id="ca90a-268">和</span><span class="sxs-lookup"><span data-stu-id="ca90a-268">and</span></span>

$$
    \begin{bmatrix}
        <span data-ttu-id="ca90a-269">a b \\\\ c d\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="ca90a-269">a\ b \\\\ c\ d \end{bmatrix}</span></span>
    \otimes 
    \begin{bmatrix}
        <span data-ttu-id="ca90a-270">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="ca90a-270">e\ f\\\\g\ h \end{bmatrix}</span></span>
     =
    \begin{bmatrix}
    <span data-ttu-id="ca90a-271">的\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="ca90a-271">a\begin{bmatrix}</span></span>
    <span data-ttu-id="ca90a-272">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="ca90a-272">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="ca90a-273">b\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="ca90a-273">b\begin{bmatrix}</span></span>
    <span data-ttu-id="ca90a-274">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="ca90a-274">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    \\\\<span data-ttu-id="ca90a-275">[1em] c\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="ca90a-275">[1em] c\begin{bmatrix}</span></span>
    <span data-ttu-id="ca90a-276">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="ca90a-276">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="ca90a-277">2-d\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="ca90a-277">d\begin{bmatrix}</span></span>
    <span data-ttu-id="ca90a-278">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="ca90a-278">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    \end{bmatrix}
    =
    \begin{bmatrix}
    <span data-ttu-id="ca90a-279">ae \ af \ \ bf\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-279">ae\ af\ be\ bf \\\\</span></span>
    <span data-ttu-id="ca90a-280">ag \ ah \ bg \ bh\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-280">ag\ ah\ bg\ bh \\\\</span></span>
    <span data-ttu-id="ca90a-281">ce \ cf \ de \ df\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-281">ce\ cf\ de\ df \\\\</span></span>
    <span data-ttu-id="ca90a-282">cg \ ch \ dg \ dh \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="ca90a-282">cg\ ch\ dg\ dh \end{bmatrix}.</span></span>
$$

<span data-ttu-id="ca90a-283">围绕 tensor 产品的最终有用的符号约定是：对于任何 vector $ v $ 或 matrix $ m $ ， $ v ^ { \otimes n } $ 或 $ M ^ { \otimes n } $ 对于 $ n $ 折重复 tensor 产品而言是短期的。</span><span class="sxs-lookup"><span data-stu-id="ca90a-283">A final useful notational convention surrounding tensor products is that, for any vector $v$ or matrix $M$, $v^{\otimes n}$ or $M^{\otimes n}$ is short hand for an $n$-fold repeated tensor product.</span></span>  <span data-ttu-id="ca90a-284">例如：</span><span class="sxs-lookup"><span data-stu-id="ca90a-284">For example:</span></span>

\begin{align}
&<span data-ttu-id="ca90a-285">\begin{bmatrix}1 \\\\ 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ， \qquad \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ 0 0 0 \\\\ \\\\ 0 \end{bmatrix} ， \qquad \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ -1 \\\\ -1 \\\\ 1 \end{bmatrix} ，\\\\</span><span class="sxs-lookup"><span data-stu-id="ca90a-285">\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ -1 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ -1 \\\\-1 \\\\1 \end{bmatrix}, \\\\</span></span>
  &<span data-ttu-id="ca90a-286">\begin{bmatrix}0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ， \qquad \begin{bmatrix} 0 & 1 \\\\ 1 & 0 2 0 0 0 0 \end{bmatrix} ^ { \otimes } = \begin{bmatrix} & & & \\\\ & 0 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 1 & 0 & & \end{bmatrix} 0 0。</span><span class="sxs-lookup"><span data-stu-id="ca90a-286">\begin{bmatrix}  0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 1}= \begin{bmatrix}  0& 1 \\\\ 1& 0    \end{bmatrix},    \qquad\begin{bmatrix}   0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 2}= \begin{bmatrix} 0 &0&0&1 \\\\ 0 &0&1&0 \\\\ 0 &1&0&0\\\\ 1 &0&0&0\end{bmatrix}.</span></span>
\end{align}
