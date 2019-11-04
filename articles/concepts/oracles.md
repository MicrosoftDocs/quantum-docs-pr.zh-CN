---
title: 量程 oracles |Microsoft Docs
description: 量程 oracles
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
ms.topic: article
ms.openlocfilehash: 96949b371a3a5a1135d624690933a48ea0214a2e
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184706"
---
# <a name="quantum-oracles"></a><span data-ttu-id="dfef9-103">量程 Oracles</span><span class="sxs-lookup"><span data-stu-id="dfef9-103">Quantum Oracles</span></span>

<span data-ttu-id="dfef9-104">Oracle $O $ 是一个 "黑色框" 操作，用于作为其他算法的输入。</span><span class="sxs-lookup"><span data-stu-id="dfef9-104">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="dfef9-105">通常，此类操作使用传统函数定义 $f： \\{0，1\\} ^ n \to \\{0，1\\} ^ m $，这将采用 $n $ 位二进制输入，并生成 $m $ 位二进制输出。</span><span class="sxs-lookup"><span data-stu-id="dfef9-105">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="dfef9-106">为此，请考虑使用特定的二进制输入 $x = （x_{0}，x_{1}，\dots ..，x_ {n-1}） $。</span><span class="sxs-lookup"><span data-stu-id="dfef9-106">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="dfef9-107">我们可以将 qubit 状态标记为 $ \ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes $。</span><span class="sxs-lookup"><span data-stu-id="dfef9-107">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="dfef9-108">我们可能首先尝试定义 $O $，$O \ket{x} = \ket{f （x）} $，但这会有几个问题。</span><span class="sxs-lookup"><span data-stu-id="dfef9-108">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="dfef9-109">首先，$f $ 可能会有不同的输入和输出大小（$n \ne m $），因此应用 $O $ 将更改寄存器中的 qubits 数。</span><span class="sxs-lookup"><span data-stu-id="dfef9-109">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="dfef9-110">其次，即使 $n = m $，函数也可能不可逆：如果 $f （x） = f （y） $ （对于某些 $x \ne y $），则 $O \ket{x} = O\ket {y} $ 但 $O ^ \dagger O\ket {x} \ne O ^ \dagger O\ket {y} $。</span><span class="sxs-lookup"><span data-stu-id="dfef9-110">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="dfef9-111">这意味着我们无法构造 adjoint 操作 $O ^ \dagger $，oracles 必须为其定义 adjoint。</span><span class="sxs-lookup"><span data-stu-id="dfef9-111">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="dfef9-112">通过其对计算基础状态的影响来定义 oracle</span><span class="sxs-lookup"><span data-stu-id="dfef9-112">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="dfef9-113">我们可以通过引入 $m $ qubits 的第二个寄存器来处理这两个问题。</span><span class="sxs-lookup"><span data-stu-id="dfef9-113">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="dfef9-114">然后，我们将定义 oracle 对所有计算基础状态的影响：对于所有 $x \in \\{0，1\\} ^ n $ 和 $y \in \\{0，1\\} ^ m $，</span><span class="sxs-lookup"><span data-stu-id="dfef9-114">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

<span data-ttu-id="dfef9-115">$ $ \begin{align} O （\ket{x} \otimes \ket{y}） = \ket{x} \otimes \ket{y \oplus f （x）}。</span><span class="sxs-lookup"><span data-stu-id="dfef9-115">$$ \begin{align} O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="dfef9-116">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="dfef9-116">\end{align} $$</span></span>

<span data-ttu-id="dfef9-117">现在，按构造 $O = O ^ \dagger $，因此我们解决了上述两个问题。</span><span class="sxs-lookup"><span data-stu-id="dfef9-117">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
> <span data-ttu-id="dfef9-118">若要查看 $O = O ^ {\dagger} $，请注意 $O ^ 2 = \boldone $，因为 $a \oplus b \oplus b = a 表示所有 $a，b \in \{0，1\}$。</span><span class="sxs-lookup"><span data-stu-id="dfef9-118">To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
> <span data-ttu-id="dfef9-119">因此，$O \ket{x} \ket{y \oplus f （x）} = \ket{x} \ket{y \oplus f （x） \oplus f （x）} = \ket{x} \ket{y} $。</span><span class="sxs-lookup"><span data-stu-id="dfef9-119">As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="dfef9-120">重要的是，以这种方式为每个计算基础状态 $ \ket{x}\ket{y} $ 定义 oracle 时，还会定义 $O $ 如何处理任何其他状态。</span><span class="sxs-lookup"><span data-stu-id="dfef9-120">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="dfef9-121">这是因为 $O $ （与所有量程操作一样）都是线性处于其作用的状态。</span><span class="sxs-lookup"><span data-stu-id="dfef9-121">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="dfef9-122">例如，假设 Hadamard 操作由 $H \ket{0} = \ket{+} $ 和 $H \ket{1} = \ket{-}$ 定义。</span><span class="sxs-lookup"><span data-stu-id="dfef9-122">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="dfef9-123">如果希望了解 $H $ 如何处理 $ \ket{+} $，可以使用 $H $ 是线性的，</span><span class="sxs-lookup"><span data-stu-id="dfef9-123">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

<span data-ttu-id="dfef9-124">$ $ \begin{align} H\ket {+} & = \frac{1}{\sqrt{2}} H （\ket{0} + \ket{1}） = \frac{1}{\sqrt{2}} （H\ket{0} + H\ket{1}） \\\\ & = \frac{1}{\sqrt{2}} （\票证 {+} + \ket{-}） = \frac12 （\ket{0} + \ket{1} + \ket{0}-\ket{1}） = \ket{0}。</span><span class="sxs-lookup"><span data-stu-id="dfef9-124">$$ \begin{align} H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\ & = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
<span data-ttu-id="dfef9-125">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="dfef9-125">\end{align} $$</span></span>

<span data-ttu-id="dfef9-126">如果定义 oracle $O $，则可以同样使用 $n + m $ qubits 上的任何状态 $ \ket{\psi} $ 都可以编写为</span><span class="sxs-lookup"><span data-stu-id="dfef9-126">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

<span data-ttu-id="dfef9-127">$ $ \begin{align} \ket{\psi} & = \sum_{x \in \\{0，1\\} ^ n，y \in \\{0，1\\} ^ m} \alpha （x，y） \ket{x} \ket{y} \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="dfef9-127">$$ \begin{align} \ket{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \end{align} $$</span></span>

<span data-ttu-id="dfef9-128">其中 $ \alpha： \\{0，1\\} ^ n \times \\{0，1\\} ^ m \to \mathbb{C} $ 表示状态 $ \ket{\psi} $ 的系数。</span><span class="sxs-lookup"><span data-stu-id="dfef9-128">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="dfef9-129">因此</span><span class="sxs-lookup"><span data-stu-id="dfef9-129">Thus,</span></span>

<span data-ttu-id="dfef9-130">$ $ \begin{align} O \ket{\psi} & = O \sum_{x \in \\{0，1\\} ^ n，y \in \\{0，1\\} ^ m} \alpha （x，y） \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0，1\\} ^ n，y \in \\{0，1\\} ^ m} \alpha （x，y） O \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0，1\\} ^ n，y \in \\{0，1\\} ^ m} \alpha （x，y） \ket{x} \ket{y \oplus f （x）}。</span><span class="sxs-lookup"><span data-stu-id="dfef9-130">$$ \begin{align} O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="dfef9-131">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="dfef9-131">\end{align} $$</span></span>

## <a name="phase-oracles"></a><span data-ttu-id="dfef9-132">阶段 oracles</span><span class="sxs-lookup"><span data-stu-id="dfef9-132">Phase oracles</span></span>
<span data-ttu-id="dfef9-133">此外，我们还可以通过应用基于输入 $O $ 的_阶段_，将 $f $ 编码为 oracle $O $。</span><span class="sxs-lookup"><span data-stu-id="dfef9-133">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$.</span></span>
<span data-ttu-id="dfef9-134">例如，我们可能会定义 $O $，$ $ \begin{align} O \ket{x} = （-1） ^ {f （x）} \ket{x}。</span><span class="sxs-lookup"><span data-stu-id="dfef9-134">For instance, we might define $O$ such that $$ \begin{align} O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
<span data-ttu-id="dfef9-135">\end{align} $ $ 如果某阶段 oracle 最初在计算基础状态 $ \ket{x} $ 中操作，则此阶段是全局阶段，因此不能观察到。</span><span class="sxs-lookup"><span data-stu-id="dfef9-135">\end{align} $$ If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="dfef9-136">但如果应用于 superposition 或作为受控操作，此类 oracle 可能是非常强大的资源。</span><span class="sxs-lookup"><span data-stu-id="dfef9-136">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="dfef9-137">例如，假设有一个阶段 orcale $O _f $ for qubit 函数 $f $。</span><span class="sxs-lookup"><span data-stu-id="dfef9-137">For example, consider a phase orcale $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="dfef9-138">然后，$ $ \begin{align} O_f \ket{+} & = O_f （\ket{0} + \ket{1}）/\sqrt{2} \\\\ & = （（-1） ^ {f （0）} \ket{0} + （-1） ^ {f （1）} \ket{1}）/\sqrt{2} \\\\ & = （-1） ^ {f （0）} （\ket{0} + （-1） ^ {f （1）-f （0）} \ket{1}）/\sqrt{2} \\\\ & = （-1） ^ {f （0）} Z ^ {f （0）-f （1）} \ket{+}。</span><span class="sxs-lookup"><span data-stu-id="dfef9-138">Then, $$ \begin{align} O_f \ket{+} & = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\ & = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
<span data-ttu-id="dfef9-139">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="dfef9-139">\end{align} $$</span></span>

<span data-ttu-id="dfef9-140">更常见的情况是，oracles 的两个视图都可以扩大了，以表示返回实数而不只是一位的传统函数。</span><span class="sxs-lookup"><span data-stu-id="dfef9-140">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="dfef9-141">选择实现 oracle 的最佳方式很大程度上取决于 oracle 在给定算法中的使用方式。</span><span class="sxs-lookup"><span data-stu-id="dfef9-141">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="dfef9-142">例如， [Deutsch-Jozsa 算法](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm)依赖于第一种方式实现的 oracle，而[Grover 的算法](https://en.wikipedia.org/wiki/Grover's_algorithm)依赖于第二个方法实现的 oracle。</span><span class="sxs-lookup"><span data-stu-id="dfef9-142">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="dfef9-143">有关更多详细信息，我们建议在[Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465)中进行讨论。</span><span class="sxs-lookup"><span data-stu-id="dfef9-143">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
