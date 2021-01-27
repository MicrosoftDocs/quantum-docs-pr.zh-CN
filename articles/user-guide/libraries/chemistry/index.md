---
title: 量子化学库简介
description: 了解 Microsoft 量子化学库，以及如何使用它来模拟量子计算机上的电子结构问题。
author: QuantumWriter
ms.author: ageller
ms.date: 12/11/2017
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3fa606600db1641b9f8b86ccefebb7681f181b92
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847489"
---
# <a name="introduction-to-the-quantum-chemistry-library"></a><span data-ttu-id="c9089-103">量子化学库简介</span><span class="sxs-lookup"><span data-stu-id="c9089-103">Introduction to the Quantum Chemistry Library</span></span>

<span data-ttu-id="c9089-104">长期以来，物理系统的模拟在量子计算中一直发挥着核心作用。</span><span class="sxs-lookup"><span data-stu-id="c9089-104">Simulation of physical systems has long played a central role in quantum computing.</span></span>  <span data-ttu-id="c9089-105">这是因为人们普遍认为，量子动力学很难在量子计算机上模拟，这意味着模拟系统的复杂性会随着所讨论的量子系统的大小呈指数增长。</span><span class="sxs-lookup"><span data-stu-id="c9089-105">This is because quantum dynamics are widely believed to be intractable to simulate on quantum computers, meaning that the complexity of simulating the system scales exponentially with the size of the quantum system in question.</span></span>  <span data-ttu-id="c9089-106">模拟化学和材料科学中的问题可能仍然是量子计算中最令人回味的应用，我们借此能够探索迄今为止我们无法测量或模拟的化学反应机制。</span><span class="sxs-lookup"><span data-stu-id="c9089-106">Simulating problems in chemistry and material science remains perhaps the most evocative application of quantum computing and would allow us to probe chemical reaction mechanisms that hitherto were beyond our ability to measure or simulate.</span></span>  <span data-ttu-id="c9089-107">我们借此还可以模拟相关的电子材料，例如高温超导体。</span><span class="sxs-lookup"><span data-stu-id="c9089-107">It would also allow us to simulate correlated electronic materials such as high-temperature superconductors.</span></span> <span data-ttu-id="c9089-108">该技术在此领域的应用非常宽广。</span><span class="sxs-lookup"><span data-stu-id="c9089-108">The list of applications in this space is vast.</span></span>

<span data-ttu-id="c9089-109">本文档的目的是简要介绍如何在量子计算机上模拟电子结构问题，帮助读者理解 Hamiltonian 模拟库在该领域的许多方面发挥的作用。</span><span class="sxs-lookup"><span data-stu-id="c9089-109">The purpose of this documentation is to provide a concise introduction to simulating electronic structure problems on quantum computers in order to help the reader understand the role that many aspects of the Hamiltonian simulation library play within the space.</span></span>  <span data-ttu-id="c9089-110">我们首先简要介绍量子力学，然后讨论如何在其中构建电子系统模型。</span><span class="sxs-lookup"><span data-stu-id="c9089-110">We begin with a brief introduction to quantum mechanics and then proceed to discuss how electronic systems are modeled in it.</span></span>  <span data-ttu-id="c9089-111">然后，我们将讨论如何使用量子计算机来模拟此类量子动力学。</span><span class="sxs-lookup"><span data-stu-id="c9089-111">We will then discuss how such quantum dynamics can be emulated using a quantum computer.</span></span>  <span data-ttu-id="c9089-112">完成后，我们将讨论两种用于将量子动力学编译为基本门序列的方法：Trotter-Suzuki 分解和量子位化。</span><span class="sxs-lookup"><span data-stu-id="c9089-112">Once this is complete we will discuss two methods used to compile the quantum dynamics to sequences of elementary gates: Trotter-Suzuki decompositions and qubitization.</span></span>
