---
uid: Microsoft.Quantum.Math.BitSizeL
title: BitSizeL 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeL
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: c94d873d7117fd2ee66226fab6d4bfc5b33bc46d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848912"
---
# <a name="bitsizel-function"></a><span data-ttu-id="6c1aa-102">BitSizeL 函数</span><span class="sxs-lookup"><span data-stu-id="6c1aa-102">BitSizeL function</span></span>

<span data-ttu-id="6c1aa-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="6c1aa-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="6c1aa-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6c1aa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6c1aa-105">对于非负整数 `a` ，返回表示所需的位数 `a` 。</span><span class="sxs-lookup"><span data-stu-id="6c1aa-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="6c1aa-106">即，返回 < 2 ^ n $ $a 的最小 $n $。</span><span class="sxs-lookup"><span data-stu-id="6c1aa-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeL (a : BigInt) : Int
```


## <a name="input"></a><span data-ttu-id="6c1aa-107">输入</span><span class="sxs-lookup"><span data-stu-id="6c1aa-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="6c1aa-108">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="6c1aa-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="6c1aa-109">要计算其位大小的整数。</span><span class="sxs-lookup"><span data-stu-id="6c1aa-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="6c1aa-110">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6c1aa-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6c1aa-111">的位大小 `a` 。</span><span class="sxs-lookup"><span data-stu-id="6c1aa-111">The bit-size of `a`.</span></span>