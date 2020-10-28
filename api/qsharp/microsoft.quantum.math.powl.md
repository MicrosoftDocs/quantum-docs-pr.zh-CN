---
uid: Microsoft.Quantum.Math.PowL
title: PowL 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowL
qsharp.summary: Returns a number raised to a given power.
ms.openlocfilehash: 22c05cf85acf691490049ce9ac27a7c6b2a4899e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700932"
---
# <a name="powl-function"></a><span data-ttu-id="31a58-102">PowL 函数</span><span class="sxs-lookup"><span data-stu-id="31a58-102">PowL function</span></span>

<span data-ttu-id="31a58-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="31a58-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="31a58-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="31a58-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="31a58-105">返回一个数的指定幂。</span><span class="sxs-lookup"><span data-stu-id="31a58-105">Returns a number raised to a given power.</span></span>

```qsharp
function PowL (a : BigInt, power : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="31a58-106">输入</span><span class="sxs-lookup"><span data-stu-id="31a58-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="31a58-107">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="31a58-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="31a58-108">要引发 $a $ 的数字。</span><span class="sxs-lookup"><span data-stu-id="31a58-108">The number $a$ that is to be raised.</span></span>


### <a name="power--int"></a><span data-ttu-id="31a58-109">幂： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="31a58-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="31a58-110">$A $ 应引发的 power $b $。</span><span class="sxs-lookup"><span data-stu-id="31a58-110">The power $b$ to which $a$ should be raised.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="31a58-111">输出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="31a58-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="31a58-112">Power $a ^ b $</span><span class="sxs-lookup"><span data-stu-id="31a58-112">The power $a^b$</span></span>