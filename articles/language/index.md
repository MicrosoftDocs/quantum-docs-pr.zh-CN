---
title: Q# 编程语言 | Microsoft Docs
description: Q# 编程语言
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.intro
ms.openlocfilehash: d8759b9f043d2e13f4b0c97d54bd824c7e87d6de
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035265"
---
# <a name="the-q-programming-language"></a><span data-ttu-id="33e0e-103">Q# 编程语言</span><span class="sxs-lookup"><span data-stu-id="33e0e-103">The Q# Programming Language</span></span>

# <a name="introduction"></a><span data-ttu-id="33e0e-104">介绍</span><span class="sxs-lookup"><span data-stu-id="33e0e-104">Introduction</span></span>

<span data-ttu-id="33e0e-105">量子计算的自然模型是将量子计算机视为协处理器，类似于用于 GPU、FPGA 和其他副处理器的计算机。</span><span class="sxs-lookup"><span data-stu-id="33e0e-105">A natural model for quantum computation is to treat the quantum computer as a coprocessor, similar to that used for GPUs, FPGAs, and other adjunct processors.</span></span>
<span data-ttu-id="33e0e-106">主要控制逻辑在经典“主机”计算机上运行经典代码。</span><span class="sxs-lookup"><span data-stu-id="33e0e-106">The primary control logic runs classical code on a classical "host" computer.</span></span>
<span data-ttu-id="33e0e-107">在适当情况下，如有必要，主机程序可以调用在副处理器上运行的子例程。</span><span class="sxs-lookup"><span data-stu-id="33e0e-107">When appropriate and necessary, the host program can invoke a subroutine that runs on the adjunct processor.</span></span>
<span data-ttu-id="33e0e-108">子例程完成后，主机程序将获取对子例程结果的访问权限。</span><span class="sxs-lookup"><span data-stu-id="33e0e-108">When the subroutine completes, the host program gets access to the subroutine's results.</span></span>

<span data-ttu-id="33e0e-109">Q# (Q-sharp) 是用于表示量子算法的特定于域的编程语言。</span><span class="sxs-lookup"><span data-stu-id="33e0e-109">Q# (Q-sharp) is a domain-specific programming language used for expressing quantum algorithms.</span></span>
<span data-ttu-id="33e0e-110">它用于在经典主机程序和计算机的控制下编写在量子副处理器上执行的子例程。</span><span class="sxs-lookup"><span data-stu-id="33e0e-110">It is to be used for writing subroutines that execute on an adjunct quantum processor, under the control of a classical host program and computer.</span></span>
<span data-ttu-id="33e0e-111">在量子处理器广泛使用之前，Q# 子例程在模拟器上执行。</span><span class="sxs-lookup"><span data-stu-id="33e0e-111">Until quantum processors are widely available, Q# subroutines execute on a simulator.</span></span>

<span data-ttu-id="33e0e-112">Q# 提供一小部分基元类型，以及用于创建新的结构化类型的两种方法（数组和元组）。</span><span class="sxs-lookup"><span data-stu-id="33e0e-112">Q# provides a small set of primitive types, along with two ways (arrays and tuples) for creating new, structured types.</span></span>
<span data-ttu-id="33e0e-113">它支持使用循环和 if/then 语句编写程序的基本过程模型。</span><span class="sxs-lookup"><span data-stu-id="33e0e-113">It supports a basic procedural model for writing programs, with loops and if/then statements.</span></span>
<span data-ttu-id="33e0e-114">Q# 中的顶级构造是用户定义的类型、操作和函数。</span><span class="sxs-lookup"><span data-stu-id="33e0e-114">The top-level constructs in Q# are user defined types, operations, and functions.</span></span>

<span data-ttu-id="33e0e-115">以下部分详细介绍：</span><span class="sxs-lookup"><span data-stu-id="33e0e-115">The following sections detail:</span></span>
- [<span data-ttu-id="33e0e-116">类型模型</span><span class="sxs-lookup"><span data-stu-id="33e0e-116">The Type Model</span></span>](xref:microsoft.quantum.language.type-model)
- [<span data-ttu-id="33e0e-117">表达式</span><span class="sxs-lookup"><span data-stu-id="33e0e-117">Expressions</span></span>](xref:microsoft.quantum.language.expressions)
- [<span data-ttu-id="33e0e-118">语句</span><span class="sxs-lookup"><span data-stu-id="33e0e-118">Statements</span></span>](xref:microsoft.quantum.language.statements)
- [<span data-ttu-id="33e0e-119">文件结构</span><span class="sxs-lookup"><span data-stu-id="33e0e-119">File Structure</span></span>](xref:microsoft.quantum.language.file-structure)

# <a name="conventions"></a><span data-ttu-id="33e0e-120">约定</span><span class="sxs-lookup"><span data-stu-id="33e0e-120">Conventions</span></span>

<span data-ttu-id="33e0e-121">我们正在努力确保在所有情况下都能一致地使用常见标点符号。</span><span class="sxs-lookup"><span data-stu-id="33e0e-121">We are working to ensure that common punctuation marks are used consistently in all situations.</span></span>
<span data-ttu-id="33e0e-122">我们预计这会使 Q# 更易于学习和阅读，因为这些标记始终表示相同的含义，相同的概念始终以相同的方式表示。</span><span class="sxs-lookup"><span data-stu-id="33e0e-122">We expect that this will make Q# easier to learn and to read because these marks always mean the same thing, and the same concept is always represented the same way.</span></span>

<span data-ttu-id="33e0e-123">具体而言：</span><span class="sxs-lookup"><span data-stu-id="33e0e-123">Specifically:</span></span>

- <span data-ttu-id="33e0e-124">分号 `;` 用于结束语句或单行指令。</span><span class="sxs-lookup"><span data-stu-id="33e0e-124">The semi-colon, `;`, is used to end a statement or single-line directive.</span></span>
  <span data-ttu-id="33e0e-125">它不用于任何其他用途。</span><span class="sxs-lookup"><span data-stu-id="33e0e-125">It is not used for any other purpose.</span></span>
- <span data-ttu-id="33e0e-126">逗号 `,` 用于分隔序列的元素。</span><span class="sxs-lookup"><span data-stu-id="33e0e-126">The comma, `,`, is used to separate elements of a sequence.</span></span> <span data-ttu-id="33e0e-127">它用于元组文本、数组文本、参数列表、元组定义和类型列表。</span><span class="sxs-lookup"><span data-stu-id="33e0e-127">It is used for tuple literals, array literals, argument lists, tuple definitions, and type lists.</span></span> <span data-ttu-id="33e0e-128">**在早期版本的更改中，`;` 不再支持作为数组文本分隔符。**</span><span class="sxs-lookup"><span data-stu-id="33e0e-128">**In a change from earlier versions, `;` is no longer supported as an array literal separator.**</span></span>
- <span data-ttu-id="33e0e-129">冒号 `:` 用于引入类型批注。</span><span class="sxs-lookup"><span data-stu-id="33e0e-129">The colon, `:`, is used to introduce a type annotation.</span></span> <span data-ttu-id="33e0e-130">它主要用于可调用签名。</span><span class="sxs-lookup"><span data-stu-id="33e0e-130">It is primarily used in callable signatures.</span></span>
  <span data-ttu-id="33e0e-131">由于冒号始终引入类型签名，因此 0.3 中引入的三元条件运算符使用竖线 `|` 来分隔 true 值和 false 值；因此，Q# 使用 `cond ? tval | fval`（而不是冒号）作为 C 中的分隔符。</span><span class="sxs-lookup"><span data-stu-id="33e0e-131">Because colon always introduces a type signature, the ternary conditional operator introduced in 0.3 uses a vertical bar, `|`, to separate the true and false values; thus, Q# uses `cond ? tval | fval` instead of the colon as separator as in C.</span></span>
  
