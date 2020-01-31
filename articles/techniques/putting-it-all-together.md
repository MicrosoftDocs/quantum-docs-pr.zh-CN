---
title: '将其全部放在一起-Q # 技术 |Microsoft Docs'
description: '将其全部放在一起-Q # 技术'
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 3605826da159757d4b321dbf4ec6acd7f4e6be05
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820158"
---
# <a name="putting-it-all-together-teleportation"></a><span data-ttu-id="327db-103">全部放在一起： Teleportation</span><span class="sxs-lookup"><span data-stu-id="327db-103">Putting It All Together: Teleportation</span></span> #
<span data-ttu-id="327db-104">让我们返回到在[量程线路](xref:microsoft.quantum.concepts.circuits)中定义的 teleportation 线路的示例。</span><span class="sxs-lookup"><span data-stu-id="327db-104">Let's return to the example of the teleportation circuit defined in [Quantum Circuits](xref:microsoft.quantum.concepts.circuits).</span></span> <span data-ttu-id="327db-105">我们将使用它来说明我们目前了解到的概念。</span><span class="sxs-lookup"><span data-stu-id="327db-105">We're going to use this to illustrate the concepts we've learned so far.</span></span> <span data-ttu-id="327db-106">下面为不熟悉理论的用户提供了对量程 teleportation 的说明，后面是 Q # 中代码实现的演练。</span><span class="sxs-lookup"><span data-stu-id="327db-106">An explanation of quantum teleportation is provided below for those who are unfamiliar with the theory, followed by a walkthrough of the code implementation in Q#.</span></span> 

## <a name="quantum-teleportation-theory"></a><span data-ttu-id="327db-107">量程 Teleportation：理论</span><span class="sxs-lookup"><span data-stu-id="327db-107">Quantum Teleportation: Theory</span></span>
<span data-ttu-id="327db-108">量程 teleportation 是一种方法，用于将未知的量程状态（我们将称为 "__消息__"）从一个位置中的 qubit 发送到另一个位置中的 qubit （我们将分别指代为 "__此处__" 和 "__存在__" 的 qubits）。</span><span class="sxs-lookup"><span data-stu-id="327db-108">Quantum teleportation is a technique for sending an unknown quantum state (which we'll refer to as the '__message__') from a qubit in one location to a qubit in another location (we'll refer to these qubits as '__here__' and '__there__', respectively).</span></span> <span data-ttu-id="327db-109">我们可以使用 Dirac 表示法将__消息__表示为矢量：</span><span class="sxs-lookup"><span data-stu-id="327db-109">We can represent our __message__ as a vector using Dirac notation:</span></span> 

<span data-ttu-id="327db-110">$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $</span><span class="sxs-lookup"><span data-stu-id="327db-110">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="327db-111">__消息__qubit 的状态未知，因为我们不知道 $ \alpha $ 和 $ \beta $ 的值。</span><span class="sxs-lookup"><span data-stu-id="327db-111">The __message__ qubit's state is unknown to us as we do not know the values of $\alpha$ and $\beta$.</span></span>

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="327db-112">步骤1：创建放大状态</span><span class="sxs-lookup"><span data-stu-id="327db-112">Step 1: Create an entangled state</span></span>
<span data-ttu-id="327db-113">若要将 qubit 的__消息__发送到__此处__，需要在此处__放大 qubit。__</span><span class="sxs-lookup"><span data-stu-id="327db-113">In order to send the __message__ we need for the qubit __here__ to be entangled with the qubit __there__.</span></span> <span data-ttu-id="327db-114">为此，可应用 Hadamard 入口，后跟 CNOT-CONTAINS 入口。</span><span class="sxs-lookup"><span data-stu-id="327db-114">This is achieved by applying a Hadamard gate, followed by a CNOT gate.</span></span> <span data-ttu-id="327db-115">让我们看看这些入口操作背后的数学。</span><span class="sxs-lookup"><span data-stu-id="327db-115">Let's look at the math behind these gate operations.</span></span>

<span data-ttu-id="327db-116">我们将从__此处__ __开始，qubits__ $ \ket{0}$ 状态。</span><span class="sxs-lookup"><span data-stu-id="327db-116">We will begin with the qubits __here__ and __there__ both in the $\ket{0}$ state.</span></span> <span data-ttu-id="327db-117">Entangling 这些 qubits 后，它们处于以下状态：</span><span class="sxs-lookup"><span data-stu-id="327db-117">After entangling these qubits, they are in the state:</span></span>

<span data-ttu-id="327db-118">$ $ \ket{\phi ^ +} = \frac{1}{\sqrt{2}} （\ket{00} + \ket{11}） $ $</span><span class="sxs-lookup"><span data-stu-id="327db-118">$$ \ket{\phi^+} = \frac{1}{\sqrt{2}}(\ket{00} + \ket{11}) $$</span></span>

### <a name="step-2-send-the-message"></a><span data-ttu-id="327db-119">步骤2：发送消息</span><span class="sxs-lookup"><span data-stu-id="327db-119">Step 2: Send the message</span></span>
<span data-ttu-id="327db-120">若要发送该__消息__，我们首先将 cnot-contains 入口应用于__消息__qubit 和__此处__qubit 作为输入（此实例中的__消息__qubit 为控件，__此处__qubit 是目标 qubit。）</span><span class="sxs-lookup"><span data-stu-id="327db-120">To send the __message__ we first apply a CNOT gate with the __message__ qubit and __here__ qubit as inputs (the __message__ qubit being the control and the __here__ qubit being the target qubit, in this instance).</span></span> <span data-ttu-id="327db-121">可以写入此输入状态：</span><span class="sxs-lookup"><span data-stu-id="327db-121">This input state can be written:</span></span>

<span data-ttu-id="327db-122">$ $ \ket{\psi}\ket{\phi ^ +} = （\alpha\ket{0} + \beta\ket{1}）（\frac{1}{\sqrt{2}} （\ket{00} + \ket{11}）） $ $</span><span class="sxs-lookup"><span data-stu-id="327db-122">$$ \ket{\psi}\ket{\phi^+} = (\alpha\ket{0} + \beta\ket{1})(\frac{1}{\sqrt{2}}(\ket{00} + \ket{11})) $$</span></span>

<span data-ttu-id="327db-123">这会扩展到：</span><span class="sxs-lookup"><span data-stu-id="327db-123">This expands to:</span></span>

<span data-ttu-id="327db-124">$ $ \ket{\psi}\ket{\phi ^ +} = \frac{\alpha}{\sqrt{2}} \ket{000} + \frac{\alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{100} + \frac{\beta}{\sqrt{2}} \ket{111} $ $</span><span class="sxs-lookup"><span data-stu-id="327db-124">$$ \ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} + \frac{\beta}{\sqrt{2}}\ket{111} $$</span></span>

<span data-ttu-id="327db-125">作为提醒，当 control qubit 为1时，CNOT-CONTAINS 入口将翻转目标 qubit。</span><span class="sxs-lookup"><span data-stu-id="327db-125">As a reminder, the CNOT gate flips the target qubit when the control qubit is 1.</span></span> <span data-ttu-id="327db-126">例如，$ \ket{000}$ 的输入将导致第一个 qubit （控件）为0时不会发生任何更改。</span><span class="sxs-lookup"><span data-stu-id="327db-126">So for example, an input of $\ket{000}$ will result in no change as the first qubit (the control) is 0.</span></span> <span data-ttu-id="327db-127">但是，在第一个 qubit 为1的情况下，例如，$ \ket{100}$ 的输入。</span><span class="sxs-lookup"><span data-stu-id="327db-127">However, take a case where the first qubit is 1 - for example an input of $\ket{100}$.</span></span> <span data-ttu-id="327db-128">在此实例中，输出为 $ \ket{110}$，因为第二个 qubit （目标）由 CNOT-CONTAINS 入口翻转。</span><span class="sxs-lookup"><span data-stu-id="327db-128">In this instance, the output is $\ket{110}$ as the second qubit (the target) is flipped by the CNOT gate.</span></span>

<span data-ttu-id="327db-129">现在，让我们在 CNOT-CONTAINS 入口对以上输入进行操作后，立即考虑输出。</span><span class="sxs-lookup"><span data-stu-id="327db-129">Let's now consider our output once the CNOT gate has acted on our input above.</span></span> <span data-ttu-id="327db-130">结果为：</span><span class="sxs-lookup"><span data-stu-id="327db-130">The result is:</span></span>

<span data-ttu-id="327db-131">$ $ \frac{\alpha}{\sqrt{2}} \ket{000} + \frac{\alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{110} + \frac{\beta}{\sqrt{2}} \ket{101} $ $</span><span class="sxs-lookup"><span data-stu-id="327db-131">$$ \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{\beta}{\sqrt{2}}\ket{101} $$</span></span>

<span data-ttu-id="327db-132">发送该__消息__的下一步是将 Hadamard 入口应用到__消息__qubit （这是每个术语的第一 qubit）。</span><span class="sxs-lookup"><span data-stu-id="327db-132">The next step to send the __message__ is to apply a Hadamard gate to the __message__ qubit (that's the first qubit of each term).</span></span> 

<span data-ttu-id="327db-133">作为提醒，Hadamard 入口会执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="327db-133">As a reminder, the Hadamard gate does the following:</span></span>

<span data-ttu-id="327db-134">输入</span><span class="sxs-lookup"><span data-stu-id="327db-134">Input</span></span> | <span data-ttu-id="327db-135">输出</span><span class="sxs-lookup"><span data-stu-id="327db-135">Output</span></span>
---------------------------| ---------------------------------------------------------------
<span data-ttu-id="327db-136">$ \ket{0}$</span><span class="sxs-lookup"><span data-stu-id="327db-136">$\ket{0}$</span></span>  | <span data-ttu-id="327db-137">$ \frac{1}{\sqrt{2}} （\ket{0} + \ket{1}） $</span><span class="sxs-lookup"><span data-stu-id="327db-137">$\frac{1}{\sqrt{2}}(\ket{0} + \ket{1})$</span></span>
<span data-ttu-id="327db-138">$ \ket{1}$</span><span class="sxs-lookup"><span data-stu-id="327db-138">$\ket{1}$</span></span>  | <span data-ttu-id="327db-139">$ \frac{1}{\sqrt{2}} （\ket{0}-\ket{1}） $</span><span class="sxs-lookup"><span data-stu-id="327db-139">$\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})$</span></span>

<span data-ttu-id="327db-140">如果我们将 Hadamard 入口应用于上述输出每个术语的第一个 qubit，则会得到以下结果：</span><span class="sxs-lookup"><span data-stu-id="327db-140">If we apply the Hadamard gate to the first qubit of each term of our output above, we get the following result:</span></span>

<span data-ttu-id="327db-141">$ $ \frac{\alpha}{\sqrt{2}} （\frac{1}{\sqrt{2}} （\ket{0} + \ket{1}）） \ket{00} + \frac{\alpha}{\sqrt{2}} （\frac{1}{\sqrt{2}} （\ket{0} + \ket{1}）） \ket{11} + \frac{\beta}{\sqrt{2}} （\frac{1}{\sqrt{2}} （\ket{0}-\ket{1}）） \ket{10} + \frac{\beta}{\sqrt{2}} （\frac{1}{2}{0}）） \sqrt{1}$ $</span><span class="sxs-lookup"><span data-stu-id="327db-141">$$ \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{00} + \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{11} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{10} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{01} $$</span></span>

<span data-ttu-id="327db-142">请注意，每个术语都有 $2 \frac{1}{\sqrt{2}} $ 系数。</span><span class="sxs-lookup"><span data-stu-id="327db-142">Note that each term has two $\frac{1}{\sqrt{2}}$ factors.</span></span> <span data-ttu-id="327db-143">我们可以将这些结果相乘，结果如下：</span><span class="sxs-lookup"><span data-stu-id="327db-143">We can multiply these out giving the following result:</span></span>

<span data-ttu-id="327db-144">$ $ \frac{\alpha}{2}（\ket{0} + \ket{1}） \ket{00} + \frac{\alpha}{2}（\ket{0} + \ket{1}） \ket{11} + \frac{\beta}{2}（\ket{0}-\ket{1}） \ket{10} + \frac{\beta}{2}（\ket{0}-\ket{1}） \ket{01} $ $</span><span class="sxs-lookup"><span data-stu-id="327db-144">$$ \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{11} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{10} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{01} $$</span></span>

<span data-ttu-id="327db-145">$ \Frac{1}{2}$ 系数对于每个术语都是通用的，因此我们现在可以将其移到方括号以外：</span><span class="sxs-lookup"><span data-stu-id="327db-145">The  $\frac{1}{2}$ factor is common to each term so we can now take it outside the brackets:</span></span>

<span data-ttu-id="327db-146">$ $ \frac{1}{2}\big [\alpha （\ket{0} + \ket{1}） \ket{00} + \alpha （\ket{0} + \ket{1}） \ket{11} + \beta （\ket{0}-\ket{1}） \ket{10} \beta] $ $</span><span class="sxs-lookup"><span data-stu-id="327db-146">$$ \frac{1}{2}\big[\alpha(\ket{0} + \ket{1})\ket{00} + \alpha(\ket{0} + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket{01}\big] $$</span></span>

<span data-ttu-id="327db-147">然后，可以将每个术语的方括号相乘，提供：</span><span class="sxs-lookup"><span data-stu-id="327db-147">We can then multiply out the brackets for each term giving:</span></span>

<span data-ttu-id="327db-148">$ $ \frac{1}{2}\big [\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010}-\beta\ket{110} + \beta\ket{001}-\beta\ket{101}\big] $ $</span><span class="sxs-lookup"><span data-stu-id="327db-148">$$ \frac{1}{2}\big[\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} - \beta\ket{110} + \beta\ket{001} - \beta\ket{101}\big] $$</span></span>

### <a name="step-3-measure-the-result"></a><span data-ttu-id="327db-149">步骤3：度量结果</span><span class="sxs-lookup"><span data-stu-id="327db-149">Step 3: Measure the result</span></span>

<span data-ttu-id="327db-150">由于__这里__ __有__放大，__这里__的任何度量都将影响其__状态。__</span><span class="sxs-lookup"><span data-stu-id="327db-150">Due to __here__ and __there__ being entangled, any measurement on __here__ will affect the state of __there__.</span></span> <span data-ttu-id="327db-151">如果我们度量第一个和第二个 qubit （__message__和__此处__），我们可以通过牵连的此属性了解上__有__什么状态。</span><span class="sxs-lookup"><span data-stu-id="327db-151">If we measure the first and second qubit (__message__ and __here__) we can learn what state __there__ is in, due to this property of entanglement.</span></span> 

* <span data-ttu-id="327db-152">如果度量并获得结果00，则 superposition 会折叠，只保留与此结果一致的术语。</span><span class="sxs-lookup"><span data-stu-id="327db-152">If we measure and get a result 00, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="327db-153">这是 $ \alpha\ket{000} + \beta\ket{001}$。</span><span class="sxs-lookup"><span data-stu-id="327db-153">That's $\alpha\ket{000} +\beta\ket{001}$.</span></span> <span data-ttu-id="327db-154">这可以重构为 $ \ket{00}（\alpha\ket{0} + \beta\ket{1}） $。</span><span class="sxs-lookup"><span data-stu-id="327db-154">This can be refactored to $\ket{00}(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="327db-155">因此，如果我们将第一个和第二个 qubit 度量值为__00，我们__知道第三个 qubit 处于状态 $ （\alpha\ket{0} + \beta\ket{1}） $。</span><span class="sxs-lookup"><span data-stu-id="327db-155">Therefore if we measure the first and second qubit to be 00, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="327db-156">如果度量并获得结果01，则 superposition 会折叠，只保留与此结果一致的条款。</span><span class="sxs-lookup"><span data-stu-id="327db-156">If we measure and get a result 01, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="327db-157">这是 $ \alpha\ket{011} + \beta\ket{010}$。</span><span class="sxs-lookup"><span data-stu-id="327db-157">That's $\alpha\ket{011} +\beta\ket{010}$.</span></span> <span data-ttu-id="327db-158">这可以重构为 $ \ket{01}（\alpha\ket{1} + \beta\ket{0}） $。</span><span class="sxs-lookup"><span data-stu-id="327db-158">This can be refactored to $\ket{01}(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="327db-159">因此，如果我们将第一个和第二个 qubit 度量为__01，我们__知道第三个 qubit 处于状态 $ （\alpha\ket{1} + \beta\ket{0}） $。</span><span class="sxs-lookup"><span data-stu-id="327db-159">Therefore if we measure the first and second qubit to be 01, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span>
* <span data-ttu-id="327db-160">如果度量并获得结果10，则 superposition 会折叠，只保留与此结果一致的条款。</span><span class="sxs-lookup"><span data-stu-id="327db-160">If we measure and get a result 10, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="327db-161">这是 $ \alpha\ket{100}-\beta\ket{101}$。</span><span class="sxs-lookup"><span data-stu-id="327db-161">That's $\alpha\ket{100} -\beta\ket{101}$.</span></span> <span data-ttu-id="327db-162">这可以重构为 $ \ket{10}（\alpha\ket{0}-\beta\ket{1}） $。</span><span class="sxs-lookup"><span data-stu-id="327db-162">This can be refactored to $\ket{10}(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="327db-163">因此，如果我们将第一个和第二个 qubit 度量值为__10，我们__知道第三个 qubit 处于状态 $ （\alpha\ket{0}-\beta\ket{1}） $。</span><span class="sxs-lookup"><span data-stu-id="327db-163">Therefore if we measure the first and second qubit to be 10, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span>
* <span data-ttu-id="327db-164">如果度量并获得结果11，则 superposition 会折叠，只保留与此结果一致的条款。</span><span class="sxs-lookup"><span data-stu-id="327db-164">If we measure and get a result 11, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="327db-165">这是 $ \alpha\ket{111}-\beta\ket{110}$。</span><span class="sxs-lookup"><span data-stu-id="327db-165">That's $\alpha\ket{111} -\beta\ket{110}$.</span></span> <span data-ttu-id="327db-166">这可以重构为 $ \ket{11}（\alpha\ket{1}-\beta\ket{0}） $。</span><span class="sxs-lookup"><span data-stu-id="327db-166">This can be refactored to $\ket{11}(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="327db-167">因此，如果我们将第一个和第二个 qubit 测量为 11 __，则我们__知道第三个 qubit 处于状态 $ （\alpha\ket{1}-\beta\ket{0}） $。</span><span class="sxs-lookup"><span data-stu-id="327db-167">Therefore if we measure the first and second qubit to be 11, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span>

### <a name="step-4-interpret-the-result"></a><span data-ttu-id="327db-168">步骤4：解释结果</span><span class="sxs-lookup"><span data-stu-id="327db-168">Step 4: Interpret the result</span></span>

<span data-ttu-id="327db-169">作为提醒，我们希望发送的原始__消息__为：</span><span class="sxs-lookup"><span data-stu-id="327db-169">As a reminder, the original __message__ we wished to send was:</span></span>

<span data-ttu-id="327db-170">$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $</span><span class="sxs-lookup"><span data-stu-id="327db-170">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="327db-171">我们需要在此状态中__获取 qubit，__ 以便接收状态是预期的状态。</span><span class="sxs-lookup"><span data-stu-id="327db-171">We need to get the __there__ qubit into this state, so that the received state is the one that was intended.</span></span> 

* <span data-ttu-id="327db-172">如果我们测量并得到00的__结果，则__第三个 qubit 的状态为 $ （\alpha\ket{0} + \beta\ket{1}） $。</span><span class="sxs-lookup"><span data-stu-id="327db-172">If we measured and got a result of 00, then the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="327db-173">由于这是预期__消息__，不需要进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="327db-173">As this is the intended __message__, no alteration is required.</span></span>
* <span data-ttu-id="327db-174">如果度量结果为__01，则__第三个 qubit 处于状态 $ （\alpha\ket{1} + \beta\ket{0}） $。</span><span class="sxs-lookup"><span data-stu-id="327db-174">If we measured and got a result of 01, then the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="327db-175">这不同于预期的__消息__，但是应用 NOT 入口会给我们提供所需状态 $ （\alpha\ket{0} + \beta\ket{1}） $。</span><span class="sxs-lookup"><span data-stu-id="327db-175">This differs from the intended __message__, however applying a NOT gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="327db-176">如果度量结果为__10，则__第三个 qubit 处于状态 $ （\alpha\ket{0}-\beta\ket{1}） $。</span><span class="sxs-lookup"><span data-stu-id="327db-176">If we measured and got a result of 10, then the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="327db-177">这不同于预期的__消息__，但是，应用 Z 门将为我们提供所需状态 $ （\alpha\ket{0} + \beta\ket{1}） $。</span><span class="sxs-lookup"><span data-stu-id="327db-177">This differs from the intended __message__, however applying a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="327db-178">如果度量结果为__11，则__第三个 qubit 处于状态 $ （\alpha\ket{1}-\beta\ket{0}） $。</span><span class="sxs-lookup"><span data-stu-id="327db-178">If we measured and got a result of 11, then the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="327db-179">这不同于预期的__消息__，但应用 "NOT" 后跟 Z 门会为我们提供所需状态 $ （\alpha\ket{0} + \beta\ket{1}） $。</span><span class="sxs-lookup"><span data-stu-id="327db-179">This differs from the intended __message__, however applying a NOT gate followed by a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>

<span data-ttu-id="327db-180">总而言之，如果度量值为1，并且第一个 qubit 为1，则应用 Z 入口。</span><span class="sxs-lookup"><span data-stu-id="327db-180">To summarize, if we measure and the first qubit is 1, a Z gate is applied.</span></span> <span data-ttu-id="327db-181">如果度量值为1，第二个 qubit 为1，则应用 NOT 入口。</span><span class="sxs-lookup"><span data-stu-id="327db-181">If we measure and the second qubit is 1, a NOT gate is applied.</span></span>

### <a name="summary"></a><span data-ttu-id="327db-182">摘要</span><span class="sxs-lookup"><span data-stu-id="327db-182">Summary</span></span>
<span data-ttu-id="327db-183">下面显示了一个用于实现 teleportation 的短信量程线路。</span><span class="sxs-lookup"><span data-stu-id="327db-183">Shown below is a text-book quantum circuit that implements the teleportation.</span></span> <span data-ttu-id="327db-184">从左到右移动可以看到：</span><span class="sxs-lookup"><span data-stu-id="327db-184">Moving from left to right you can see:</span></span>
- <span data-ttu-id="327db-185">步骤 1 __：通过应用__Hadamard__入口和 Cnot-contains 入口，Entangling。__</span><span class="sxs-lookup"><span data-stu-id="327db-185">Step 1: Entangling __here__ and __there__ by applying a Hadamard gate and CNOT gate.</span></span>
- <span data-ttu-id="327db-186">步骤2：使用 CNOT-CONTAINS 入口和 Hadamard 入口发送__消息__。</span><span class="sxs-lookup"><span data-stu-id="327db-186">Step 2: Sending the __message__ using a CNOT gate and a Hadamard gate.</span></span>
- <span data-ttu-id="327db-187">步骤3：度量第一个和第二个 qubits、__消息__和__此处__。</span><span class="sxs-lookup"><span data-stu-id="327db-187">Step 3: Taking a measurement of the first and second qubits, __message__ and __here__.</span></span>
- <span data-ttu-id="327db-188">步骤4：应用 NOT 入口或 Z 门，具体取决于步骤3中的测量结果。</span><span class="sxs-lookup"><span data-stu-id="327db-188">Step 4: Applying a NOT gate or a Z gate, depending on the result of the measurement in step 3.</span></span>

!["传送（msg： Qubit，存在： Qubit）： Unit"](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a><span data-ttu-id="327db-190">量程 Teleportation：代码</span><span class="sxs-lookup"><span data-stu-id="327db-190">Quantum Teleportation: Code</span></span>

<span data-ttu-id="327db-191">我们的线路用于量程 teleportation：</span><span class="sxs-lookup"><span data-stu-id="327db-191">We have our circuit for quantum teleportation:</span></span>

!["传送（msg： Qubit，存在： Qubit）： Unit"](~/media/teleportation.svg)

<span data-ttu-id="327db-193">现在，我们可以将该量程线路中的每个步骤都转换为 Q #。</span><span class="sxs-lookup"><span data-stu-id="327db-193">We can now translate each of the steps in this quantum circuit into Q#.</span></span>

### <a name="step-0-definition"></a><span data-ttu-id="327db-194">步骤0：定义</span><span class="sxs-lookup"><span data-stu-id="327db-194">Step 0: Definition</span></span>
<span data-ttu-id="327db-195">执行 teleportation 时，我们必须知道要发送的消息，以及要将__消息__发送到的位置。</span><span class="sxs-lookup"><span data-stu-id="327db-195">When we perform teleportation, we must know the __message__ we wish to send, and where we wish to send it (__there__).</span></span> <span data-ttu-id="327db-196">出于此原因，我们首先定义一个新的传送操作，该操作将给定两个 qubits 作为参数，`msg` 和 `there`：</span><span class="sxs-lookup"><span data-stu-id="327db-196">For this reason, we begin by defining a new Teleport operation that is given two qubits as arguments, `msg` and `there`:</span></span>

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

<span data-ttu-id="327db-197">我们还需要使用 `using` 块来分配 qubit `here`：</span><span class="sxs-lookup"><span data-stu-id="327db-197">We also need to allocate a qubit `here` which we achieve with a `using` block:</span></span>

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="327db-198">步骤1：创建放大状态</span><span class="sxs-lookup"><span data-stu-id="327db-198">Step 1: Create an entangled state</span></span>
<span data-ttu-id="327db-199">然后，可以使用 @"microsoft.quantum.intrinsic.h" 和 @"microsoft.quantum.intrinsic.cnot" 操作在 `here` 和 `there` 之间创建放大对：</span><span class="sxs-lookup"><span data-stu-id="327db-199">We can then create the entangled pair between `here` and `there` by using the @"microsoft.quantum.intrinsic.h" and @"microsoft.quantum.intrinsic.cnot" operations:</span></span>

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a><span data-ttu-id="327db-200">步骤2：发送消息</span><span class="sxs-lookup"><span data-stu-id="327db-200">Step 2: Send the message</span></span>
<span data-ttu-id="327db-201">然后，使用下一个 $ \operatorname{CNOT} $ 和 $H $ 关口来移动消息 qubit：</span><span class="sxs-lookup"><span data-stu-id="327db-201">We then use the next $\operatorname{CNOT}$ and $H$ gates to move our message qubit:</span></span>

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a><span data-ttu-id="327db-202">步骤 3 & 4：测量和解释结果</span><span class="sxs-lookup"><span data-stu-id="327db-202">Step 3 & 4: Measuring and interpreting the result</span></span>
<span data-ttu-id="327db-203">最后，我们使用 @"microsoft.quantum.intrinsic.m" 执行度量，并执行必要的入口操作以获取所需状态，如 `if` 语句所示：</span><span class="sxs-lookup"><span data-stu-id="327db-203">Finally, we use @"microsoft.quantum.intrinsic.m" to perform the measurements and perform the necessary gate operations to get the desired state, as denoted by `if` statements:</span></span>

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

<span data-ttu-id="327db-204">这将完成 teleportation 运算符的定义，因此，我们可以释放 `here`、结束正文并结束操作。</span><span class="sxs-lookup"><span data-stu-id="327db-204">This finishes the definition of our teleportation operator, so we can deallocate `here`, end the body, and end the operation.</span></span>

```qsharp
    }
}
```
