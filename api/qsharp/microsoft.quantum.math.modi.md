---
uid: Microsoft.Quantum.Math.ModI
title: ModI 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModI
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: d5581c5e2e4f0bcb4f8eec78464292e23031155c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700464"
---
# <a name="modi-function"></a><span data-ttu-id="dc95f-102">ModI 函数</span><span class="sxs-lookup"><span data-stu-id="dc95f-102">ModI function</span></span>

<span data-ttu-id="dc95f-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="dc95f-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="dc95f-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dc95f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dc95f-105">返回与另一个数字相关的数字的模数。</span><span class="sxs-lookup"><span data-stu-id="dc95f-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModI (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="dc95f-106">输入</span><span class="sxs-lookup"><span data-stu-id="dc95f-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="dc95f-107">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dc95f-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dc95f-108">要返回其模数的输入 $a $。</span><span class="sxs-lookup"><span data-stu-id="dc95f-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--int"></a><span data-ttu-id="dc95f-109">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dc95f-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dc95f-110">要返回其 $a $ 的模数的相对数量。</span><span class="sxs-lookup"><span data-stu-id="dc95f-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="dc95f-111">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dc95f-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dc95f-112">取模 $a \bmod b $。</span><span class="sxs-lookup"><span data-stu-id="dc95f-112">The modulus $a \bmod b$.</span></span>