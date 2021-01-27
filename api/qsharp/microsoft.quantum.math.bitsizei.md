---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: e7edf37a81571dfa1d4cb755493e1863a44c694e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857700"
---
# <a name="bitsizei-function"></a><span data-ttu-id="ee7fb-102">BitSizeI 函数</span><span class="sxs-lookup"><span data-stu-id="ee7fb-102">BitSizeI function</span></span>

<span data-ttu-id="ee7fb-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="ee7fb-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="ee7fb-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ee7fb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ee7fb-105">对于非负整数 `a` ，返回表示所需的位数 `a` 。</span><span class="sxs-lookup"><span data-stu-id="ee7fb-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="ee7fb-106">即，返回 < 2 ^ n $ $a 的最小 $n $。</span><span class="sxs-lookup"><span data-stu-id="ee7fb-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a><span data-ttu-id="ee7fb-107">输入</span><span class="sxs-lookup"><span data-stu-id="ee7fb-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="ee7fb-108">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ee7fb-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ee7fb-109">要计算其位大小的整数。</span><span class="sxs-lookup"><span data-stu-id="ee7fb-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="ee7fb-110">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ee7fb-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ee7fb-111">的位大小 `a` 。</span><span class="sxs-lookup"><span data-stu-id="ee7fb-111">The bit-size of `a`.</span></span>