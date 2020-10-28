---
uid: Microsoft.Quantum.Math.ModL
title: ModL 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModL
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: 15b11a59d189aa881da9fb514cf0fe3bc9f20201
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700461"
---
# <a name="modl-function"></a><span data-ttu-id="af5b9-102">ModL 函数</span><span class="sxs-lookup"><span data-stu-id="af5b9-102">ModL function</span></span>

<span data-ttu-id="af5b9-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="af5b9-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="af5b9-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="af5b9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="af5b9-105">返回与另一个数字相关的数字的模数。</span><span class="sxs-lookup"><span data-stu-id="af5b9-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="af5b9-106">输入</span><span class="sxs-lookup"><span data-stu-id="af5b9-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="af5b9-107">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="af5b9-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="af5b9-108">要返回其模数的输入 $a $。</span><span class="sxs-lookup"><span data-stu-id="af5b9-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="af5b9-109">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="af5b9-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="af5b9-110">要返回其 $a $ 的模数的相对数量。</span><span class="sxs-lookup"><span data-stu-id="af5b9-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="af5b9-111">输出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="af5b9-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="af5b9-112">取模 $a \bmod b $。</span><span class="sxs-lookup"><span data-stu-id="af5b9-112">The modulus $a \bmod b$.</span></span>