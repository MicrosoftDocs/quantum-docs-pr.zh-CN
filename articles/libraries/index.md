---
title: Quantum 开发工具包库
description: 概述 Microsoft Quantum 开发工具包中包含的标准库、化学库和数值库。
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries
ms.openlocfilehash: 89612aaa5c11e1a5e0d418256e96366953fdd3fe
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906400"
---
# <a name="overview-of-q-libraries"></a><span data-ttu-id="08587-103">Q# 库概述</span><span class="sxs-lookup"><span data-stu-id="08587-103">Overview of Q# Libraries</span></span>
<span data-ttu-id="08587-104">量子开发工具包附带几个库，让在 Q# 中开发量子应用程序变得更轻松。</span><span class="sxs-lookup"><span data-stu-id="08587-104">The Quantum Development Kit is provided with several libraries to make it easier to develop quantum applications in Q#.</span></span>
<span data-ttu-id="08587-105">在文档的此部分中，我们介绍了这些库，以及如何在程序中使用这些库。</span><span class="sxs-lookup"><span data-stu-id="08587-105">In this section of the documentation, we describe these libraries and how to use them in your programs.</span></span>

- <span data-ttu-id="08587-106">[**标准库**](xref:microsoft.quantum.libraries.standard.intro)：此部分介绍 prelude 和 canon。prelude 定义 Q# 程序与目标计算机之间的接口，canon 是一个 Q# 库，提供用于编写 Q# 程序的常规操作和函数。</span><span class="sxs-lookup"><span data-stu-id="08587-106">[**Standard libraries**](xref:microsoft.quantum.libraries.standard.intro): This section describes the prelude, which defines the interface between Q# programs and target machines, and the canon, a Q# library that provides general-purpose operations and functions for use in writing Q# programs.</span></span>
- <span data-ttu-id="08587-107">[**量子化学库**](xref:microsoft.quantum.chemistry.concepts.intro)：本部分介绍量子化学库，该库提供了一个数据模型，用于加载 Hamiltonians 费米子的表示形式和用于处理这些表示形式的量子模拟操作和函数。</span><span class="sxs-lookup"><span data-stu-id="08587-107">[**Quantum chemistry library**](xref:microsoft.quantum.chemistry.concepts.intro): This section describes the quantum chemistry library, which provides a data model for loading representations of fermionic Hamiltonians and quantum simulation operations and functions which act on these representations.</span></span>
- <span data-ttu-id="08587-108">[**量子数字库**](xref:microsoft.quantum.numerics.intro)：本部分介绍量子数字库，该库可以实现众多数学函数。</span><span class="sxs-lookup"><span data-stu-id="08587-108">[**Quantum numerics library**](xref:microsoft.quantum.numerics.intro): This section describes the quantum numerics library, which provides implementations for a host of mathematical functions.</span></span> <span data-ttu-id="08587-109">它支持整数（有符号和无符号）和定点表示形式。</span><span class="sxs-lookup"><span data-stu-id="08587-109">It supports integer (signed & unsigned) and fixed-point representations.</span></span>

<span data-ttu-id="08587-110">从 GitHub 可以获取库和代码示例的原始资料。</span><span class="sxs-lookup"><span data-stu-id="08587-110">Sources of the libraries as well as code samples can be obtained from GitHub.</span></span> <span data-ttu-id="08587-111">有关详细信息，另请参阅[许可](xref:microsoft.quantum.libraries.licensing)部分。</span><span class="sxs-lookup"><span data-stu-id="08587-111">See also the [licensing](xref:microsoft.quantum.libraries.licensing) section for further information.</span></span> <span data-ttu-id="08587-112">请注意，包引用（“二进制”）也适用于库，因此提供了在项目中添加库的另一种方法。</span><span class="sxs-lookup"><span data-stu-id="08587-112">It should be noted that package references ("binaries") are available also for the libraries which offers another way of including the libraries in projects.</span></span> <span data-ttu-id="08587-113">通过使用 [nuget](https://nuget.org) 可以方便地获取这些资源。</span><span class="sxs-lookup"><span data-stu-id="08587-113">A convenient way of obtaining them is via [nuget](https://nuget.org).</span></span>
