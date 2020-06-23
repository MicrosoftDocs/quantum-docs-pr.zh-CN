---
title: 量子数字库简介 | Microsoft Docs
description: 量子数字库简介
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.intro
ms.openlocfilehash: efd1a712616534ac281433fc008f0983271881d7
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273283"
---
# <a name="introduction-to-the-quantum-numerics-library"></a><span data-ttu-id="de56b-103">量子数字库简介</span><span class="sxs-lookup"><span data-stu-id="de56b-103">Introduction to the Quantum Numerics Library</span></span>

<span data-ttu-id="de56b-104">许多量子算法依赖于 [oracle](xref:microsoft.quantum.concepts.oracles)，可通过叠加输入来计算数学函数。</span><span class="sxs-lookup"><span data-stu-id="de56b-104">Many quantum algorithms rely on [oracles](xref:microsoft.quantum.concepts.oracles) that evaluate mathematical functions on a superposition of inputs.</span></span>
<span data-ttu-id="de56b-105">例如，秀尔算法的主成分使用固定的 $a$，赋予数值的因子 $N$，以及 $x$ 一个在所有 $2n$ 位字符串上一致叠加的 $2n$ 量子位整数，求 $f(x) = a^x\operatorname{mod} N$ 的值。</span><span class="sxs-lookup"><span data-stu-id="de56b-105">The main component of Shor's algorithm, for example, evaluates $f(x) = a^x\operatorname{mod} N$ for a fixed $a$, the number to factor $N$, and $x$ a $2n$-qubit integer in a uniform superposition over all $2n$-bit strings.</span></span>

<span data-ttu-id="de56b-106">若要在实际量子计算机上运行秀尔算法，则必须根据目标计算机的本机操作编写此函数。</span><span class="sxs-lookup"><span data-stu-id="de56b-106">To run Shor's algorithm on an actual quantum computer, this function has to be written in terms of the native operations of the target machine.</span></span>
<span data-ttu-id="de56b-107">使用 $x$ 的二进制表示形式，其中 $x_i$ 表示从最低有效位开始计数的第 $i$ 位，$f(x)$ 可以写为 $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$。</span><span class="sxs-lookup"><span data-stu-id="de56b-107">Using the binary representation of $x$ with $x_i$ denoting the $i$-th bit counting from the least-significant bit, $f(x)$ can be written as $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$.</span></span>
<span data-ttu-id="de56b-108">反过来，这可以写为 $a^{2^i x_i}=(a^{2^i})^{x_i}$ 术语的产品 (mod N)。</span><span class="sxs-lookup"><span data-stu-id="de56b-108">In turn, this can be written as a product (mod N) of terms $a^{2^i x_i}=(a^{2^i})^{x_i}$.</span></span> <span data-ttu-id="de56b-109">因此，函数 $f(x)$ 可以使用 $2n$（模）乘序列来实现，其中 $a^{2^i}$ 为条件，$x_i$ 为非零值。</span><span class="sxs-lookup"><span data-stu-id="de56b-109">The function $f(x)$ can thus be implemented using a sequence of $2n$ (modular) multiplications by $a^{2^i}$ conditional on $x_i$ being nonzero.</span></span> <span data-ttu-id="de56b-110">在运行该算法之前，常量 $a^{2^i}$ 可以预计算并规约取模 N。</span><span class="sxs-lookup"><span data-stu-id="de56b-110">The constants $a^{2^i}$ can be precomputed and reduced modulo N before running the algorithm.</span></span>

<span data-ttu-id="de56b-111">可以进一步简化此受控模乘的序列：可以使用 $n$ 受控模加的序列来执行每个乘法；每个模加都可以通过常规加法器和比较器构建。</span><span class="sxs-lookup"><span data-stu-id="de56b-111">This sequence of controlled modular multiplications can be simplified further: Each multiplication can be performed using a sequence of $n$ controlled modular additions; and each modular addition can be built from a regular addition and a comparator.</span></span>


<span data-ttu-id="de56b-112">考虑到要得到一个实际的实现需要执行许多步骤，因此从一开始就可以使用这样的功能将非常有帮助。</span><span class="sxs-lookup"><span data-stu-id="de56b-112">Given that so many steps are necessary to arrive at an actual implementation, it would be extremely helpful to have such functionality available from the start.</span></span>
<span data-ttu-id="de56b-113">这就是量子开发工具包支持广泛的数字功能支持的原因。</span><span class="sxs-lookup"><span data-stu-id="de56b-113">This is why the Quantum Development Kit provides support for a wide range of numerics functionality.</span></span>


## <a name="functionality"></a><span data-ttu-id="de56b-114">功能</span><span class="sxs-lookup"><span data-stu-id="de56b-114">Functionality</span></span>

<span data-ttu-id="de56b-115">除了到目前为止提到的整数运算，数字库还提供</span><span class="sxs-lookup"><span data-stu-id="de56b-115">Besides the integer arithmetic mentioned thus far, the numerics library provides</span></span>

 - <span data-ttu-id="de56b-116">使用一个或两个量子整数作为输入的有/无符号整数功能（乘法、平方、带余除法、反演...）</span><span class="sxs-lookup"><span data-stu-id="de56b-116">(Un)signed integer functionality (multiply, square, division with remainder, inversion, ...) with one or two quantum integer numbers as input</span></span>
 - <span data-ttu-id="de56b-117">使用一个或两个量子定点数作为输入的定点功能（加法/减法、乘法、平方、1/x、多项式求值）</span><span class="sxs-lookup"><span data-stu-id="de56b-117">Fixed-point functionality (add / subtract, multiply, square, 1/x, polynomial evaluation) with one or two quantum fixed-point numbers as input</span></span>

## <a name="getting-started"></a><span data-ttu-id="de56b-118">入门</span><span class="sxs-lookup"><span data-stu-id="de56b-118">Getting started</span></span>

<span data-ttu-id="de56b-119">若要开始使用数字库，请查看[安装指南](xref:microsoft.quantum.numerics.installation)以及有关[使用数字库](xref:microsoft.quantum.numerics.usage)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="de56b-119">To get started with the Numerics Library, check out the [installation guide](xref:microsoft.quantum.numerics.installation) and more information on [using the Numerics Library](xref:microsoft.quantum.numerics.usage).</span></span>
