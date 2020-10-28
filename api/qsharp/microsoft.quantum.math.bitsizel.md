---
uid: Microsoft.Quantum.Math.BitSizeL
title: BitSizeL 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeL
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 97068f12050317a9aa17c95f33650ef6f406066d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700485"
---
# <a name="bitsizel-function"></a><span data-ttu-id="9a151-102">BitSizeL 函数</span><span class="sxs-lookup"><span data-stu-id="9a151-102">BitSizeL function</span></span>

<span data-ttu-id="9a151-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="9a151-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="9a151-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9a151-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9a151-105">对于非负整数 `a` ，返回表示所需的位数 `a` 。</span><span class="sxs-lookup"><span data-stu-id="9a151-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="9a151-106">即，返回 < 2 ^ n $ $a 的最小 $n $。</span><span class="sxs-lookup"><span data-stu-id="9a151-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeL (a : BigInt) : Int
```


## <a name="input"></a><span data-ttu-id="9a151-107">输入</span><span class="sxs-lookup"><span data-stu-id="9a151-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="9a151-108">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9a151-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="9a151-109">要计算其位大小的整数。</span><span class="sxs-lookup"><span data-stu-id="9a151-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="9a151-110">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9a151-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9a151-111">的位大小 `a` 。</span><span class="sxs-lookup"><span data-stu-id="9a151-111">The bit-size of `a`.</span></span>