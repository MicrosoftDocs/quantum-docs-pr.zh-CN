---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: fb7aa5af8f3eb07399e0d2dd2d50723f4e6b169a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855528"
---
# <a name="decomposedon-function"></a><span data-ttu-id="26c68-102">DecomposedOn 函数</span><span class="sxs-lookup"><span data-stu-id="26c68-102">DecomposedOn function</span></span>

<span data-ttu-id="26c68-103">命名空间 [：](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="26c68-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="26c68-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="26c68-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="26c68-105">对变量分解</span><span class="sxs-lookup"><span data-stu-id="26c68-105">Decomposes a permutation on a variable</span></span>

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a><span data-ttu-id="26c68-106">说明</span><span class="sxs-lookup"><span data-stu-id="26c68-106">Description</span></span>

<span data-ttu-id="26c68-107">给定排列 $ \pi $ (`perm`) ，$i $ () 的索引 `index` ，此方法返回三个排列 $ ( # A5 \ pi_l，\ pi_r) ，\pi ' ) $，以使 $ \ pi_l $ 和 $ \ pi_r $ 的图像不会在其元素中的索引（而不是 $ \pi ' $ 的）中更改其元素中的位。</span><span class="sxs-lookup"><span data-stu-id="26c68-107">Given a permutation $\pi$ (`perm`) and an index $i$ (`index`), this method returns three permutations $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>

## <a name="input"></a><span data-ttu-id="26c68-108">输入</span><span class="sxs-lookup"><span data-stu-id="26c68-108">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="26c68-109">永久状态： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="26c68-109">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="index--int"></a><span data-ttu-id="26c68-110">索引： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="26c68-110">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--intintint"></a><span data-ttu-id="26c68-111">Output： ( # B1 [Int](xref:microsoft.quantum.lang-ref.int)[]，[int](xref:microsoft.quantum.lang-ref.int)[] ) ，[int](xref:microsoft.quantum.lang-ref.int)[] ) </span><span class="sxs-lookup"><span data-stu-id="26c68-111">Output : (([Int](xref:microsoft.quantum.lang-ref.int)[],[Int](xref:microsoft.quantum.lang-ref.int)[]),[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>



## <a name="example"></a><span data-ttu-id="26c68-112">示例</span><span class="sxs-lookup"><span data-stu-id="26c68-112">Example</span></span>

<span data-ttu-id="26c68-113">假设输入为永久状态 = [0，2，3，5，7，1，4，6]，index = 0，则此函数将基于下表计算三个排列，其中 `perm` 使用组 A 中的元素和组 D 中的图像列出二进制表示法中的排列。 列列出位索引。</span><span class="sxs-lookup"><span data-stu-id="26c68-113">Assume that the input is perm = [0, 2, 3, 5, 7, 1, 4, 6] and index = 0, then this function computes three permutations based on the following table, which lists the permutation `perm` in binary notation with elements in group A and images in group D.  The columns list the bit indices.</span></span>

<span data-ttu-id="26c68-114">|  A |  B |  C |  D |</span><span class="sxs-lookup"><span data-stu-id="26c68-114">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="26c68-115">2 1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-115">2 1 0</span></span> | <span data-ttu-id="26c68-116">2 1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-116">2 1 0</span></span> | <span data-ttu-id="26c68-117">2 1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-117">2 1 0</span></span> | <span data-ttu-id="26c68-118">2 1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-118">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="26c68-119">0 0 0</span><span class="sxs-lookup"><span data-stu-id="26c68-119">0 0 0</span></span> |       |       | <span data-ttu-id="26c68-120">0 0 0</span><span class="sxs-lookup"><span data-stu-id="26c68-120">0 0 0</span></span> | <span data-ttu-id="26c68-121">0</span><span class="sxs-lookup"><span data-stu-id="26c68-121">0</span></span>
| <span data-ttu-id="26c68-122">0 0 1</span><span class="sxs-lookup"><span data-stu-id="26c68-122">0 0 1</span></span> |       |       | <span data-ttu-id="26c68-123">0 1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-123">0 1 0</span></span> | <span data-ttu-id="26c68-124">2</span><span class="sxs-lookup"><span data-stu-id="26c68-124">2</span></span>
| <span data-ttu-id="26c68-125">0 1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-125">0 1 0</span></span> |       |       | <span data-ttu-id="26c68-126">0 1 1</span><span class="sxs-lookup"><span data-stu-id="26c68-126">0 1 1</span></span> | <span data-ttu-id="26c68-127">3</span><span class="sxs-lookup"><span data-stu-id="26c68-127">3</span></span>
| <span data-ttu-id="26c68-128">0 1 1</span><span class="sxs-lookup"><span data-stu-id="26c68-128">0 1 1</span></span> |       |       | <span data-ttu-id="26c68-129">1 0 1</span><span class="sxs-lookup"><span data-stu-id="26c68-129">1 0 1</span></span> | <span data-ttu-id="26c68-130">5</span><span class="sxs-lookup"><span data-stu-id="26c68-130">5</span></span>
| <span data-ttu-id="26c68-131">1 0 0</span><span class="sxs-lookup"><span data-stu-id="26c68-131">1 0 0</span></span> |       |       | <span data-ttu-id="26c68-132">1 1 1</span><span class="sxs-lookup"><span data-stu-id="26c68-132">1 1 1</span></span> | <span data-ttu-id="26c68-133">7</span><span class="sxs-lookup"><span data-stu-id="26c68-133">7</span></span>
| <span data-ttu-id="26c68-134">1 0 1</span><span class="sxs-lookup"><span data-stu-id="26c68-134">1 0 1</span></span> |       |       | <span data-ttu-id="26c68-135">0 0 1</span><span class="sxs-lookup"><span data-stu-id="26c68-135">0 0 1</span></span> | <span data-ttu-id="26c68-136">1</span><span class="sxs-lookup"><span data-stu-id="26c68-136">1</span></span>
| <span data-ttu-id="26c68-137">1 1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-137">1 1 0</span></span> |       |       | <span data-ttu-id="26c68-138">1 0 0</span><span class="sxs-lookup"><span data-stu-id="26c68-138">1 0 0</span></span> | <span data-ttu-id="26c68-139">4</span><span class="sxs-lookup"><span data-stu-id="26c68-139">4</span></span>
| <span data-ttu-id="26c68-140">1 1 1</span><span class="sxs-lookup"><span data-stu-id="26c68-140">1 1 1</span></span> |       |       | <span data-ttu-id="26c68-141">1 1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-141">1 1 0</span></span> | <span data-ttu-id="26c68-142">6</span><span class="sxs-lookup"><span data-stu-id="26c68-142">6</span></span>

<span data-ttu-id="26c68-143">索引的所有值不等于 0 (= 索引) 从 A 复制到 B，从 D 复制到 C。</span><span class="sxs-lookup"><span data-stu-id="26c68-143">All values for indices not equal to 0 (= index) are copied from A to B and from D to C.</span></span>

<span data-ttu-id="26c68-144">|  A |  B |  C |  D |</span><span class="sxs-lookup"><span data-stu-id="26c68-144">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="26c68-145">2 1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-145">2 1 0</span></span> | <span data-ttu-id="26c68-146">2 1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-146">2 1 0</span></span> | <span data-ttu-id="26c68-147">2 1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-147">2 1 0</span></span> | <span data-ttu-id="26c68-148">2 1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-148">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="26c68-149">0 0 0</span><span class="sxs-lookup"><span data-stu-id="26c68-149">0 0 0</span></span> | <span data-ttu-id="26c68-150">0 0</span><span class="sxs-lookup"><span data-stu-id="26c68-150">0 0</span></span>   | <span data-ttu-id="26c68-151">0 0</span><span class="sxs-lookup"><span data-stu-id="26c68-151">0 0</span></span>   | <span data-ttu-id="26c68-152">0 0 0</span><span class="sxs-lookup"><span data-stu-id="26c68-152">0 0 0</span></span> |
| <span data-ttu-id="26c68-153">0 0 1</span><span class="sxs-lookup"><span data-stu-id="26c68-153">0 0 1</span></span> | <span data-ttu-id="26c68-154">0 0</span><span class="sxs-lookup"><span data-stu-id="26c68-154">0 0</span></span>   | <span data-ttu-id="26c68-155">0 1</span><span class="sxs-lookup"><span data-stu-id="26c68-155">0 1</span></span>   | <span data-ttu-id="26c68-156">0 1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-156">0 1 0</span></span> |
| <span data-ttu-id="26c68-157">0 1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-157">0 1 0</span></span> | <span data-ttu-id="26c68-158">0 1</span><span class="sxs-lookup"><span data-stu-id="26c68-158">0 1</span></span>   | <span data-ttu-id="26c68-159">0 1</span><span class="sxs-lookup"><span data-stu-id="26c68-159">0 1</span></span>   | <span data-ttu-id="26c68-160">0 1 1</span><span class="sxs-lookup"><span data-stu-id="26c68-160">0 1 1</span></span> |
| <span data-ttu-id="26c68-161">0 1 1</span><span class="sxs-lookup"><span data-stu-id="26c68-161">0 1 1</span></span> | <span data-ttu-id="26c68-162">0 1</span><span class="sxs-lookup"><span data-stu-id="26c68-162">0 1</span></span>   | <span data-ttu-id="26c68-163">1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-163">1 0</span></span>   | <span data-ttu-id="26c68-164">1 0 1</span><span class="sxs-lookup"><span data-stu-id="26c68-164">1 0 1</span></span> |
| <span data-ttu-id="26c68-165">1 0 0</span><span class="sxs-lookup"><span data-stu-id="26c68-165">1 0 0</span></span> | <span data-ttu-id="26c68-166">1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-166">1 0</span></span>   | <span data-ttu-id="26c68-167">1 1</span><span class="sxs-lookup"><span data-stu-id="26c68-167">1 1</span></span>   | <span data-ttu-id="26c68-168">1 1 1</span><span class="sxs-lookup"><span data-stu-id="26c68-168">1 1 1</span></span> |
| <span data-ttu-id="26c68-169">1 0 1</span><span class="sxs-lookup"><span data-stu-id="26c68-169">1 0 1</span></span> | <span data-ttu-id="26c68-170">1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-170">1 0</span></span>   | <span data-ttu-id="26c68-171">0 0</span><span class="sxs-lookup"><span data-stu-id="26c68-171">0 0</span></span>   | <span data-ttu-id="26c68-172">0 0 1</span><span class="sxs-lookup"><span data-stu-id="26c68-172">0 0 1</span></span> |
| <span data-ttu-id="26c68-173">1 1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-173">1 1 0</span></span> | <span data-ttu-id="26c68-174">1 1</span><span class="sxs-lookup"><span data-stu-id="26c68-174">1 1</span></span>   | <span data-ttu-id="26c68-175">1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-175">1 0</span></span>   | <span data-ttu-id="26c68-176">1 0 0</span><span class="sxs-lookup"><span data-stu-id="26c68-176">1 0 0</span></span> |
| <span data-ttu-id="26c68-177">1 1 1</span><span class="sxs-lookup"><span data-stu-id="26c68-177">1 1 1</span></span> | <span data-ttu-id="26c68-178">1 1</span><span class="sxs-lookup"><span data-stu-id="26c68-178">1 1</span></span>   | <span data-ttu-id="26c68-179">1 1</span><span class="sxs-lookup"><span data-stu-id="26c68-179">1 1</span></span>   | <span data-ttu-id="26c68-180">1 1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-180">1 1 0</span></span> |

<span data-ttu-id="26c68-181">接下来，将在块 B 中第0列处为第一个具有空索引的元素放置0，然后将1放置在 B 中，其中前缀与索引 0 0) 的其他行 (。</span><span class="sxs-lookup"><span data-stu-id="26c68-181">Next a 0 is placed for the first element with an empty index at column 0 in block B and then a 1 is placed in B where the prefix matches (in the first case the other row with indices 0 0).</span></span>
<span data-ttu-id="26c68-182">之后，在块 C 的同一行中添加一个1，然后在块 C 中将相应的前缀添加为0。 重复此过程，直到所有索引都放置在块 B 和 C 的第0列中。</span><span class="sxs-lookup"><span data-stu-id="26c68-182">Afterwards, a 1 is added in the same row in block C, and then a 0 for the corresponding prefix in block C.  This process is repeated, until all indices have been placed in column 0 in blocks B and C.</span></span>

<span data-ttu-id="26c68-183">|  A |  B |  C |  D |</span><span class="sxs-lookup"><span data-stu-id="26c68-183">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="26c68-184">2 1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-184">2 1 0</span></span> | <span data-ttu-id="26c68-185">2 1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-185">2 1 0</span></span> | <span data-ttu-id="26c68-186">2 1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-186">2 1 0</span></span> | <span data-ttu-id="26c68-187">2 1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-187">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="26c68-188">0 0 0</span><span class="sxs-lookup"><span data-stu-id="26c68-188">0 0 0</span></span> | <span data-ttu-id="26c68-189">0 0 0</span><span class="sxs-lookup"><span data-stu-id="26c68-189">0 0 0</span></span> | <span data-ttu-id="26c68-190">0 0 0</span><span class="sxs-lookup"><span data-stu-id="26c68-190">0 0 0</span></span> | <span data-ttu-id="26c68-191">0 0 0</span><span class="sxs-lookup"><span data-stu-id="26c68-191">0 0 0</span></span> |
| <span data-ttu-id="26c68-192">0 0 1</span><span class="sxs-lookup"><span data-stu-id="26c68-192">0 0 1</span></span> | <span data-ttu-id="26c68-193">0 0 1</span><span class="sxs-lookup"><span data-stu-id="26c68-193">0 0 1</span></span> | <span data-ttu-id="26c68-194">0 1 1</span><span class="sxs-lookup"><span data-stu-id="26c68-194">0 1 1</span></span> | <span data-ttu-id="26c68-195">0 1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-195">0 1 0</span></span> |
| <span data-ttu-id="26c68-196">0 1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-196">0 1 0</span></span> | <span data-ttu-id="26c68-197">0 1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-197">0 1 0</span></span> | <span data-ttu-id="26c68-198">0 1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-198">0 1 0</span></span> | <span data-ttu-id="26c68-199">0 1 1</span><span class="sxs-lookup"><span data-stu-id="26c68-199">0 1 1</span></span> |
| <span data-ttu-id="26c68-200">0 1 1</span><span class="sxs-lookup"><span data-stu-id="26c68-200">0 1 1</span></span> | <span data-ttu-id="26c68-201">0 1 1</span><span class="sxs-lookup"><span data-stu-id="26c68-201">0 1 1</span></span> | <span data-ttu-id="26c68-202">1 0 1</span><span class="sxs-lookup"><span data-stu-id="26c68-202">1 0 1</span></span> | <span data-ttu-id="26c68-203">1 0 1</span><span class="sxs-lookup"><span data-stu-id="26c68-203">1 0 1</span></span> |
| <span data-ttu-id="26c68-204">1 0 0</span><span class="sxs-lookup"><span data-stu-id="26c68-204">1 0 0</span></span> | <span data-ttu-id="26c68-205">1 0 0</span><span class="sxs-lookup"><span data-stu-id="26c68-205">1 0 0</span></span> | <span data-ttu-id="26c68-206">1 1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-206">1 1 0</span></span> | <span data-ttu-id="26c68-207">1 1 1</span><span class="sxs-lookup"><span data-stu-id="26c68-207">1 1 1</span></span> |
| <span data-ttu-id="26c68-208">1 0 1</span><span class="sxs-lookup"><span data-stu-id="26c68-208">1 0 1</span></span> | <span data-ttu-id="26c68-209">1 0 1</span><span class="sxs-lookup"><span data-stu-id="26c68-209">1 0 1</span></span> | <span data-ttu-id="26c68-210">0 0 1</span><span class="sxs-lookup"><span data-stu-id="26c68-210">0 0 1</span></span> | <span data-ttu-id="26c68-211">0 0 1</span><span class="sxs-lookup"><span data-stu-id="26c68-211">0 0 1</span></span> |
| <span data-ttu-id="26c68-212">1 1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-212">1 1 0</span></span> | <span data-ttu-id="26c68-213">1 1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-213">1 1 0</span></span> | <span data-ttu-id="26c68-214">1 0 0</span><span class="sxs-lookup"><span data-stu-id="26c68-214">1 0 0</span></span> | <span data-ttu-id="26c68-215">1 0 0</span><span class="sxs-lookup"><span data-stu-id="26c68-215">1 0 0</span></span> |
| <span data-ttu-id="26c68-216">1 1 1</span><span class="sxs-lookup"><span data-stu-id="26c68-216">1 1 1</span></span> | <span data-ttu-id="26c68-217">1 1 1</span><span class="sxs-lookup"><span data-stu-id="26c68-217">1 1 1</span></span> | <span data-ttu-id="26c68-218">1 1 1</span><span class="sxs-lookup"><span data-stu-id="26c68-218">1 1 1</span></span> | <span data-ttu-id="26c68-219">1 1 0</span><span class="sxs-lookup"><span data-stu-id="26c68-219">1 1 0</span></span> |

<span data-ttu-id="26c68-220">我们可以从表中读取三个新排列：</span><span class="sxs-lookup"><span data-stu-id="26c68-220">We can read three new permutations from the table:</span></span>

- <span data-ttu-id="26c68-221">$ \ pi_l $ 包含中的元素，B (左的图像) </span><span class="sxs-lookup"><span data-stu-id="26c68-221">$\pi_l$ with elements in A, images in B (left)</span></span>
- <span data-ttu-id="26c68-222">$ \ pi_r $ with D 中的元素，C 中的图像 (right) </span><span class="sxs-lookup"><span data-stu-id="26c68-222">$\pi_r$ with elements in D, images in C (right)</span></span>
- <span data-ttu-id="26c68-223">$ \pi $ with B 中的元素，C 中的图像 (余数) </span><span class="sxs-lookup"><span data-stu-id="26c68-223">$\pi'$  with elements in B, images in C (remainder)</span></span>

<span data-ttu-id="26c68-224">请注意，按设计位值不会更改索引1和2的 $ \ pi_l $ 和 $ \ pi_r $，并且索引0的 $ \ pi_ $ $ 中的位值不会发生更改。</span><span class="sxs-lookup"><span data-stu-id="26c68-224">Note that by design bit values do not change in $\pi_l$ and $\pi_r$ for indices 1 and 2, and bit values do not change for in $\pi_'$ for index 0.</span></span>  <span data-ttu-id="26c68-225">另请注意，$ \ pi_l $ 和 $ \ pi_r $ 必须是自反的。</span><span class="sxs-lookup"><span data-stu-id="26c68-225">Also note that $\pi_l$ and $\pi_r$ must be self-inverse.</span></span>

<span data-ttu-id="26c68-226">派生的和返回的排列包括： left = [0，1，2，3，4，5，6，7] right = [0，1，3，2，4，5，7，6] 余数 = [0，3，2，5，6，1，4，7]</span><span class="sxs-lookup"><span data-stu-id="26c68-226">The derived and returned permutations are: left      = [0, 1, 2, 3, 4, 5, 6, 7] right     = [0, 1, 3, 2, 4, 5, 7, 6] remainder = [0, 3, 2, 5, 6, 1, 4, 7]</span></span>