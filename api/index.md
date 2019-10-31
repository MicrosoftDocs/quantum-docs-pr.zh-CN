---
uid: microsoft.quantum.standardlibsintro
title: 'Microsoft Quantum 的 Q # 标准库'
description: 'Microsoft Quantum 的 Q # 标准库的参考文档'
author: natke
ms.author: nakersha
ms.date: 09/04/2019
ms.topic: landing-page
ms.openlocfilehash: 25a53e1cb8577761ef89cdcf2cfcddc509093f86
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73056965"
---
# <a name="q-standard-libraries"></a><span data-ttu-id="9f585-103">Q# 标准库</span><span class="sxs-lookup"><span data-stu-id="9f585-103">Q# standard libraries</span></span> #

<span data-ttu-id="9f585-104">Q# 由包含 Q # 标准库的各种不同的有用操作、函数和用户定义的类型支持  。</span><span class="sxs-lookup"><span data-stu-id="9f585-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard library*.</span></span>
<span data-ttu-id="9f585-105">Q# 标准库分为两个主要部分：</span><span class="sxs-lookup"><span data-stu-id="9f585-105">The Q# standard library is split into two main parts:</span></span>

- <span data-ttu-id="9f585-106">**prelude**：定义为目标计算机和编译器的一部分的操作和函数，通常采用传统的本机 .NET 代码。</span><span class="sxs-lookup"><span data-stu-id="9f585-106">**The prelude**: operations and functions defined as a part of the target machine and compiler, typically in classical native .NET code.</span></span>
  <span data-ttu-id="9f585-107">通常，不同的目标计算机可能具有适用于每个系统的 prelude 的不同实现。</span><span class="sxs-lookup"><span data-stu-id="9f585-107">In general, different target machines may have different implementations of the prelude appropriate to each system.</span></span>
- <span data-ttu-id="9f585-108">**canon**：Q# 中定义的操作和函数，在 prelude 中定义的逻辑上生成。</span><span class="sxs-lookup"><span data-stu-id="9f585-108">**The canon**: operations and functions defined in Q# building on the logic defined in the prelude.</span></span>
  <span data-ttu-id="9f585-109">canon 实现是目标计算机不可知的。</span><span class="sxs-lookup"><span data-stu-id="9f585-109">The canon implementation is agnostic with respect to target machines.</span></span>
<span data-ttu-id="9f585-110">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span><span class="sxs-lookup"><span data-stu-id="9f585-110">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span></span>