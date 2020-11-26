---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 561450ef43144aa4d7820e1f15d9300018104acd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195845"
---
# <a name="bitsizei-function"></a><span data-ttu-id="742fc-102">BitSizeI 函数</span><span class="sxs-lookup"><span data-stu-id="742fc-102">BitSizeI function</span></span>

<span data-ttu-id="742fc-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="742fc-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="742fc-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="742fc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="742fc-105">对于非负整数 `a` ，返回表示所需的位数 `a` 。</span><span class="sxs-lookup"><span data-stu-id="742fc-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="742fc-106">即，返回 < 2 ^ n $ $a 的最小 $n $。</span><span class="sxs-lookup"><span data-stu-id="742fc-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a><span data-ttu-id="742fc-107">输入</span><span class="sxs-lookup"><span data-stu-id="742fc-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="742fc-108">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="742fc-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="742fc-109">要计算其位大小的整数。</span><span class="sxs-lookup"><span data-stu-id="742fc-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="742fc-110">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="742fc-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="742fc-111">的位大小 `a` 。</span><span class="sxs-lookup"><span data-stu-id="742fc-111">The bit-size of `a`.</span></span>