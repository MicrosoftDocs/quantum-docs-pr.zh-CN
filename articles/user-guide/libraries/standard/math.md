---
title: '标准库中的数学公式 :::no-loc(Q#):::'
description: '了解 :::no-loc(Q#)::: 与内置数据类型一起使用的标准库中的传统数学函数。'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: article
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 6de1574341d67c569cd2f040ec533e263fdd386e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692058"
---
# <a name="classical-mathematical-functions"></a><span data-ttu-id="0923f-103">传统数学函数</span><span class="sxs-lookup"><span data-stu-id="0923f-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="0923f-104">这些函数主要用于处理 :::no-loc(Q#)::: 内置的数据类型 `Int` 、 `Double` 和 `Range` 。</span><span class="sxs-lookup"><span data-stu-id="0923f-104">These functions are primarily used to work with the :::no-loc(Q#)::: built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="0923f-105"><xref:Microsoft.Quantum.Intrinsic.Random>操作具有签名 `(Double[] => Int)` 。</span><span class="sxs-lookup"><span data-stu-id="0923f-105">The <xref:Microsoft.Quantum.Intrinsic.Random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="0923f-106">它采用双精度数组作为输入，并将随机选择的索引作为返回到数组中 `Int` 。</span><span class="sxs-lookup"><span data-stu-id="0923f-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="0923f-107">选择特定索引的概率与该索引处数组元素的值成正比。</span><span class="sxs-lookup"><span data-stu-id="0923f-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="0923f-108">已忽略等于零的 n 个数组元素，并且从不返回它们的索引。</span><span class="sxs-lookup"><span data-stu-id="0923f-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="0923f-109">如果任何数组元素小于0，或者如果没有数组元素大于零，则操作将失败。</span><span class="sxs-lookup"><span data-stu-id="0923f-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
