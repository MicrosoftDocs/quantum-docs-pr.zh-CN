---
title: 'Q # 标准库-数学 |Microsoft Docs'
description: 'Q # 标准库-数学'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 7ac9d321f59f7cc95ad8939a4cf7c36e0c5e0491
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184451"
---
# <a name="classical-mathematical-functions"></a><span data-ttu-id="3e335-103">传统数学函数</span><span class="sxs-lookup"><span data-stu-id="3e335-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="3e335-104">这些函数主要用于处理 Q # 内置数据类型 `Int`、`Double`和 `Range`。</span><span class="sxs-lookup"><span data-stu-id="3e335-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="3e335-105"><xref:microsoft.quantum.intrinsic.random> 操作的签名 `(Double[] => Int)`。</span><span class="sxs-lookup"><span data-stu-id="3e335-105">The <xref:microsoft.quantum.intrinsic.random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="3e335-106">它采用双精度数组作为输入，并将随机选择的索引作为 `Int`返回到数组中。</span><span class="sxs-lookup"><span data-stu-id="3e335-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="3e335-107">选择特定索引的概率与该索引处数组元素的值成正比。</span><span class="sxs-lookup"><span data-stu-id="3e335-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="3e335-108">已忽略等于零的 n 个数组元素，并且从不返回它们的索引。</span><span class="sxs-lookup"><span data-stu-id="3e335-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="3e335-109">如果任何数组元素小于0，或者如果没有数组元素大于零，则操作将失败。</span><span class="sxs-lookup"><span data-stu-id="3e335-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>