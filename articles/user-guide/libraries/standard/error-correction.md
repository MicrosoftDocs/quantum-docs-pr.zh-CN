---
title: '标准库中的错误更正 Q#'
description: '了解如何在程序中使用纠错代码， Q# 同时保护 qubits 的状态。'
author: QuantumWriter
uid: microsoft.quantum.libraries.error-correction
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 94251e185cea65c5fc08ed70d5fba9b7b19501e3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692033"
---
# <a name="error-correction"></a><span data-ttu-id="e614d-103">错误更正</span><span class="sxs-lookup"><span data-stu-id="e614d-103">Error Correction</span></span> #

## <a name="introduction"></a><span data-ttu-id="e614d-104">简介</span><span class="sxs-lookup"><span data-stu-id="e614d-104">Introduction</span></span> ##

<span data-ttu-id="e614d-105">在传统计算中，如果有一位要防范错误，通常可以通过重复数据位来用 *逻辑位* 来表示该位。</span><span class="sxs-lookup"><span data-stu-id="e614d-105">In classical computing, if one wants to protect a bit against errors, it can often suffice to represent that bit by a *logical bit* by repeating the data bit.</span></span>
<span data-ttu-id="e614d-106">例如，让 $ \overline {0} = $0 是数据位0的编码，其中使用标签0上面的一行来指示它是0状态中位的编码。</span><span class="sxs-lookup"><span data-stu-id="e614d-106">For instance, let $\overline{0} = 000$ be the encoding of the data bit 0, where we use the a line above the label 0 to indicate that it is an encoding of a bit in the 0 state.</span></span>
<span data-ttu-id="e614d-107">如果我们以类似的方式让 $ \overline {1} = $111，则我们有一个简单的重复代码，可以防止出现一位翻转错误。</span><span class="sxs-lookup"><span data-stu-id="e614d-107">If we similarly let $\overline{1} = 111$, then we have a simple repetition code that protects against any one bit flip error.</span></span>
<span data-ttu-id="e614d-108">也就是说，如果三个位中有任何一个进行了翻转，则可以通过使用大多数投票来恢复逻辑位的状态。</span><span class="sxs-lookup"><span data-stu-id="e614d-108">That is, if any of the three bits are flipped, then we can recover the state of the logical bit by taking a majority vote.</span></span>
<span data-ttu-id="e614d-109">尽管传统的纠错是一个非常丰富的主题，这一特定的示例 (我们建议不 [起毛的编码理论简介](https://www.springer.com/us/book/9783540641339)) ，上面的重复代码已指向保护量程信息的可能问题。</span><span class="sxs-lookup"><span data-stu-id="e614d-109">Though classical error correction is a much richer subject that this particular example (we recommend [Lint's introduction to coding theory](https://www.springer.com/us/book/9783540641339)), the repetition code above already points to a possible problem in protecting quantum information.</span></span>
<span data-ttu-id="e614d-110">也就是说，" [无克隆" 定理](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) 意味着如果我们测量每个单独的 qubit，并通过与上面的传统代码进行交叉投票，就会丢失我们尝试保护的准确信息。</span><span class="sxs-lookup"><span data-stu-id="e614d-110">Namely, the [no-cloning theorem](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) implies that if we measure each individual qubit and take a majority vote by analogy to classical code above, then we have lost the precise information that we are trying to protect.</span></span>

<span data-ttu-id="e614d-111">在量程设置中，我们会看到测量值有问题。</span><span class="sxs-lookup"><span data-stu-id="e614d-111">In the quantum setting, we will see that the measurement is problematic.</span></span> <span data-ttu-id="e614d-112">我们仍可以实现上述编码。</span><span class="sxs-lookup"><span data-stu-id="e614d-112">We can still implement the encoding above.</span></span>
<span data-ttu-id="e614d-113">这样做有助于了解我们如何将错误更正通用化到量程情况。</span><span class="sxs-lookup"><span data-stu-id="e614d-113">It is helpful to do so to see how we can generalize error correction to the quantum case.</span></span>
<span data-ttu-id="e614d-114">因此，让 $ \ket{\overline {0} } = \ket {000} = \ket {0} \otimes \ket {0} \otimes \ket {0} $，并让 $ \ket{\overline {1} } = \ket {111} $。</span><span class="sxs-lookup"><span data-stu-id="e614d-114">Thus, let $\ket{\overline{0}} = \ket{000} = \ket{0} \otimes \ket{0} \otimes \ket{0}$, and let $\ket{\overline{1}} = \ket{111}$.</span></span>
<span data-ttu-id="e614d-115">然后，按线性，为所有输入定义重复代码;例如，$ \ket{\overline{+}} = ( \ket{\overline {0} } + \ket{\overline {1} } ) /\sqrt {2} = ( \ket {000} + \ket {111}) /\sqrt {2} $。</span><span class="sxs-lookup"><span data-stu-id="e614d-115">Then, by linearity, we have defined our repetition code for all inputs; for instance, $\ket{\overline{+}} = (\ket{\overline{0}} + \ket{\overline{1}}) / \sqrt{2} = (\ket{000} + \ket{111}) / \sqrt{2}$.</span></span>
<span data-ttu-id="e614d-116">具体而言，在 qubit 中使用 _1 $ act $X 时，请注意，这两个分支中所需的更正精确 $X _1 $： $ $ \begin{align} X_1 \ket{\overline{+}} & = \frac {1} {\sqrt {2} } \left ( X_1 \ket {000} + X_1 \ket {111} \right) \\ \\ & = \frac {1} {\sqrt {2} } \left ( \ket {010} + \ket {101} \right) 。</span><span class="sxs-lookup"><span data-stu-id="e614d-116">In particular, letting a bit-flip error $X_1$ act on the middle qubit, we see that the correction needed in both branches is precisely $X_1$: $$ \begin{align} X_1 \ket{\overline{+}} & = \frac{1}{\sqrt{2}} \left( X_1 \ket{000} + X_1 \ket{111} \right) \\\\ & = \frac{1}{\sqrt{2}} \left( \ket{010} + \ket{101} \right).</span></span>
<span data-ttu-id="e614d-117">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="e614d-117">\end{align} $$</span></span>

<span data-ttu-id="e614d-118">若要查看我们如何确定这种情况，而无需测量我们尝试保护的状态，可以记下每个不同的位翻转错误对逻辑状态的操作：</span><span class="sxs-lookup"><span data-stu-id="e614d-118">To see how we can identify that this is the case without measuring the very state we are trying to protect, it is helpful to write down what each different bit flip error does to our logical states:</span></span>

| <span data-ttu-id="e614d-119">错误 $E $</span><span class="sxs-lookup"><span data-stu-id="e614d-119">Error $E$</span></span> | <span data-ttu-id="e614d-120">$E \ket{\overline {0} } $</span><span class="sxs-lookup"><span data-stu-id="e614d-120">$E\ket{\overline{0}}$</span></span> | <span data-ttu-id="e614d-121">$E \ket{\overline {1} } $</span><span class="sxs-lookup"><span data-stu-id="e614d-121">$E\ket{\overline{1}}$</span></span> |
| --- | --- | --- |
| <span data-ttu-id="e614d-122">$ \boldone $</span><span class="sxs-lookup"><span data-stu-id="e614d-122">$\boldone$</span></span> | <span data-ttu-id="e614d-123">$ \ket {000} $</span><span class="sxs-lookup"><span data-stu-id="e614d-123">$\ket{000}$</span></span> | <span data-ttu-id="e614d-124">$ \ket {111} $</span><span class="sxs-lookup"><span data-stu-id="e614d-124">$\ket{111}$</span></span> |
| <span data-ttu-id="e614d-125">$X_0$</span><span class="sxs-lookup"><span data-stu-id="e614d-125">$X_0$</span></span> | <span data-ttu-id="e614d-126">$ \ket {100} $</span><span class="sxs-lookup"><span data-stu-id="e614d-126">$\ket{100}$</span></span> | <span data-ttu-id="e614d-127">$ \ket {011} $</span><span class="sxs-lookup"><span data-stu-id="e614d-127">$\ket{011}$</span></span> |
| <span data-ttu-id="e614d-128">$X_1$</span><span class="sxs-lookup"><span data-stu-id="e614d-128">$X_1$</span></span> | <span data-ttu-id="e614d-129">$ \ket {010} $</span><span class="sxs-lookup"><span data-stu-id="e614d-129">$\ket{010}$</span></span> | <span data-ttu-id="e614d-130">$ \ket {101} $</span><span class="sxs-lookup"><span data-stu-id="e614d-130">$\ket{101}$</span></span> |
| <span data-ttu-id="e614d-131">$X_2$</span><span class="sxs-lookup"><span data-stu-id="e614d-131">$X_2$</span></span> | <span data-ttu-id="e614d-132">$ \ket {001} $</span><span class="sxs-lookup"><span data-stu-id="e614d-132">$\ket{001}$</span></span> | <span data-ttu-id="e614d-133">$ \ket {110} $</span><span class="sxs-lookup"><span data-stu-id="e614d-133">$\ket{110}$</span></span> |

<span data-ttu-id="e614d-134">为了保护我们正在编码的状态，我们需要能够区分三个错误，并将其从标识 $ \boldone $ 区分开来，而不区分 $ \ket{\overline {0} } $ 和 $ \ket{\overline {1} } $。</span><span class="sxs-lookup"><span data-stu-id="e614d-134">In order to protect the state that we're encoding, we need to be able to distinguish the three errors from each other and from the identity $\boldone$ without distinguishing between $\ket{\overline{0}}$ and $\ket{\overline{1}}$.</span></span>
<span data-ttu-id="e614d-135">例如，如果度量值为 $Z _0 $， {0} 则在无错误情况下，为 $ \ket{\overline} $ 和 $ \ket{\overline} $ 获取不同的结果 {1} ，以便折叠已编码状态。</span><span class="sxs-lookup"><span data-stu-id="e614d-135">For example, if we measure $Z_0$, we get a different result for $\ket{\overline{0}}$ and $\ket{\overline{1}}$ in the no-error case, so that collapses the encoded state.</span></span>
<span data-ttu-id="e614d-136">另一方面，请考虑在每个计算基础状态下测量 Z_1 $ $Z _0 的前两位的奇偶校验。</span><span class="sxs-lookup"><span data-stu-id="e614d-136">On the other hand, consider measuring $Z_0 Z_1$, the parity of the first two bits in each computational basis state.</span></span>
<span data-ttu-id="e614d-137">回忆一下，Pauli 运算符的每个度量值都会检查正在测量的状态对应的 eigenvalue，因此对于上表中的每个状态 $ \ket{\psi} $，我们都可以计算 $Z _0 Z_1 \ket{\psi} $，以查看是否获得 $ \pm\ket{\psi} $。</span><span class="sxs-lookup"><span data-stu-id="e614d-137">Recall that each measurement of a Pauli operator checks which eigenvalue  the state being measured corresponds to, so for each state $\ket{\psi}$ in the table above, we can compute $Z_0 Z_1 \ket{\psi}$ to see if we get $\pm\ket{\psi}$.</span></span>
<span data-ttu-id="e614d-138">请注意，$Z _0 Z_1 \ket {000} = \ket {000} $ and，$Z _0 Z_1 \ket {111} = \ket {111} $，因此，我们得出这一度量值对这两种编码状态执行相同的操作。</span><span class="sxs-lookup"><span data-stu-id="e614d-138">Note that $Z_0 Z_1 \ket{000} = \ket{000}$ and that $Z_0 Z_1 \ket{111} = \ket{111}$, so that we conclude that this measurement does the same thing to both encoded states.</span></span>
<span data-ttu-id="e614d-139">另一方面，$Z _0 Z_1 \ket {100} =-\ket {100} $ and $Z _0 Z_1 \ket {011} =-\ket {011} $，因此衡量 $Z _0 Z_1 $ 的结果将显示有关发生了哪些错误的有用信息。</span><span class="sxs-lookup"><span data-stu-id="e614d-139">On the other hand, $Z_0 Z_1 \ket{100} = - \ket{100}$ and $Z_0 Z_1 \ket{011} = -\ket{011}$, so the result of measuring $Z_0 Z_1$ reveals useful information about which error occurred.</span></span>

<span data-ttu-id="e614d-140">为了强调这一点，请重复上述表，但在每一行上添加度量 $Z _0 Z_1 $ 和 $Z _1 Z_2 $ 的结果。</span><span class="sxs-lookup"><span data-stu-id="e614d-140">To emphasize this, we repeat the table above, but add the results of measuring $Z_0 Z_1$ and $Z_1 Z_2$ on each row.</span></span>
<span data-ttu-id="e614d-141">我们将每个度量值的结果表示为所观察到的 eigenvalue 的符号，分别为 $ + $ 或 $-$，分别对应于 Q# `Result` 和的值 `Zero` `One` 。</span><span class="sxs-lookup"><span data-stu-id="e614d-141">We denote the results of each measurement by the sign of the eigenvalue that is observed, either $+$ or $-$, corresponding to the Q# `Result` values of `Zero` and `One`, respectively.</span></span>

| <span data-ttu-id="e614d-142">错误 $E $</span><span class="sxs-lookup"><span data-stu-id="e614d-142">Error $E$</span></span> | <span data-ttu-id="e614d-143">$E \ket{\overline {0} } $</span><span class="sxs-lookup"><span data-stu-id="e614d-143">$E\ket{\overline{0}}$</span></span> | <span data-ttu-id="e614d-144">$E \ket{\overline {1} } $</span><span class="sxs-lookup"><span data-stu-id="e614d-144">$E\ket{\overline{1}}$</span></span> | <span data-ttu-id="e614d-145">$Z _0 的结果 Z_1 $</span><span class="sxs-lookup"><span data-stu-id="e614d-145">Result of $Z_0 Z_1$</span></span> | <span data-ttu-id="e614d-146">$Z _1 Z_2 $ 的结果</span><span class="sxs-lookup"><span data-stu-id="e614d-146">Result of $Z_1 Z_2$</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="e614d-147">$ \boldone $</span><span class="sxs-lookup"><span data-stu-id="e614d-147">$\boldone$</span></span> | <span data-ttu-id="e614d-148">$ \ket {000} $</span><span class="sxs-lookup"><span data-stu-id="e614d-148">$\ket{000}$</span></span> | <span data-ttu-id="e614d-149">$ \ket {111} $</span><span class="sxs-lookup"><span data-stu-id="e614d-149">$\ket{111}$</span></span> | $+$ | $+$ |
| <span data-ttu-id="e614d-150">$X_0$</span><span class="sxs-lookup"><span data-stu-id="e614d-150">$X_0$</span></span> | <span data-ttu-id="e614d-151">$ \ket {100} $</span><span class="sxs-lookup"><span data-stu-id="e614d-151">$\ket{100}$</span></span> | <span data-ttu-id="e614d-152">$ \ket {011} $</span><span class="sxs-lookup"><span data-stu-id="e614d-152">$\ket{011}$</span></span> | $-$ | $+$ |
| <span data-ttu-id="e614d-153">$X_1$</span><span class="sxs-lookup"><span data-stu-id="e614d-153">$X_1$</span></span> | <span data-ttu-id="e614d-154">$ \ket {010} $</span><span class="sxs-lookup"><span data-stu-id="e614d-154">$\ket{010}$</span></span> | <span data-ttu-id="e614d-155">$ \ket {101} $</span><span class="sxs-lookup"><span data-stu-id="e614d-155">$\ket{101}$</span></span> | $-$ | $-$ |
| <span data-ttu-id="e614d-156">$X_2$</span><span class="sxs-lookup"><span data-stu-id="e614d-156">$X_2$</span></span> | <span data-ttu-id="e614d-157">$ \ket {001} $</span><span class="sxs-lookup"><span data-stu-id="e614d-157">$\ket{001}$</span></span> | <span data-ttu-id="e614d-158">$ \ket {110} $</span><span class="sxs-lookup"><span data-stu-id="e614d-158">$\ket{110}$</span></span> | $+$ | $-$ |

<span data-ttu-id="e614d-159">因此，两个度量值的结果可唯一确定发生了哪个位翻转错误，但不会泄漏有关所编码的状态的任何信息。</span><span class="sxs-lookup"><span data-stu-id="e614d-159">Thus, the results of the two measurements uniquely determines which bit-flip error occurred, but without revealing any information about which state we encoded.</span></span>
<span data-ttu-id="e614d-160">我们将这些结果称为 "不 *症状* "，并参阅将一个症状映射回导致其 *恢复* 的错误的过程。</span><span class="sxs-lookup"><span data-stu-id="e614d-160">We call these results a *syndrome* , and refer to the process of mapping a syndrome back to the error that caused it as *recovery* .</span></span>
<span data-ttu-id="e614d-161">特别是，我们强调，恢复是一种 *传统* 的推理过程，该过程会将发生的症状作为其输入，并返回一个指示，说明如何修复可能发生的任何错误。</span><span class="sxs-lookup"><span data-stu-id="e614d-161">In particular, we emphasize that recovery is a *classical* inference procedure which takes as its input the syndrome which occurred, and returns a prescription for how to fix any errors that may have occurred.</span></span>

> [!NOTE]
> <span data-ttu-id="e614d-162">以上的位翻转代码只能纠正单个位翻转错误;也就是说， `X` 操作在单个 qubit 上。</span><span class="sxs-lookup"><span data-stu-id="e614d-162">The bit-flip code above can only correct against single bit-flip errors; that is, an `X` operation acting on a single qubit.</span></span>
> <span data-ttu-id="e614d-163">如果应用 `X` 于多个 qubit，将在恢复后将 $ \ket{\overline {0} } $ 映射到 $ \ket{\overline {1} } $。</span><span class="sxs-lookup"><span data-stu-id="e614d-163">Applying `X` to more than one qubit will map $\ket{\overline{0}}$ to $\ket{\overline{1}}$ following recovery.</span></span>
> <span data-ttu-id="e614d-164">同样，应用阶段翻转操作 `Z` 会将 $ \ket{\overline {1} } $ 映射到 $-\ket{\overline {1} } $，因此会将 $ \ket{\overline{+}} $ 映射到 $ \ket{\overline {-} } $。</span><span class="sxs-lookup"><span data-stu-id="e614d-164">Similarly, applying a phase flip operation `Z` will map $\ket{\overline{1}}$ to $-\ket{\overline{1}}$, and hence will map $\ket{\overline{+}}$ to $\ket{\overline{-}}$.</span></span>
> <span data-ttu-id="e614d-165">通常，可以创建代码来处理更多错误，并处理 $Z $ 个错误以及 $X $ 个错误。</span><span class="sxs-lookup"><span data-stu-id="e614d-165">More generally, codes can be created to handle larger number of errors, and to handle $Z$ errors as well as $X$ errors.</span></span>

<span data-ttu-id="e614d-166">对于在所有代码状态下以相同方式操作的量程错误更正，我们可以对其进行描述，这就是 *稳定的形式* 。</span><span class="sxs-lookup"><span data-stu-id="e614d-166">The insight that we can describe measurements in quantum error correction that act the same way on all code states, is the essence of the *stabilizer formalism* .</span></span>
<span data-ttu-id="e614d-167">Q#Canon 提供了一个框架，用于描述从稳定程序代码进行的编码和解码，并描述了一个从错误中恢复的方法。</span><span class="sxs-lookup"><span data-stu-id="e614d-167">The Q# canon provides a framework for describing encoding into and decoding from stabilizer codes, and for describing how one recovers from errors.</span></span>
<span data-ttu-id="e614d-168">在本部分中，我们使用几个简单的量程纠错代码描述此框架及其应用程序。</span><span class="sxs-lookup"><span data-stu-id="e614d-168">In this section, we describe this framework and its application to a few simple quantum error-correcting codes.</span></span>

> [!TIP]
> <span data-ttu-id="e614d-169">稳定介绍了对稳定形式的介绍。</span><span class="sxs-lookup"><span data-stu-id="e614d-169">A full introduction to the stabilizer formalism is beyond the scope of this section.</span></span>
> <span data-ttu-id="e614d-170">我们向读者介绍了了解更多 [Gottesman 2009](https://arxiv.org/abs/0904.2557)的兴趣。</span><span class="sxs-lookup"><span data-stu-id="e614d-170">We refer readers interested in learning more to [Gottesman 2009](https://arxiv.org/abs/0904.2557).</span></span>

## <a name="representing-error-correcting-codes-in-no-locq"></a><span data-ttu-id="e614d-171">表示中的纠错代码 Q#</span><span class="sxs-lookup"><span data-stu-id="e614d-171">Representing Error Correcting Codes in Q#</span></span> ##

<span data-ttu-id="e614d-172">为了帮助指定错误更正代码， Q# canon 提供了几种不同的用户定义类型：</span><span class="sxs-lookup"><span data-stu-id="e614d-172">To help specify error correcting codes, the Q# canon provides several distinct user-defined types:</span></span>

- <span data-ttu-id="e614d-173"><xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister>`= Qubit[]`：表示 qubits 的寄存器应解释为纠错代码的代码块。</span><span class="sxs-lookup"><span data-stu-id="e614d-173"><xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister> `= Qubit[]`: Denotes that a register of qubits should be interpreted as the code block of an error-correcting code.</span></span>
- <span data-ttu-id="e614d-174"><xref:Microsoft.Quantum.ErrorCorrection.Syndrome>`= Result[]`：表示度量结果的数组应解释为在代码块上测量的症状。</span><span class="sxs-lookup"><span data-stu-id="e614d-174"><xref:Microsoft.Quantum.ErrorCorrection.Syndrome> `= Result[]`: Denotes that an array of measurement results should be interpreted as the syndrome measured on a code block.</span></span>
- <span data-ttu-id="e614d-175"><xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn>`= (Syndrome -> Pauli[])`：表示 *传统* 函数应用于解释症状并返回应应用的更正。</span><span class="sxs-lookup"><span data-stu-id="e614d-175"><xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn> `= (Syndrome -> Pauli[])`: Denotes that a *classical* function should be used to interpret a syndrome and return a correction that should be applied.</span></span>
- <span data-ttu-id="e614d-176"><xref:Microsoft.Quantum.ErrorCorrection.EncodeOp>`= ((Qubit[], Qubit[]) => LogicalRegister)`：表示操作使用表示数据的 qubits 和全新的 ancilla qubits，以生成错误更正代码的代码块。</span><span class="sxs-lookup"><span data-stu-id="e614d-176"><xref:Microsoft.Quantum.ErrorCorrection.EncodeOp> `= ((Qubit[], Qubit[]) => LogicalRegister)`: Denotes that an operation takes qubits representing data along with fresh ancilla qubits in order to produce a code block of an error-correcting code.</span></span>
- <span data-ttu-id="e614d-177"><xref:Microsoft.Quantum.ErrorCorrection.DecodeOp>`= (LogicalRegister => (Qubit[], Qubit[]))`：表示一个操作，分解将错误更正代码的代码块转换为数据 qubits，并使用 ancilla qubits 表示症状信息。</span><span class="sxs-lookup"><span data-stu-id="e614d-177"><xref:Microsoft.Quantum.ErrorCorrection.DecodeOp> `= (LogicalRegister => (Qubit[], Qubit[]))`: Denotes than an operation decomposes a code block of an error correcting code into the data qubits and the ancilla qubits used to represent syndrome information.</span></span>
- <span data-ttu-id="e614d-178"><xref:Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp>`= (LogicalRegister => Syndrome)`：表示一个操作，该操作应用于从代码块中提取症状信息，而不会影响由代码保护的状态。</span><span class="sxs-lookup"><span data-stu-id="e614d-178"><xref:Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp> `= (LogicalRegister => Syndrome)`: Denotes an operation that should be used to extract syndrome information from a code block, without disturbing the state protected by the code.</span></span>

<span data-ttu-id="e614d-179">最后，canon 提供 <xref:Microsoft.Quantum.ErrorCorrection.QECC> 类型以收集定义量程错误更正代码所需的其他类型。</span><span class="sxs-lookup"><span data-stu-id="e614d-179">Finally, the canon provides the <xref:Microsoft.Quantum.ErrorCorrection.QECC> type to collect the other types required to define a quantum error-correcting code.</span></span> <span data-ttu-id="e614d-180">与每个稳定量程代码相关联的代码长度为： $ $n $、逻辑 qubits 的数字 $k $，$d $，最小距离 $，通常以表示法⟦ $n $，$k $，$d $ ⟧。</span><span class="sxs-lookup"><span data-stu-id="e614d-180">Associated with each stabilizer quantum code is the code length $n$, the number $k$ of logical qubits, and the minimum distance $d$, often conveniently grouped together in the notation ⟦$n$, $k$, $d$⟧.</span></span> <span data-ttu-id="e614d-181">例如， <xref:Microsoft.Quantum.ErrorCorrection.BitFlipCode> 函数定义⟦3，1，1⟧位翻转代码：</span><span class="sxs-lookup"><span data-stu-id="e614d-181">For example, the <xref:Microsoft.Quantum.ErrorCorrection.BitFlipCode> function defines the ⟦3, 1, 1⟧ bit flip code:</span></span>

```qsharp
let encodeOp = EncodeOp(BitFlipEncoder);
let decodeOp = DecodeOp(BitFlipDecoder);
let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
    [PauliZ, PauliZ, PauliI],
    [PauliI, PauliZ, PauliZ]
], _, MeasureWithScratch));
let code = QECC(encodeOp, decodeOp, syndMeasOp);
```

<span data-ttu-id="e614d-182">请注意，该 `QECC` 类型 *不* 包含恢复功能。</span><span class="sxs-lookup"><span data-stu-id="e614d-182">Notice that the `QECC` type does *not* include a recovery function.</span></span>
<span data-ttu-id="e614d-183">这样，我们就可以更改在更正错误时使用的恢复功能，而无需更改代码本身的定义;此功能在将信息从特征度量纳入到恢复所假定的模型时特别有用。</span><span class="sxs-lookup"><span data-stu-id="e614d-183">This allows us to change the recovery function that is used in correcting errors without changing the definition of the code itself; this ability is in particular useful when incorporating feedback from characterization measurements into the model assumed by recovery.</span></span>

<span data-ttu-id="e614d-184">以这种方式定义代码后，可以使用该 <xref:Microsoft.Quantum.ErrorCorrection.Recover> 操作从错误中恢复：</span><span class="sxs-lookup"><span data-stu-id="e614d-184">Once a code is defined in this way, we can use the <xref:Microsoft.Quantum.ErrorCorrection.Recover> operation to recover from errors:</span></span>

```qsharp
let code = BitFlipCode();
let fn = BitFlipRecoveryFn();
let X0 = ApplyPauli([PauliX, PauliI, PauliI], _);
using (scratch = Qubit[nScratch]) {
    let logicalRegister = encode(data, scratch);
    // Cause an error.
    X0(logicalRegister);
    Recover(code, fn, logicalRegister);
    let (decodedData, decodedScratch) = decode(logicalRegister);
    ApplyToEach(Reset, decodedScratch);
}
```

<span data-ttu-id="e614d-185">我们将在 [位翻转代码示例](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code)中更详细地探讨这一点。</span><span class="sxs-lookup"><span data-stu-id="e614d-185">We explore this in more detail in the [bit flip code sample](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code).</span></span>

<span data-ttu-id="e614d-186">除了位翻转代码 Q# 外，canon 还提供了 [5 qubit 完美代码](https://arxiv.org/abs/quant-ph/9602019)的实现和 [七 qubit 代码](https://arxiv.org/abs/quant-ph/9705052)，这两者都可以更正任意单 qubit 错误。</span><span class="sxs-lookup"><span data-stu-id="e614d-186">Aside from the bit-flip code, the Q# canon is provided with implementations of the [five-qubit perfect code](https://arxiv.org/abs/quant-ph/9602019), and the [seven-qubit code](https://arxiv.org/abs/quant-ph/9705052), both of which can correct an arbitrary single-qubit error.</span></span>
