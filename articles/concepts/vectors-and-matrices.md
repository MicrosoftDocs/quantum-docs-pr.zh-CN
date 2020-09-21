---
<span data-ttu-id="a19b4-101">标题：量程计算说明中的矢量和矩阵：了解有关如何使用向量和矩阵的基本知识。</span><span class="sxs-lookup"><span data-stu-id="a19b4-101">title: Vectors and matrices in quantum computing description: Learn the basics of how to work with vectors and matrices.</span></span>
<span data-ttu-id="a19b4-102">author： QuantumWriter uid： benbra 毫秒。作者： v-毫秒。日期： 12/11/2017 ms. 主题：项目不是：</span><span class="sxs-lookup"><span data-stu-id="a19b4-102">author: QuantumWriter uid: microsoft.quantum.concepts.vectors ms.author: v-benbra ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="a19b4-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="a19b4-103">"Q#"</span></span>
- <span data-ttu-id="a19b4-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="a19b4-104">"$$v"</span></span>
- <span data-ttu-id="a19b4-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="a19b4-105">"$$"</span></span>
- <span data-ttu-id="a19b4-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="a19b4-106">"$$"</span></span>
- <span data-ttu-id="a19b4-107">"$"</span><span class="sxs-lookup"><span data-stu-id="a19b4-107">"$"</span></span>
- <span data-ttu-id="a19b4-108">"$"</span><span class="sxs-lookup"><span data-stu-id="a19b4-108">"$"</span></span>
- <span data-ttu-id="a19b4-109">"$"</span><span class="sxs-lookup"><span data-stu-id="a19b4-109">"$"</span></span>
- <span data-ttu-id="a19b4-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="a19b4-110">"$$"</span></span>
- <span data-ttu-id="a19b4-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="a19b4-111">"\cdots"</span></span>
- <span data-ttu-id="a19b4-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="a19b4-112">"bmatrix"</span></span>
- <span data-ttu-id="a19b4-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="a19b4-113">"\ddots"</span></span>
- <span data-ttu-id="a19b4-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="a19b4-114">"\equiv"</span></span>
- <span data-ttu-id="a19b4-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="a19b4-115">"\sum"</span></span>
- <span data-ttu-id="a19b4-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="a19b4-116">"\begin"</span></span>
- <span data-ttu-id="a19b4-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="a19b4-117">"\end"</span></span>
- <span data-ttu-id="a19b4-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="a19b4-118">"\sqrt"</span></span>
- <span data-ttu-id="a19b4-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="a19b4-119">"\otimes"</span></span>
- <span data-ttu-id="a19b4-120">"{"</span><span class="sxs-lookup"><span data-stu-id="a19b4-120">"{"</span></span>
- <span data-ttu-id="a19b4-121">"}"</span><span class="sxs-lookup"><span data-stu-id="a19b4-121">"}"</span></span>
- <span data-ttu-id="a19b4-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="a19b4-122">"\text"</span></span>
- <span data-ttu-id="a19b4-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="a19b4-123">"\phi"</span></span>
- <span data-ttu-id="a19b4-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="a19b4-124">"\kappa"</span></span>
- <span data-ttu-id="a19b4-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="a19b4-125">"\psi"</span></span>
- <span data-ttu-id="a19b4-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="a19b4-126">"\alpha"</span></span>
- <span data-ttu-id="a19b4-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="a19b4-127">"\beta"</span></span>
- <span data-ttu-id="a19b4-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="a19b4-128">"\gamma"</span></span>
- <span data-ttu-id="a19b4-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="a19b4-129">"\delta"</span></span>
- <span data-ttu-id="a19b4-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="a19b4-130">"\omega"</span></span>
- <span data-ttu-id="a19b4-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="a19b4-131">"\bra"</span></span>
- <span data-ttu-id="a19b4-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="a19b4-132">"\ket"</span></span>
- <span data-ttu-id="a19b4-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="a19b4-133">"\boldone"</span></span>
- <span data-ttu-id="a19b4-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="a19b4-134">"\\\\"</span></span>
- <span data-ttu-id="a19b4-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="a19b4-135">"\\"</span></span>
- <span data-ttu-id="a19b4-136">"="</span><span class="sxs-lookup"><span data-stu-id="a19b4-136">"="</span></span>
- <span data-ttu-id="a19b4-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="a19b4-137">"\frac"</span></span>
- <span data-ttu-id="a19b4-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="a19b4-138">"\text"</span></span>
- <span data-ttu-id="a19b4-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="a19b4-139">"\mapsto"</span></span>
- <span data-ttu-id="a19b4-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="a19b4-140">"\dagger"</span></span>
- <span data-ttu-id="a19b4-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="a19b4-141">"\to"</span></span>
- <span data-ttu-id="a19b4-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="a19b4-142">"\begin{cases}"</span></span>
- <span data-ttu-id="a19b4-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="a19b4-143">"\end{cases}"</span></span>
- <span data-ttu-id="a19b4-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="a19b4-144">"\operatorname"</span></span>
- <span data-ttu-id="a19b4-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="a19b4-145">"\braket"</span></span>
- <span data-ttu-id="a19b4-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="a19b4-146">"\id"</span></span>
- <span data-ttu-id="a19b4-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="a19b4-147">"\expect"</span></span>
- <span data-ttu-id="a19b4-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="a19b4-148">"\defeq"</span></span>
- <span data-ttu-id="a19b4-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="a19b4-149">"\variance"</span></span>
- <span data-ttu-id="a19b4-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="a19b4-150">"\dd"</span></span>
- <span data-ttu-id="a19b4-151">"&"</span><span class="sxs-lookup"><span data-stu-id="a19b4-151">"&"</span></span>
- <span data-ttu-id="a19b4-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="a19b4-152">"\begin{align}"</span></span>
- <span data-ttu-id="a19b4-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="a19b4-153">"\end{align}"</span></span>
- <span data-ttu-id="a19b4-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="a19b4-154">"\Lambda"</span></span>
- <span data-ttu-id="a19b4-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="a19b4-155">"\lambda"</span></span>
- <span data-ttu-id="a19b4-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="a19b4-156">"\Omega"</span></span>
- <span data-ttu-id="a19b4-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="a19b4-157">"\mathrm"</span></span>
- <span data-ttu-id="a19b4-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="a19b4-158">"\left"</span></span>
- <span data-ttu-id="a19b4-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="a19b4-159">"\right"</span></span>
- <span data-ttu-id="a19b4-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="a19b4-160">"\qquad"</span></span>
- <span data-ttu-id="a19b4-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="a19b4-161">"\times"</span></span>
- <span data-ttu-id="a19b4-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="a19b4-162">"\big"</span></span>
- <span data-ttu-id="a19b4-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="a19b4-163">"\langle"</span></span>
- <span data-ttu-id="a19b4-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="a19b4-164">"\rangle"</span></span>
- <span data-ttu-id="a19b4-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="a19b4-165">"\bigg"</span></span>
- <span data-ttu-id="a19b4-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="a19b4-166">"\Big"</span></span>
- <span data-ttu-id="a19b4-167">"|"</span><span class="sxs-lookup"><span data-stu-id="a19b4-167">"|"</span></span>
- <span data-ttu-id="a19b4-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="a19b4-168">"\mathbb"</span></span>
- <span data-ttu-id="a19b4-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="a19b4-169">"\vec"</span></span>
- <span data-ttu-id="a19b4-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="a19b4-170">"\in"</span></span>
- <span data-ttu-id="a19b4-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="a19b4-171">"\texttt"</span></span>
- <span data-ttu-id="a19b4-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="a19b4-172">"\ne"</span></span>
- <span data-ttu-id="a19b4-173">"<"</span><span class="sxs-lookup"><span data-stu-id="a19b4-173">"<"</span></span>
- <span data-ttu-id="a19b4-174">">"</span><span class="sxs-lookup"><span data-stu-id="a19b4-174">">"</span></span>
- <span data-ttu-id="a19b4-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="a19b4-175">"\leq"</span></span>
- <span data-ttu-id="a19b4-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="a19b4-176">"\geq"</span></span>
- <span data-ttu-id="a19b4-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="a19b4-177">"~~"</span></span>
- <span data-ttu-id="a19b4-178">"~"</span><span class="sxs-lookup"><span data-stu-id="a19b4-178">"~"</span></span>
- <span data-ttu-id="a19b4-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="a19b4-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="a19b4-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="a19b4-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="a19b4-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="a19b4-181">"\_"</span></span>

---

# <a name="vectors-and-matrices"></a><span data-ttu-id="a19b4-182">向量和矩阵</span><span class="sxs-lookup"><span data-stu-id="a19b4-182">Vectors and Matrices</span></span>

<span data-ttu-id="a19b4-183">熟悉矢量和矩阵对于了解量程计算至关重要。</span><span class="sxs-lookup"><span data-stu-id="a19b4-183">Some familiarity with vectors and matrices is essential to understand quantum computing.</span></span> <span data-ttu-id="a19b4-184">我们提供了以下简短简介，并建议读者阅读有关线性代数（如 *Strang、 (1993) 的标准引用。线性代数简介 () 。Wellesley、MA： Wellesley-剑桥按下* 或联机引用，如 [线性代数](http://joshua.smcvt.edu/linearalgebra/)。</span><span class="sxs-lookup"><span data-stu-id="a19b4-184">We provide a brief introduction below and interested readers are recommended to read a standard reference on linear algebra such as *Strang, G. (1993). Introduction to linear algebra (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* or an online reference such as [Linear Algebra](http://joshua.smcvt.edu/linearalgebra/).</span></span>

<span data-ttu-id="a19b4-185">列向量 (或只是 [*矢量*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $ v of $ dimension (或 size) $ n $ 为 $ n 复数的集合 $ (v_1 $ 、v_2、\ldots、v_n) $ 排列为一列：</span><span class="sxs-lookup"><span data-stu-id="a19b4-185">A column vector (or simply [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v$ of dimension (or size) $n$ is a collection of $n$ complex numbers $(v_1,v_2,\ldots,v_n)$ arranged as a column:</span></span>

<span data-ttu-id="a19b4-186">$$v =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a19b4-186">$$v =\begin{bmatrix}</span></span>
<span data-ttu-id="a19b4-187">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-187">v_1\\\\</span></span>
<span data-ttu-id="a19b4-188">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-188">v_2\\\\</span></span>
<span data-ttu-id="a19b4-189">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-189">\vdots\\\\</span></span>
<span data-ttu-id="a19b4-190">v_n \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="a19b4-190">v_n \end{bmatrix}$$</span></span>

<span data-ttu-id="a19b4-191">向量 v 的标准 $ $ 定义为 $ \sqrt { \sum \_ i i | \_ i i | ^ 2 } $ 。</span><span class="sxs-lookup"><span data-stu-id="a19b4-191">The norm of a vector $v$ is defined as $\sqrt{\sum\_i |v\_i|^2}$.</span></span> <span data-ttu-id="a19b4-192">矢量称为单位规范 (或如果其标准为1，则称为 [*单位矢量*](https://en.wikipedia.org/wiki/Unit_vector)) $ $ 。</span><span class="sxs-lookup"><span data-stu-id="a19b4-192">A vector is said to be of unit norm (or alternatively it is called a [*unit vector*](https://en.wikipedia.org/wiki/Unit_vector)) if its norm is $1$.</span></span> <span data-ttu-id="a19b4-193">向量 v 的[*adjoint*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ $ 表示 $ v ^ \dagger $ ，并定义为以下行向量 $ \* $ ，其中表示复数共轭。</span><span class="sxs-lookup"><span data-stu-id="a19b4-193">The [*adjoint of a vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v$ is denoted $v^\dagger$ and is defined to be the following row vector where $\*$ denotes the complex conjugate,</span></span>

<span data-ttu-id="a19b4-194">$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix} ^ \dagger = \begin{bmatrix} v_1 ^ \* & \cdots & v_n ^ \*\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="a19b4-194">$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix}^\dagger = \begin{bmatrix}v_1^\* & \cdots & v_n^\* \end{bmatrix}$$</span></span>

<span data-ttu-id="a19b4-195">将两个矢量相乘的最常见方法是通过 [*内部产品*](https://en.wikipedia.org/wiki/Inner_product_space)（也称为点积）。</span><span class="sxs-lookup"><span data-stu-id="a19b4-195">The most common way to multiply two vectors together is through the [*inner product*](https://en.wikipedia.org/wiki/Inner_product_space), also known as a dot product.</span></span>  <span data-ttu-id="a19b4-196">内部产品提供了一个向量的投影到另一个向量，这在描述如何将一个向量表达为其他更简单的向量的总和方面非常有用。</span><span class="sxs-lookup"><span data-stu-id="a19b4-196">The inner product gives the projection of one vector onto another and is invaluable in describing how to express one vector as a sum of other simpler vectors.</span></span>  <span data-ttu-id="a19b4-197">U 和 v 之间的内部积 $ $ $ $ ，表示 $ \left \langle u，v \right \rangle $ 定义为</span><span class="sxs-lookup"><span data-stu-id="a19b4-197">The inner product between $u$ and $v$, denoted $\left\langle u, v\right\rangle$ is defined as</span></span>

$$
<span data-ttu-id="a19b4-198">\langleu，v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } v_1 + \cdots + u \_ n ^ { \* } v \_ n。</span><span class="sxs-lookup"><span data-stu-id="a19b4-198">\langle u, v\rangle = u^\dagger v=u\_1^{\*} v_1 + \cdots + u\_n^{\*} v\_n.</span></span>
$$

<span data-ttu-id="a19b4-199">此表示法还允许将 vector v 的 $ 标准 $ 编写为 $ \sqrt { \langle v，v \rangle } $ 。</span><span class="sxs-lookup"><span data-stu-id="a19b4-199">This notation also allows the norm of a vector $v$ to be written as $\sqrt{\langle v, v\rangle}$.</span></span>

<span data-ttu-id="a19b4-200">我们可以将一个向量与数字 $ c 相乘 $ ，以形成一个新向量，其项乘以 $ c $ 。</span><span class="sxs-lookup"><span data-stu-id="a19b4-200">We can multiply a vector with a number $c$ to form a new vector whose entries are multiplied by $c$.</span></span> <span data-ttu-id="a19b4-201">我们还可以添加两个向量 $ u $ 和 v， $ $ 以形成新的向量，其项是 $ u $ 和 v 项的 $ 总和 $ 。</span><span class="sxs-lookup"><span data-stu-id="a19b4-201">We can also add two vectors $u$ and $v$ to form a new vector whose entries are the sum of the entries of $u$ and $v$.</span></span> <span data-ttu-id="a19b4-202">这些操作如下所示：</span><span class="sxs-lookup"><span data-stu-id="a19b4-202">These operations are depicted below:</span></span>

<span data-ttu-id="a19b4-203">$$\mathrm{如果为 } ~ u=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a19b4-203">$$\mathrm{If}~u =\begin{bmatrix}</span></span>
<span data-ttu-id="a19b4-204">u_1\\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-204">u_1\\\\</span></span>
<span data-ttu-id="a19b4-205">u_2\\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-205">u_2\\\\</span></span>
<span data-ttu-id="a19b4-206">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-206">\vdots\\\\</span></span>
<span data-ttu-id="a19b4-207">u_n \end{bmatrix} ~ \mathrm { 和}~</span><span class="sxs-lookup"><span data-stu-id="a19b4-207">u_n \end{bmatrix}~\mathrm{and}~</span></span>
<span data-ttu-id="a19b4-208">向量 =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a19b4-208">v =\begin{bmatrix}</span></span>
    <span data-ttu-id="a19b4-209">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-209">v_1\\\\</span></span>
    <span data-ttu-id="a19b4-210">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-210">v_2\\\\</span></span>
    <span data-ttu-id="a19b4-211">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-211">\vdots\\\\</span></span>
    <span data-ttu-id="a19b4-212">v_n \end{bmatrix} ， ~ \mathrm { 然后}~</span><span class="sxs-lookup"><span data-stu-id="a19b4-212">v_n \end{bmatrix},~\mathrm{then}~</span></span>
<span data-ttu-id="a19b4-213">au + bv =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a19b4-213">au+bv =\begin{bmatrix}</span></span>
<span data-ttu-id="a19b4-214">au_1 + bv_1\\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-214">au_1+bv_1\\\\</span></span>
<span data-ttu-id="a19b4-215">au_2 + bv_2\\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-215">au_2+bv_2\\\\</span></span>
<span data-ttu-id="a19b4-216">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-216">\vdots\\\\</span></span>
<span data-ttu-id="a19b4-217">au_n + bv_n \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="a19b4-217">au_n+bv_n \end{bmatrix}.</span></span>
$$

<span data-ttu-id="a19b4-218">大小[*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics))为 $ m n 的 \times 矩阵 $ 是 $ $ 按 $ m 行和 n 列排列的 mn 复数的集合，如下 $ $ $ 所示：</span><span class="sxs-lookup"><span data-stu-id="a19b4-218">A [*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) of size $m \times n$ is a collection of $mn$ complex numbers arranged in $m$ rows and $n$ columns as shown below:</span></span>

<span data-ttu-id="a19b4-219">$$年 =</span><span class="sxs-lookup"><span data-stu-id="a19b4-219">$$M =</span></span> 
\begin{bmatrix}
<span data-ttu-id="a19b4-220">M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1n}\\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-220">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\</span></span>
<span data-ttu-id="a19b4-221">M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2n}\\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-221">M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="a19b4-222">M_ { m1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { mn}\\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-222">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}\\\\</span></span>
<span data-ttu-id="a19b4-223">\end{bmatrix}.$$</span><span class="sxs-lookup"><span data-stu-id="a19b4-223">\end{bmatrix}.$$</span></span>

<span data-ttu-id="a19b4-224">请注意，维度 n 的 $ 矢量 $ 只是大小为 $ n 1 的 \times 矩阵 $ 。</span><span class="sxs-lookup"><span data-stu-id="a19b4-224">Note that a vector of dimension $n$ is simply a matrix of size $n \times 1$.</span></span> <span data-ttu-id="a19b4-225">对于向量，我们可以将矩阵与数字 c 相乘， $ $ 以获取一个新矩阵，其中每个条目都与 $ c 相乘 $ ，并且我们可以添加两个相同大小的矩阵，以生成一个新矩阵，其项是两个矩阵的相应项的总和。</span><span class="sxs-lookup"><span data-stu-id="a19b4-225">As with vectors, we can multiply a matrix with a number $c$ to obtain a new matrix where every entry is multiplied with $c$, and we can add two matrices of the same size to produce a new matrix whose entries are the sum of the respective entries of the two matrices.</span></span> 

## <a name="matrix-multiplication-and-tensor-products"></a><span data-ttu-id="a19b4-226">Matrix 乘法 and Tensor Products</span><span class="sxs-lookup"><span data-stu-id="a19b4-226">Matrix Multiplication and Tensor Products</span></span>

<span data-ttu-id="a19b4-227">我们还可以将 dimension m n 和 n 维度 n p 的两个矩阵相乘， $ $ $ \times $ $ $ $ \times $ 以获取 $ $ dimension m p 的新 matrix p， $ \times $ 如下所示：</span><span class="sxs-lookup"><span data-stu-id="a19b4-227">We can also multiply two matrices $M$ of dimension $m\times n$ and $N$ of dimension $n \times p$ to get a new matrix $P$ of dimension $m \times p$ as follows:</span></span>

\begin{align}
&\begin{bmatrix}
    <span data-ttu-id="a19b4-228">M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1n}\\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-228">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\</span></span>
    <span data-ttu-id="a19b4-229">M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2n}\\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-229">M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\</span></span>
    \ddots\\\\
    <span data-ttu-id="a19b4-230">M_ { m1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { mn}</span><span class="sxs-lookup"><span data-stu-id="a19b4-230">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}</span></span>
\end{bmatrix}
\begin{bmatrix}
<span data-ttu-id="a19b4-231">N_ { 11 } ~~ N_ { 12 } ~~ \cdots ~~ N_ { 1 p}\\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-231">N_{11} ~~ N_{12} ~~ \cdots ~~ N_{1p}\\\\</span></span>
<span data-ttu-id="a19b4-232">N_ { 21 } ~~ N_ { 22 } ~~ \cdots ~~ N_ { 2 p}\\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-232">N_{21} ~~ N_{22} ~~ \cdots ~~ N_{2p}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="a19b4-233">N_ { n1 } ~~ N_ { n2 } ~~ \cdots ~~ N_ { np}</span><span class="sxs-lookup"><span data-stu-id="a19b4-233">N_{n1} ~~ N_{n2} ~~ \cdots ~~ N_{np}</span></span>
\end{bmatrix}=\begin{bmatrix}
<span data-ttu-id="a19b4-234">P_ { 11 } ~~ P_ { 12 } ~~ \cdots ~~ P_ { 1 p}\\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-234">P_{11} ~~ P_{12} ~~ \cdots ~~ P_{1p}\\\\</span></span>
<span data-ttu-id="a19b4-235">P_ { 21 } ~~ P_ { 22 } ~~ \cdots ~~ P_ { 2 p}\\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-235">P_{21} ~~ P_{22} ~~ \cdots ~~ P_{2p}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="a19b4-236">P_ { m1 } ~~ P_ { m2 } ~~ \cdots ~~ P_ { mp}</span><span class="sxs-lookup"><span data-stu-id="a19b4-236">P_{m1} ~~ P_{m2} ~~ \cdots ~~ P_{mp}</span></span>
\end{bmatrix}
\end{align}

<span data-ttu-id="a19b4-237">其中，P 条目 $ $ $ P_ { ik } = \sum _j M_ { ij } N_ { jk } $ 。</span><span class="sxs-lookup"><span data-stu-id="a19b4-237">where the entries of $P$ are $P_{ik} = \sum_j M_{ij}N_{jk}$.</span></span> <span data-ttu-id="a19b4-238">例如，条目 $ P_ { 11 } $ 是 M 第一行的第一行的第一 $ 列， $ 第一列是 $ N $ 。请注意，由于矢量只是矩阵的一种特殊情况，因此此定义延伸到矩阵向量乘法。</span><span class="sxs-lookup"><span data-stu-id="a19b4-238">For example, the entry $P_{11}$ is the inner product of the first row of $M$ with the first column of $N$. Note that since a vector is simply a special case of a matrix, this definition extends to matrix-vector multiplication.</span></span> 

<span data-ttu-id="a19b4-239">我们考虑的所有矩阵均为方形矩阵，其中的行数和列数相等，或向量仅对应于 $ 1 $ 列。</span><span class="sxs-lookup"><span data-stu-id="a19b4-239">All the matrices we consider will either be square matrices, where the number of rows and columns are equal, or vectors, which corresponds to only $1$ column.</span></span> <span data-ttu-id="a19b4-240">一个特殊的正方形矩阵是表示的[*标识矩阵*](https://en.wikipedia.org/wiki/Identity_matrix)， $ \boldone $ 它的所有对角线元素都等于 $ 1， $ 剩余元素等于 $ 0 $ ：</span><span class="sxs-lookup"><span data-stu-id="a19b4-240">One special square matrix is the [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix), denoted $\boldone$, which has all its diagonal elements equal to $1$ and the remaining elements equal to $0$:</span></span>

$$\boldone=\begin{bmatrix}
<span data-ttu-id="a19b4-241">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-241">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="a19b4-242">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-242">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="a19b4-243">~~ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-243">~~ \ddots\\\\</span></span>
<span data-ttu-id="a19b4-244">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix} 。$$</span><span class="sxs-lookup"><span data-stu-id="a19b4-244">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix}.$$</span></span>

<span data-ttu-id="a19b4-245">对于正方形矩阵 $ a $ ，我们说， $ $ 如果 AB BA，矩阵 B 是[*相反*](https://en.wikipedia.org/wiki/Invertible_matrix)的 $ = = \boldone $ 。</span><span class="sxs-lookup"><span data-stu-id="a19b4-245">For a square matrix $A$, we say a matrix $B$ is its [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) if $AB = BA = \boldone$.</span></span> <span data-ttu-id="a19b4-246">矩阵的逆矩阵不需要存在，但如果它存在，则它是唯一的，并 $ 将其表示为 ^ { -1 } $ 。</span><span class="sxs-lookup"><span data-stu-id="a19b4-246">The inverse of a matrix need not exist, but when it exists it is unique and we denote it $A^{-1}$.</span></span> 

<span data-ttu-id="a19b4-247">对于任何矩阵 $ m $ ，m 的 adjoint 或共轭转 $ 置 $ 为 matrix $ N， $ 以便 $ N_ { ij } = M_ { ji } ^ \* $ 。</span><span class="sxs-lookup"><span data-stu-id="a19b4-247">For any matrix $M$, the adjoint or conjugate transpose of $M$ is a matrix $N$ such that $N_{ij} = M_{ji}^\*$.</span></span> <span data-ttu-id="a19b4-248">M 的 adjoint $ $ 通常表示为 $ m ^ \dagger $ 。</span><span class="sxs-lookup"><span data-stu-id="a19b4-248">The adjoint of $M$ is usually denoted $M^\dagger$.</span></span> <span data-ttu-id="a19b4-249">$ $ 如果为[*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) $ UU ^ \dagger = u ^ \dagger u = \boldone $ 或等效 $ 项 u ^ { -1 } = u ^ \dagger $ ，则假设矩阵 U 为单一矩阵。</span><span class="sxs-lookup"><span data-stu-id="a19b4-249">We say a matrix $U$ is [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) if $UU^\dagger = U^\dagger U = \boldone$ or equivalently, $U^{-1} = U^\dagger$.</span></span>  <span data-ttu-id="a19b4-250">单一矩阵的最重要的属性可能是它们保留向量的标准。</span><span class="sxs-lookup"><span data-stu-id="a19b4-250">Perhaps the most important property of unitary matrices is that they preserve the norm of a vector.</span></span>  <span data-ttu-id="a19b4-251">出现这种情况的原因是</span><span class="sxs-lookup"><span data-stu-id="a19b4-251">This happens because</span></span> 

<span data-ttu-id="a19b4-252">$$\langlev、v \rangle = v ^ \dagger v = v ^ \dagger u ^ { -1 } U v = v ^ \dagger u ^ \dagger u v = \langle u v、u v \rangle 。$$</span><span class="sxs-lookup"><span data-stu-id="a19b4-252">$$\langle v,v \rangle=v^\dagger v = v^\dagger U^{-1} U v = v^\dagger U^\dagger U v = \langle U v, U v\rangle.$$</span></span>  

<span data-ttu-id="a19b4-253">$ $ 如果[*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) $ m m ^，则认为矩阵 M 是 Hermitian 的 = \dagger $ 。</span><span class="sxs-lookup"><span data-stu-id="a19b4-253">A matrix $M$ is said to be [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) if $M=M^\dagger$.</span></span>

<span data-ttu-id="a19b4-254">最后， [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (或 Kronecker product) 2 个2个矩阵，大小为 $ p q 的2个矩阵 $ $ \times $ ，第 n 个大小 $ $ 为 p q，为大小为 $ \times $ $ = \otimes $ 的 $ mp \times nq $ ， $ 并 $ $ 按如下所示从 M 和 n 获取 $ ：</span><span class="sxs-lookup"><span data-stu-id="a19b4-254">Finally, the [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (or Kronecker product) of two matrices $M$ of size $m\times n$ and $N$ of size $p \times q$ is a larger matrix $P=M\otimes N$ of size $mp \times nq$, and is obtained from $M$ and $N$ as follows:</span></span>

\begin{align}
    <span data-ttu-id="a19b4-255">M \otimes N &=</span><span class="sxs-lookup"><span data-stu-id="a19b4-255">M \otimes N &=</span></span>
    \begin{bmatrix}
        <span data-ttu-id="a19b4-256">M_ { 11 } ~~ \cdots ~~ M_ { 1n }\\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-256">M_{11} ~~ \cdots ~~ M_{1n} \\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="a19b4-257">M_ { m1 } ~~ \cdots ~~ M_ { mn  }</span><span class="sxs-lookup"><span data-stu-id="a19b4-257">M_{m1}  ~~ \cdots ~~ M_{mn}</span></span>
    \end{bmatrix}
    \otimes
    \begin{bmatrix}
        <span data-ttu-id="a19b4-258">N_ { 11 } ~~ \cdots ~~ N_ { 1q  }\\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-258">N_{11}  ~~ \cdots ~~ N_{1q}\\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="a19b4-259">N_ { p1 } ~~ \cdots ~~ N_ { pq}</span><span class="sxs-lookup"><span data-stu-id="a19b4-259">N_{p1} ~~ \cdots ~~ N_{pq}</span></span>
    \end{bmatrix}\\\\
    &=
    \begin{bmatrix}
        <span data-ttu-id="a19b4-260">M_ { 11 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq } \end{bmatrix} ~~ \cdots  ~~</span><span class="sxs-lookup"><span data-stu-id="a19b4-260">M_{11} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~</span></span> 
        <span data-ttu-id="a19b4-261">M_ { 1n } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq }  \end{bmatrix}\\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-261">M_{1n} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}\\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="a19b4-262">M_ { m1 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq } \end{bmatrix} ~~ \cdots  ~~</span><span class="sxs-lookup"><span data-stu-id="a19b4-262">M_{m1} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~</span></span> 
        <span data-ttu-id="a19b4-263">M_ { mn } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq }  \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a19b4-263">M_{mn} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}</span></span>
    <span data-ttu-id="a19b4-264">\end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="a19b4-264">\end{bmatrix}.</span></span>
\end{align}

<span data-ttu-id="a19b4-265">下面的示例对此进行了更好的演示：</span><span class="sxs-lookup"><span data-stu-id="a19b4-265">This is better demonstrated with some examples:</span></span>

$$
    \begin{bmatrix}
        <span data-ttu-id="a19b4-266">a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}=</span><span class="sxs-lookup"><span data-stu-id="a19b4-266">a \\\\ b  \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} =</span></span>
    \begin{bmatrix}
        <span data-ttu-id="a19b4-267">\begin{bmatrix}c \\\\ d \\\\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a19b4-267">a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}</span></span>
        <span data-ttu-id="a19b4-268">\\\\[1.5 em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a19b4-268">\\\\[1.5em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span></span>
    \end{bmatrix}
    <span data-ttu-id="a19b4-269">=\begin{bmatrix}a c a \\\\ d \\\\ a e \\\\ b c \\\\ b d \\\\\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a19b4-269">= \begin{bmatrix} a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end{bmatrix}</span></span>
$$

<span data-ttu-id="a19b4-270">和</span><span class="sxs-lookup"><span data-stu-id="a19b4-270">and</span></span>

$$
    \begin{bmatrix}
        <span data-ttu-id="a19b4-271">a b \\\\ c d \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a19b4-271">a\ b \\\\ c\ d \end{bmatrix}</span></span>
    \otimes 
    \begin{bmatrix}
        <span data-ttu-id="a19b4-272">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a19b4-272">e\ f\\\\g\ h \end{bmatrix}</span></span>
     =
    \begin{bmatrix}
    <span data-ttu-id="a19b4-273">的\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a19b4-273">a\begin{bmatrix}</span></span>
    <span data-ttu-id="a19b4-274">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a19b4-274">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="a19b4-275">b\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a19b4-275">b\begin{bmatrix}</span></span>
    <span data-ttu-id="a19b4-276">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a19b4-276">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="a19b4-277">\\\\[1em] c\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a19b4-277">\\\\[1em] c\begin{bmatrix}</span></span>
    <span data-ttu-id="a19b4-278">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a19b4-278">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="a19b4-279">2-d\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a19b4-279">d\begin{bmatrix}</span></span>
    <span data-ttu-id="a19b4-280">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a19b4-280">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    \end{bmatrix}
    =
    \begin{bmatrix}
    <span data-ttu-id="a19b4-281">ae \ af \ \ bf \\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-281">ae\ af\ be\ bf \\\\</span></span>
    <span data-ttu-id="a19b4-282">ag \ ah \ bg \ bh \\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-282">ag\ ah\ bg\ bh \\\\</span></span>
    <span data-ttu-id="a19b4-283">ce \ cf \ de \ df \\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-283">ce\ cf\ de\ df \\\\</span></span>
    <span data-ttu-id="a19b4-284">cg \ ch \ dg \ dh \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="a19b4-284">cg\ ch\ dg\ dh \end{bmatrix}.</span></span>
$$

<span data-ttu-id="a19b4-285">围绕 tensor 产品的最终有用的符号约定是：对于任何 vector $ v $ 或 matrix $ m $ ， $ v ^ { \otimes n } $ 或 $ M ^ { \otimes n } $ 对于 $ n $ 折重复 tensor 产品而言是短期的。</span><span class="sxs-lookup"><span data-stu-id="a19b4-285">A final useful notational convention surrounding tensor products is that, for any vector $v$ or matrix $M$, $v^{\otimes n}$ or $M^{\otimes n}$ is short hand for an $n$-fold repeated tensor product.</span></span>  <span data-ttu-id="a19b4-286">例如：</span><span class="sxs-lookup"><span data-stu-id="a19b4-286">For example:</span></span>

\begin{align}
<span data-ttu-id="a19b4-287">&\begin{bmatrix}1 \\\\ 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ， \qquad \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ 0 0 0 \\\\ \\\\ 0 \end{bmatrix} ， \qquad \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ -1 \\\\ -1 \\\\ 1 \end{bmatrix} ，\\\\</span><span class="sxs-lookup"><span data-stu-id="a19b4-287">&\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ -1 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ -1 \\\\-1 \\\\1 \end{bmatrix}, \\\\</span></span>
  <span data-ttu-id="a19b4-288">&\begin{bmatrix}0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ， \qquad \begin{bmatrix} 0 & 1 \\\\ 1 & 0 2 0 0 0 0 \end{bmatrix} ^ { \otimes } = \begin{bmatrix} & & & \\\\ & 0 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 1 & 0 & & \end{bmatrix} 0 0。</span><span class="sxs-lookup"><span data-stu-id="a19b4-288">&\begin{bmatrix}  0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 1}= \begin{bmatrix}  0& 1 \\\\ 1& 0    \end{bmatrix},    \qquad\begin{bmatrix}   0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 2}= \begin{bmatrix} 0 &0&0&1 \\\\ 0 &0&1&0 \\\\ 0 &1&0&0\\\\ 1 &0&0&0\end{bmatrix}.</span></span>
\end{align}
