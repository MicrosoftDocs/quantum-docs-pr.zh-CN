---
title: 创建量子随机数生成器
description: 生成一个 Q# 项目，通过创建量子随机数生成器来演示基本的量子概念（例如叠加）。
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: c3039b92c4b3235a397d5cf31280ac2673706e9d
ms.sourcegitcommit: 2ca4755d1a63431e3cb2d2918a10ad477ec2e368
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73462834"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="22901-103">快速入门：在 Q# 中实现量子随机数生成器</span><span class="sxs-lookup"><span data-stu-id="22901-103">Quickstart: Implement a Quantum Random Number Generator in Q#</span></span>
<span data-ttu-id="22901-104">以 Q# 编写的量子算法的一个简单示例是量子随机数生成器。</span><span class="sxs-lookup"><span data-stu-id="22901-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="22901-105">此算法利用量子力学特性来生成随机数。</span><span class="sxs-lookup"><span data-stu-id="22901-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="22901-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="22901-106">Prerequisites</span></span>

- <span data-ttu-id="22901-107">Microsoft [Quantum 开发工具包](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="22901-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- [<span data-ttu-id="22901-108">创建 Q# 项目</span><span class="sxs-lookup"><span data-stu-id="22901-108">Create a Q# Project</span></span>](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a><span data-ttu-id="22901-109">编写 Q# 运算</span><span class="sxs-lookup"><span data-stu-id="22901-109">Write a Q# operation</span></span>

### <a name="q-operation-code"></a><span data-ttu-id="22901-110">Q# 运算代码</span><span class="sxs-lookup"><span data-stu-id="22901-110">Q# operation code</span></span>

1. <span data-ttu-id="22901-111">将 Operation.qs 文件的内容替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="22901-111">Replace the contents of the Operation.qs file with the following code:</span></span>

    ```qsharp
    namespace Quantum {
        open Microsoft.Quantum.Intrinsic;

        operation QuantumRandomNumberGenerator() : Result {
            using(q = Qubit())  { // Allocate a qubit.
                H(q);             // Put the qubit to superposition. It now has a 50% chance of being 0 or 1.
                let r = M(q);     // Measure the qubit value.
                Reset(q);
                return r;
            }
        }
    }
    ```

<span data-ttu-id="22901-112">如 [What is Quantum Computing?](xref:microsoft.quantum.overview.what)（什么是量子计算？）一文所述，量子位是可以处于叠加态的量子信息单元。</span><span class="sxs-lookup"><span data-stu-id="22901-112">As mentioned in our [What is Quantum Computing?](xref:microsoft.quantum.overview.what) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="22901-113">度量时，量子位只能是 0 或 1。</span><span class="sxs-lookup"><span data-stu-id="22901-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="22901-114">但在执行时，量子位的状态表示进行度量时读取值为 0 或 1 的概率。</span><span class="sxs-lookup"><span data-stu-id="22901-114">However, during execution the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="22901-115">此概率状态称为叠加。</span><span class="sxs-lookup"><span data-stu-id="22901-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="22901-116">我们可以根据此概率生成随机数。</span><span class="sxs-lookup"><span data-stu-id="22901-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="22901-117">在 Q# 操作中，我们引入了 Q# 原生的 `Qubit` 数据类型。</span><span class="sxs-lookup"><span data-stu-id="22901-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="22901-118">我们只能通过 `using` 语句来分配 `Qubit`。</span><span class="sxs-lookup"><span data-stu-id="22901-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="22901-119">分配后，量子位始终处于 `Zero` 状态。</span><span class="sxs-lookup"><span data-stu-id="22901-119">When it gets allocated a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="22901-120">我们可以使用 `H` 操作将 `Qubit` 置于叠加态。</span><span class="sxs-lookup"><span data-stu-id="22901-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="22901-121">若要度量某个量子位并读取其值，请使用 `M` 内部操作。</span><span class="sxs-lookup"><span data-stu-id="22901-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="22901-122">将 `Qubit` 置于叠加态并对其进行度量以后，每次调用代码时，我们的结果都会是一个不同值。</span><span class="sxs-lookup"><span data-stu-id="22901-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span> 

<span data-ttu-id="22901-123">取消分配 `Qubit` 时，必须将其显式设置回 `Zero` 状态，否则模拟器会报告运行时错误。</span><span class="sxs-lookup"><span data-stu-id="22901-123">When a `Qubit` is de-allocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="22901-124">实现此目的的一种简单方法是调用 `Reset`。</span><span class="sxs-lookup"><span data-stu-id="22901-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="22901-125">使用 Bloch 球将代码可视化</span><span class="sxs-lookup"><span data-stu-id="22901-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="22901-126">在 Bloch 球中，北极表示经典值 **0**，南极表示经典值 **1**。</span><span class="sxs-lookup"><span data-stu-id="22901-126">In the Bloch sphere the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="22901-127">任何叠加态都可以用球上的某个点来表示（用箭头表示）。</span><span class="sxs-lookup"><span data-stu-id="22901-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="22901-128">箭头末端越靠近极点，量子位塌缩成经典值（在度量时分配给该极点）的概率越高。</span><span class="sxs-lookup"><span data-stu-id="22901-128">When the closer the end of the arrow to a pole, the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="22901-129">例如，下面的红色箭头表示的量子位状态在我们度量它时有较高的概率给出值 **0**。</span><span class="sxs-lookup"><span data-stu-id="22901-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="./Bloch.svg" width="175">

<span data-ttu-id="22901-130">我们可以使用此表示法将代码的功能可视化：</span><span class="sxs-lookup"><span data-stu-id="22901-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="22901-131">首先，我们一开始的量子位初始化为状态 **0**，对其应用 `H` 后会产生一个叠加态，其中获得 **0** 和 **1** 的概率相同。</span><span class="sxs-lookup"><span data-stu-id="22901-131">First we start with a qubit initalizated in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="./H.svg" width="450">

* <span data-ttu-id="22901-132">然后，我们度量该量子位并保存输出：</span><span class="sxs-lookup"><span data-stu-id="22901-132">Then we measure the qubit and save the output:</span></span>

<img src="./Measurement2.svg" width="450">

<span data-ttu-id="22901-133">由于度量结果是完全随机的，我们获得了一个随机位。</span><span class="sxs-lookup"><span data-stu-id="22901-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="22901-134">我们可以调用此操作多次来创建多个整数。</span><span class="sxs-lookup"><span data-stu-id="22901-134">We can call this operation several times to create integers.</span></span> <span data-ttu-id="22901-135">例如，如果我们调用此操作三次来获取三个随机位，我们就可以生成随机的 3 位数（即 0 到 7 之间的随机数）。</span><span class="sxs-lookup"><span data-stu-id="22901-135">For example, if we call the operation three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>
