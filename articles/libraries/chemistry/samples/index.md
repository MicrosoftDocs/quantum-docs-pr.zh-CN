---
title: 量子化学示例 | Microsoft Docs
description: 量子化学示例文档
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples
ms.openlocfilehash: 586ea98321ff71947df8d81a2141a8b050dbd9ed
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2019
ms.locfileid: "72960400"
---
# <a name="quantum-chemistry-examples"></a><span data-ttu-id="32037-103">量子化学示例</span><span class="sxs-lookup"><span data-stu-id="32037-103">Quantum chemistry examples</span></span>

<span data-ttu-id="32037-104">在量子化学概念中，我们手动构造了示例 Hamiltonian 费米子。</span><span class="sxs-lookup"><span data-stu-id="32037-104">In the quantum chemistry concepts, we manually constructed example fermion Hamiltonians.</span></span> <span data-ttu-id="32037-105">现将[模拟 Hamiltonian 动力学](xref:microsoft.quantum.libraries.standard.algorithms)中概述的化学模拟算法与 canon 库中的[量子相位估计](xref:microsoft.quantum.libraries.characterization)结合起来。</span><span class="sxs-lookup"><span data-stu-id="32037-105">We now combine the chemistry simulation algorithms outlined in [Simulating Hamiltonian dynamics](xref:microsoft.quantum.libraries.standard.algorithms) with [quantum phase estimation](xref:microsoft.quantum.libraries.characterization) in the canon library.</span></span> <span data-ttu-id="32037-106">通过这种结合，我们能够获取所表示的分子中的能级估计值，这是量子化学在量子计算机上的关键应用之一。</span><span class="sxs-lookup"><span data-stu-id="32037-106">This combination allows us to obtain  estimates of energy levels in the represented molecule, which is one of the key applications of quantum chemistry on a quantum computer.</span></span> 

<span data-ttu-id="32037-107">我们还研究了一些可以实现大规模量子化学实验的示例，但没有逐个指定 Hamiltonian 的术语。</span><span class="sxs-lookup"><span data-stu-id="32037-107">Instead of specifying terms of the Hamiltonian one-by-one, we also work through some examples that allow us to perform quantum chemistry experiments at scale.</span></span> <span data-ttu-id="32037-108">我们首先研究用于加载以 [Broombridge 架构](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)编码的化学 Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="32037-108">We begin with examples that load a chemistry Hamiltonian encoded in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).</span></span>

<span data-ttu-id="32037-109">对于因太大而无法在[完全状态模拟器](xref:microsoft.quantum.machines.full-state-simulator)上进行模拟的分子，仍可执行有趣的科学研究。</span><span class="sxs-lookup"><span data-stu-id="32037-109">For molecules that are too large to simulate on the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), interesting science can still be performed.</span></span> <span data-ttu-id="32037-110">例如，通过将[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)设为目标，仍可以评估执行大型化学模拟的资源成本。</span><span class="sxs-lookup"><span data-stu-id="32037-110">For instance, the resource costs of performing large chemistry simulations may still be evaluated by targeting the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>

<span data-ttu-id="32037-111">现在，让我们通过几个提供的示例解释化学模拟库的有趣应用。</span><span class="sxs-lookup"><span data-stu-id="32037-111">Let us now illustrate interesting applications of the chemistry simulation library through a few of the provided samples.</span></span>