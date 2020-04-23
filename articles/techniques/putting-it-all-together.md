---
title: Q# 技术 - 将其全部放在一起
description: 浏览演示量子传送的基本 Q# 程序。
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4bd91699017e4c1acd9f4449b8a65e39bd07878e
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030559"
---
# <a name="putting-it-all-together-teleportation"></a><span data-ttu-id="52847-103">将所有功能放在一起：传送</span><span class="sxs-lookup"><span data-stu-id="52847-103">Putting It All Together: Teleportation</span></span> #
<span data-ttu-id="52847-104">让我们回到[量子电路](xref:microsoft.quantum.concepts.circuits)中定义的传送电路的例子。</span><span class="sxs-lookup"><span data-stu-id="52847-104">Let's return to the example of the teleportation circuit defined in [Quantum Circuits](xref:microsoft.quantum.concepts.circuits).</span></span> <span data-ttu-id="52847-105">我们将用它来说明我们迄今学到的概念。</span><span class="sxs-lookup"><span data-stu-id="52847-105">We're going to use this to illustrate the concepts we've learned so far.</span></span> <span data-ttu-id="52847-106">下面为不熟悉该理论的人提供量子传送的说明，随后在 Q# 中介绍代码实现。</span><span class="sxs-lookup"><span data-stu-id="52847-106">An explanation of quantum teleportation is provided below for those who are unfamiliar with the theory, followed by a walkthrough of the code implementation in Q#.</span></span> 

## <a name="quantum-teleportation-theory"></a><span data-ttu-id="52847-107">量子传送：理论</span><span class="sxs-lookup"><span data-stu-id="52847-107">Quantum Teleportation: Theory</span></span>
<span data-ttu-id="52847-108">量子传送是一种将未知量子状态（我们称之为"__消息__"）从一个位置的量子位发送到另一个位置的量子位的技术（我们将这些量子位分别称为"__此处__"和"__此处__"。</span><span class="sxs-lookup"><span data-stu-id="52847-108">Quantum teleportation is a technique for sending an unknown quantum state (which we'll refer to as the '__message__') from a qubit in one location to a qubit in another location (we'll refer to these qubits as '__here__' and '__there__', respectively).</span></span> <span data-ttu-id="52847-109">我们可以使用 Dirac 表示法表示我们__的消息__作为矢量：</span><span class="sxs-lookup"><span data-stu-id="52847-109">We can represent our __message__ as a vector using Dirac notation:</span></span> 

<span data-ttu-id="52847-110">$$$\ket_psi] = \alpha\ket{0} ={1} \beta\ket $$$</span><span class="sxs-lookup"><span data-stu-id="52847-110">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="52847-111">__消息__qubit 的状态是未知的，因为我们不知道 $_alpha$ 和 $_beta$的值。</span><span class="sxs-lookup"><span data-stu-id="52847-111">The __message__ qubit's state is unknown to us as we do not know the values of $\alpha$ and $\beta$.</span></span>

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="52847-112">第 1 步：创建纠缠状态</span><span class="sxs-lookup"><span data-stu-id="52847-112">Step 1: Create an entangled state</span></span>
<span data-ttu-id="52847-113">为了__发送消息，我们需要____在这里__的量子位与那里的量子位纠缠在一__起__。</span><span class="sxs-lookup"><span data-stu-id="52847-113">In order to send the __message__ we need for the qubit __here__ to be entangled with the qubit __there__.</span></span> <span data-ttu-id="52847-114">这是通过应用哈达马德门来实现的，然后是 CNOT 门。</span><span class="sxs-lookup"><span data-stu-id="52847-114">This is achieved by applying a Hadamard gate, followed by a CNOT gate.</span></span> <span data-ttu-id="52847-115">让我们来看看这些门操作背后的数学。</span><span class="sxs-lookup"><span data-stu-id="52847-115">Let's look at the math behind these gate operations.</span></span>

<span data-ttu-id="52847-116">我们将从__此处__和__此处__的 qubit 开始，两者都位于{0}$ket $ 状态。</span><span class="sxs-lookup"><span data-stu-id="52847-116">We will begin with the qubits __here__ and __there__ both in the $\ket{0}$ state.</span></span> <span data-ttu-id="52847-117">纠缠这些量子位后，它们处于以下状态：</span><span class="sxs-lookup"><span data-stu-id="52847-117">After entangling these qubits, they are in the state:</span></span>

<span data-ttu-id="52847-118">{1}$$$\ket_phi_= = _frac [sqrt]（\ket{2}{00} ={11}\ket） $$$</span><span class="sxs-lookup"><span data-stu-id="52847-118">$$ \ket{\phi^+} = \frac{1}{\sqrt{2}}(\ket{00} + \ket{11}) $$</span></span>

### <a name="step-2-send-the-message"></a><span data-ttu-id="52847-119">第 2 步：发送消息</span><span class="sxs-lookup"><span data-stu-id="52847-119">Step 2: Send the message</span></span>
<span data-ttu-id="52847-120">为了__发送消息，我们__首先应用一个带有__消息__qubit的 CNOT 门，__此处__将 qubit 作为输入（__消息__qubit 是控件，__此处__的 qubit 是目标 qubit，在这种情况下）。</span><span class="sxs-lookup"><span data-stu-id="52847-120">To send the __message__ we first apply a CNOT gate with the __message__ qubit and __here__ qubit as inputs (the __message__ qubit being the control and the __here__ qubit being the target qubit, in this instance).</span></span> <span data-ttu-id="52847-121">可以写入此输入状态：</span><span class="sxs-lookup"><span data-stu-id="52847-121">This input state can be written:</span></span>

<span data-ttu-id="52847-122">$$$\ket\psi_ket_ket_phi_]= （\alpha_ket{0} {1}= \beta_ket）（\frac{1}[sqrt]（\ket{2}{00} {11}= \ket）$$</span><span class="sxs-lookup"><span data-stu-id="52847-122">$$ \ket{\psi}\ket{\phi^+} = (\alpha\ket{0} + \beta\ket{1})(\frac{1}{\sqrt{2}}(\ket{00} + \ket{11})) $$</span></span>

<span data-ttu-id="52847-123">这将扩展到：</span><span class="sxs-lookup"><span data-stu-id="52847-123">This expands to:</span></span>

<span data-ttu-id="52847-124">$$ \ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} + \frac{\beta}{\sqrt{2}}\ket{111} $$</span><span class="sxs-lookup"><span data-stu-id="52847-124">$$ \ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} + \frac{\beta}{\sqrt{2}}\ket{111} $$</span></span>

<span data-ttu-id="52847-125">作为提醒，当控件 qubit 为 1 时，CNOT 门将翻转目标量子位。</span><span class="sxs-lookup"><span data-stu-id="52847-125">As a reminder, the CNOT gate flips the target qubit when the control qubit is 1.</span></span> <span data-ttu-id="52847-126">因此，例如，$_ket{000}$ 的输入不会导致任何变化，因为第一个 qubit（控件）为 0。</span><span class="sxs-lookup"><span data-stu-id="52847-126">So for example, an input of $\ket{000}$ will result in no change as the first qubit (the control) is 0.</span></span> <span data-ttu-id="52847-127">但是，以第一个 qubit 为 1 的情况为例 ， 例如{100}，输入为 $_ket $。</span><span class="sxs-lookup"><span data-stu-id="52847-127">However, take a case where the first qubit is 1 - for example an input of $\ket{100}$.</span></span> <span data-ttu-id="52847-128">在这种情况下，输出为 $_ket{110}$，因为第二个 qubit（目标）由 CNOT 门翻转。</span><span class="sxs-lookup"><span data-stu-id="52847-128">In this instance, the output is $\ket{110}$ as the second qubit (the target) is flipped by the CNOT gate.</span></span>

<span data-ttu-id="52847-129">现在，让我们考虑我们的输出，一旦CNOT门已经按照我们上面的意见采取行动。</span><span class="sxs-lookup"><span data-stu-id="52847-129">Let's now consider our output once the CNOT gate has acted on our input above.</span></span> <span data-ttu-id="52847-130">结果为：</span><span class="sxs-lookup"><span data-stu-id="52847-130">The result is:</span></span>

<span data-ttu-id="52847-131">$$ \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{\beta}{\sqrt{2}}\ket{101} $$</span><span class="sxs-lookup"><span data-stu-id="52847-131">$$ \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{\beta}{\sqrt{2}}\ket{101} $$</span></span>

<span data-ttu-id="52847-132">发送__消息__的下一步是将 Hadamard 门应用于__消息__qubit（这是每个术语的第一个 qubit）。</span><span class="sxs-lookup"><span data-stu-id="52847-132">The next step to send the __message__ is to apply a Hadamard gate to the __message__ qubit (that's the first qubit of each term).</span></span> 

<span data-ttu-id="52847-133">作为提醒，哈达马德门执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="52847-133">As a reminder, the Hadamard gate does the following:</span></span>

<span data-ttu-id="52847-134">输入</span><span class="sxs-lookup"><span data-stu-id="52847-134">Input</span></span> | <span data-ttu-id="52847-135">输出</span><span class="sxs-lookup"><span data-stu-id="52847-135">Output</span></span>
---------------------------| ---------------------------------------------------------------
<span data-ttu-id="52847-136">$\ket{0}$</span><span class="sxs-lookup"><span data-stu-id="52847-136">$\ket{0}$</span></span>  | <span data-ttu-id="52847-137">$_frac{1}\sqrt{2}[（\ket{0} ={1}\ket ）$</span><span class="sxs-lookup"><span data-stu-id="52847-137">$\frac{1}{\sqrt{2}}(\ket{0} + \ket{1})$</span></span>
<span data-ttu-id="52847-138">$\ket{1}$</span><span class="sxs-lookup"><span data-stu-id="52847-138">$\ket{1}$</span></span>  | <span data-ttu-id="52847-139">$_frac{1}\sqrt{2}\（\ket{0} -{1}\ket ）$</span><span class="sxs-lookup"><span data-stu-id="52847-139">$\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})$</span></span>

<span data-ttu-id="52847-140">如果我们将 Hadamard 门应用于上述输出的每个术语的第一个 qubit，我们会得到以下结果：</span><span class="sxs-lookup"><span data-stu-id="52847-140">If we apply the Hadamard gate to the first qubit of each term of our output above, we get the following result:</span></span>

<span data-ttu-id="52847-141">$${2}_frac_alpha_sqrt _（\frac{1}_sqrt{2}\c \c{0} =ket{1}）\ket{00} \c =\c_\c_\c_\c_\c_sqrt{2}[（\frac{1}_sqrt{2}\c{0} {1}_ket）\ket{11} ]{2}[frac_beta]_sqrt{1}_（\frac{1}_sqrt{10} {2}\c _c_ket{0} ）\ket{2}=\c_beta_sqrt_（_frac{1}_sqrt{2}_（\ket{0} - \ket））\ket{1}{01} $$$$$$$</span><span class="sxs-lookup"><span data-stu-id="52847-141">$$ \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{00} + \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{11} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{10} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{01} $$</span></span>

<span data-ttu-id="52847-142">请注意，每个术语都有两个 $frac{1}\sqrt{2}\$$因子。</span><span class="sxs-lookup"><span data-stu-id="52847-142">Note that each term has two $\frac{1}{\sqrt{2}}$ factors.</span></span> <span data-ttu-id="52847-143">我们可以将这些乘数乘以给出以下结果：</span><span class="sxs-lookup"><span data-stu-id="52847-143">We can multiply these out giving the following result:</span></span>

<span data-ttu-id="52847-144">$$ [frac_alpha]{2}（\ket{0} ={1}\ket{00} ）\ket{2}={0} \ket{1}\ket ）\ket{11} =\c_beta]（\ket{2}{0} {1}- \ket）\ket{10} {2}=\c_beta]（\ket{0} - \ket）\ket）\ket{1}{01}</span><span class="sxs-lookup"><span data-stu-id="52847-144">$$ \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{11} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{10} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{01} $$</span></span>

<span data-ttu-id="52847-145">$_frac{1}{2}$ 因子是每个术语的通用，因此我们现在可以在括号外将其采用：</span><span class="sxs-lookup"><span data-stu-id="52847-145">The  $\frac{1}{2}$ factor is common to each term so we can now take it outside the brackets:</span></span>

<span data-ttu-id="52847-146">$$ \frac{1}{2}\big[\alpha(\ket{0} + \ket{1})\ket{00} + \alpha(\ket{0} + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket{01}\big] $$</span><span class="sxs-lookup"><span data-stu-id="52847-146">$$ \frac{1}{2}\big[\alpha(\ket{0} + \ket{1})\ket{00} + \alpha(\ket{0} + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket{01}\big] $$</span></span>

<span data-ttu-id="52847-147">然后，我们可以将每个术语的括号相乘：</span><span class="sxs-lookup"><span data-stu-id="52847-147">We can then multiply out the brackets for each term giving:</span></span>

<span data-ttu-id="52847-148">$$ \frac{1}{2}\big[\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} - \beta\ket{110} + \beta\ket{001} - \beta\ket{101}\big] $$</span><span class="sxs-lookup"><span data-stu-id="52847-148">$$ \frac{1}{2}\big[\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} - \beta\ket{110} + \beta\ket{001} - \beta\ket{101}\big] $$</span></span>

### <a name="step-3-measure-the-result"></a><span data-ttu-id="52847-149">第 3 步：测量结果</span><span class="sxs-lookup"><span data-stu-id="52847-149">Step 3: Measure the result</span></span>

<span data-ttu-id="52847-150">由于__这里____和那里__纠缠，__任何测量在这里__将影响__那里__的状态。</span><span class="sxs-lookup"><span data-stu-id="52847-150">Due to __here__ and __there__ being entangled, any measurement on __here__ will affect the state of __there__.</span></span> <span data-ttu-id="52847-151">如果我们测量第一个和第二量子位（__消息__和__这里__），我们可以知道__处于__什么状态，由于这种纠缠的属性。</span><span class="sxs-lookup"><span data-stu-id="52847-151">If we measure the first and second qubit (__message__ and __here__) we can learn what state __there__ is in, due to this property of entanglement.</span></span> 

* <span data-ttu-id="52847-152">如果我们测量并获取结果 00，叠加将折叠，仅保留与此结果一致的术语。</span><span class="sxs-lookup"><span data-stu-id="52847-152">If we measure and get a result 00, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="52847-153">那是 $_alpha\ket{000} \beta\ket{001}$。</span><span class="sxs-lookup"><span data-stu-id="52847-153">That's $\alpha\ket{000} +\beta\ket{001}$.</span></span> <span data-ttu-id="52847-154">这可以重构为 $\ket{00}（\alpha\ket{0} \beta_ket{1}）$。</span><span class="sxs-lookup"><span data-stu-id="52847-154">This can be refactored to $\ket{00}(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="52847-155">因此，如果我们将第一个和第二个 qubit 测量为 00，我们知道第三个 qubit，__有__，处于状态 $（\alpha\ket\beta\ket）$。{0} {1}</span><span class="sxs-lookup"><span data-stu-id="52847-155">Therefore if we measure the first and second qubit to be 00, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="52847-156">如果我们测量并获取结果 01，叠加将折叠，仅保留与此结果一致的术语。</span><span class="sxs-lookup"><span data-stu-id="52847-156">If we measure and get a result 01, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="52847-157">那是 $_alpha\ket{011} \beta\ket{010}$。</span><span class="sxs-lookup"><span data-stu-id="52847-157">That's $\alpha\ket{011} +\beta\ket{010}$.</span></span> <span data-ttu-id="52847-158">这可以重构为 $\ket{01}（\alpha\ket{1} \beta_ket{0}）$。</span><span class="sxs-lookup"><span data-stu-id="52847-158">This can be refactored to $\ket{01}(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="52847-159">因此，如果我们测量第一个和第二个量子位为 01，我们知道第三个 qubit，__有__，在状态 $（\alpha\ket\beta\ket）$。{1} {0}</span><span class="sxs-lookup"><span data-stu-id="52847-159">Therefore if we measure the first and second qubit to be 01, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span>
* <span data-ttu-id="52847-160">如果我们测量并获取结果 10，叠加将折叠，仅保留与此结果一致的术语。</span><span class="sxs-lookup"><span data-stu-id="52847-160">If we measure and get a result 10, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="52847-161">那是 $_alpha\ket{100} -\beta\ket{101}$。</span><span class="sxs-lookup"><span data-stu-id="52847-161">That's $\alpha\ket{100} -\beta\ket{101}$.</span></span> <span data-ttu-id="52847-162">这可以重构为 $\ket{10}（\alpha\ket{0} -_beta_ket{1}）$。</span><span class="sxs-lookup"><span data-stu-id="52847-162">This can be refactored to $\ket{10}(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="52847-163">因此，如果我们将第一个和第二个量子位度量为 10，我们知道第三个 qubit，__有__，处于状态 $（\alpha_ket-_beta_ket）$。{0} {1}</span><span class="sxs-lookup"><span data-stu-id="52847-163">Therefore if we measure the first and second qubit to be 10, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span>
* <span data-ttu-id="52847-164">如果我们测量并获取结果 11，叠加将折叠，仅保留与此结果一致的术语。</span><span class="sxs-lookup"><span data-stu-id="52847-164">If we measure and get a result 11, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="52847-165">那是 $_alpha\ket{111} -\beta\ket{110}$。</span><span class="sxs-lookup"><span data-stu-id="52847-165">That's $\alpha\ket{111} -\beta\ket{110}$.</span></span> <span data-ttu-id="52847-166">这可以重构为 $\ket{11}（\alpha\ket{1} -_beta_ket{0}）$。</span><span class="sxs-lookup"><span data-stu-id="52847-166">This can be refactored to $\ket{11}(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="52847-167">因此，如果我们将第一个和第二个量子位度量为 11，我们知道第三个 qubit，__有__，处于状态 $（\alpha_ket-_beta_ket）$。{1} {0}</span><span class="sxs-lookup"><span data-stu-id="52847-167">Therefore if we measure the first and second qubit to be 11, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span>

### <a name="step-4-interpret-the-result"></a><span data-ttu-id="52847-168">第 4 步：解释结果</span><span class="sxs-lookup"><span data-stu-id="52847-168">Step 4: Interpret the result</span></span>

<span data-ttu-id="52847-169">作为提醒，我们希望发送的原始__信息__是：</span><span class="sxs-lookup"><span data-stu-id="52847-169">As a reminder, the original __message__ we wished to send was:</span></span>

<span data-ttu-id="52847-170">$$$\ket_psi] = \alpha\ket{0} ={1} \beta\ket $$$</span><span class="sxs-lookup"><span data-stu-id="52847-170">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="52847-171">我们需要将__那里的__qubit 放入此状态，以便接收的状态是预期状态。</span><span class="sxs-lookup"><span data-stu-id="52847-171">We need to get the __there__ qubit into this state, so that the received state is the one that was intended.</span></span> 

* <span data-ttu-id="52847-172">如果我们测量并得到的结果为 00，则第三个 qubit，__有__，处于状态 $（\alpha\ket\beta\ket）$。{0} {1}</span><span class="sxs-lookup"><span data-stu-id="52847-172">If we measured and got a result of 00, then the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="52847-173">由于这是预期__的消息__，因此无需更改。</span><span class="sxs-lookup"><span data-stu-id="52847-173">As this is the intended __message__, no alteration is required.</span></span>
* <span data-ttu-id="52847-174">如果我们测量并得到 01 的结果，则第三个 qubit，__有__，处于状态 $（\alpha\ket\beta_ket）$。{1} {0}</span><span class="sxs-lookup"><span data-stu-id="52847-174">If we measured and got a result of 01, then the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="52847-175">这与预期__消息__不同，但是应用 NOT 门会给我们所需的状态 $（\alpha\ket\beta\ket）$。{0} {1}</span><span class="sxs-lookup"><span data-stu-id="52847-175">This differs from the intended __message__, however applying a NOT gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="52847-176">如果我们测量并得到 10 的结果，则第三个 qubit，__有__，在状态 $（\alpha\ket{0} -_beta_ket）$。{1}</span><span class="sxs-lookup"><span data-stu-id="52847-176">If we measured and got a result of 10, then the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="52847-177">这与预期__消息__不同，但是应用 Z 门会给我们所需的状态 $（\alpha\ket\beta\ket）$。{0} {1}</span><span class="sxs-lookup"><span data-stu-id="52847-177">This differs from the intended __message__, however applying a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="52847-178">如果我们测量并得到 11 的结果，那么第三个 qubit，__有__，是在状态 $（\alpha\ket{1} -_beta_ket）$。{0}</span><span class="sxs-lookup"><span data-stu-id="52847-178">If we measured and got a result of 11, then the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="52847-179">这与预期__消息__不同，但是应用 NOT 门后跟 Z 门会给我们所需的状态 $（\alpha\ket\beta_ket）$。{0} {1}</span><span class="sxs-lookup"><span data-stu-id="52847-179">This differs from the intended __message__, however applying a NOT gate followed by a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>

<span data-ttu-id="52847-180">总之，如果我们测量第一个量子位为 1，则应用 Z 门。</span><span class="sxs-lookup"><span data-stu-id="52847-180">To summarize, if we measure and the first qubit is 1, a Z gate is applied.</span></span> <span data-ttu-id="52847-181">如果我们测量第二个量子位为 1，则应用 NOT 门。</span><span class="sxs-lookup"><span data-stu-id="52847-181">If we measure and the second qubit is 1, a NOT gate is applied.</span></span>

### <a name="summary"></a><span data-ttu-id="52847-182">总结</span><span class="sxs-lookup"><span data-stu-id="52847-182">Summary</span></span>
<span data-ttu-id="52847-183">下面显示了实现传送的教科书量子电路。</span><span class="sxs-lookup"><span data-stu-id="52847-183">Shown below is a text-book quantum circuit that implements the teleportation.</span></span> <span data-ttu-id="52847-184">从左到右移动，您可以看到：</span><span class="sxs-lookup"><span data-stu-id="52847-184">Moving from left to right you can see:</span></span>
- <span data-ttu-id="52847-185">第1步：通过应用哈达马德门和CNOT门，__在这里____和那里__纠缠。</span><span class="sxs-lookup"><span data-stu-id="52847-185">Step 1: Entangling __here__ and __there__ by applying a Hadamard gate and CNOT gate.</span></span>
- <span data-ttu-id="52847-186">第 2 步 __：使用__CNOT 门和哈达马德门发送消息。</span><span class="sxs-lookup"><span data-stu-id="52847-186">Step 2: Sending the __message__ using a CNOT gate and a Hadamard gate.</span></span>
- <span data-ttu-id="52847-187">步骤 3：测量第一和第二个量子位，__消息__和__这里__。</span><span class="sxs-lookup"><span data-stu-id="52847-187">Step 3: Taking a measurement of the first and second qubits, __message__ and __here__.</span></span>
- <span data-ttu-id="52847-188">步骤 4：根据步骤 3 中的测量结果应用不门或 Z 门。</span><span class="sxs-lookup"><span data-stu-id="52847-188">Step 4: Applying a NOT gate or a Z gate, depending on the result of the measurement in step 3.</span></span>

!['传送（msg ： Qubit， 有 ： Qubit） ： 单位'](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a><span data-ttu-id="52847-190">量子传送：代码</span><span class="sxs-lookup"><span data-stu-id="52847-190">Quantum Teleportation: Code</span></span>

<span data-ttu-id="52847-191">我们有用于量子传送的电路：</span><span class="sxs-lookup"><span data-stu-id="52847-191">We have our circuit for quantum teleportation:</span></span>

!['传送（msg ： Qubit， 有 ： Qubit） ： 单位'](~/media/teleportation.svg)

<span data-ttu-id="52847-193">现在，我们可以将此量子电路中的每个步骤转换为 Q#。</span><span class="sxs-lookup"><span data-stu-id="52847-193">We can now translate each of the steps in this quantum circuit into Q#.</span></span>

### <a name="step-0-definition"></a><span data-ttu-id="52847-194">步骤 0：定义</span><span class="sxs-lookup"><span data-stu-id="52847-194">Step 0: Definition</span></span>
<span data-ttu-id="52847-195">当我们执行传送时，我们必须知道我们想要__发送的信息__，以及我们希望发送的位置（__那里__）。</span><span class="sxs-lookup"><span data-stu-id="52847-195">When we perform teleportation, we must know the __message__ we wish to send, and where we wish to send it (__there__).</span></span> <span data-ttu-id="52847-196">因此，我们首先定义一个新的传送运运运，该操作给定两个 qubit 作为参数`msg`，`there`和 ：</span><span class="sxs-lookup"><span data-stu-id="52847-196">For this reason, we begin by defining a new Teleport operation that is given two qubits as arguments, `msg` and `there`:</span></span>

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

<span data-ttu-id="52847-197">我们还需要分配一个通过`here``using`块实现的量子位：</span><span class="sxs-lookup"><span data-stu-id="52847-197">We also need to allocate a qubit `here` which we achieve with a `using` block:</span></span>

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="52847-198">第 1 步：创建纠缠状态</span><span class="sxs-lookup"><span data-stu-id="52847-198">Step 1: Create an entangled state</span></span>
<span data-ttu-id="52847-199">然后`here`，我们可以使用`there`@"microsoft.quantum.intrinsic.h"和@"microsoft.quantum.intrinsic.cnot"操作创建 和 之间的纠缠对：</span><span class="sxs-lookup"><span data-stu-id="52847-199">We can then create the entangled pair between `here` and `there` by using the @"microsoft.quantum.intrinsic.h" and @"microsoft.quantum.intrinsic.cnot" operations:</span></span>

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a><span data-ttu-id="52847-200">第 2 步：发送消息</span><span class="sxs-lookup"><span data-stu-id="52847-200">Step 2: Send the message</span></span>
<span data-ttu-id="52847-201">然后，我们使用下一个 $_运算符名称[CNOT_$ 和 $H$ 门来移动我们的消息库比特：</span><span class="sxs-lookup"><span data-stu-id="52847-201">We then use the next $\operatorname{CNOT}$ and $H$ gates to move our message qubit:</span></span>

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a><span data-ttu-id="52847-202">第3步&4：测量和解释结果</span><span class="sxs-lookup"><span data-stu-id="52847-202">Step 3 & 4: Measuring and interpreting the result</span></span>
<span data-ttu-id="52847-203">最后，我们使用@"microsoft.quantum.intrinsic.m"执行测量并执行必要的门操作以获得所需的状态，如`if`语句所述：</span><span class="sxs-lookup"><span data-stu-id="52847-203">Finally, we use @"microsoft.quantum.intrinsic.m" to perform the measurements and perform the necessary gate operations to get the desired state, as denoted by `if` statements:</span></span>

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

### <a name="step-5-restarting-the-qubit-register"></a><span data-ttu-id="52847-204">第 5 步：重新启动量子位寄存器</span><span class="sxs-lookup"><span data-stu-id="52847-204">Step 5: Restarting the qubit register</span></span>

<span data-ttu-id="52847-205">在每个 Q# 操作结束时，我们需要让状态中的 qubit $\ket{0}$$。</span><span class="sxs-lookup"><span data-stu-id="52847-205">At the end of every Q# operation we need to let the qubits in the state $\ket{0}$.</span></span> <span data-ttu-id="52847-206">我们可以使用@"microsoft.quantum.intrinsic.reset"重新启动所有量子位到零状态，这将完成我们的操作。</span><span class="sxs-lookup"><span data-stu-id="52847-206">We can use @"microsoft.quantum.intrinsic.reset" to restart all the qubits to the zero state and this will finish our operation.</span></span>

```qsharp
        Reset(msg);
        Reset(here);
        Reset(there);
    }
}
```


