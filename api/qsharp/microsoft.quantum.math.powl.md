---
uid: Microsoft.Quantum.Math.PowL
title: PowL 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowL
qsharp.summary: Returns a number raised to a given power.
ms.openlocfilehash: b3207d1854f6b69cdb5b68d354000a0b6746c0c2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228315"
---
# <a name="powl-function"></a><span data-ttu-id="406aa-102">PowL 函数</span><span class="sxs-lookup"><span data-stu-id="406aa-102">PowL function</span></span>

<span data-ttu-id="406aa-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="406aa-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="406aa-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="406aa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="406aa-105">返回一个数的指定幂。</span><span class="sxs-lookup"><span data-stu-id="406aa-105">Returns a number raised to a given power.</span></span>

```qsharp
function PowL (a : BigInt, power : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="406aa-106">输入</span><span class="sxs-lookup"><span data-stu-id="406aa-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="406aa-107">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="406aa-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="406aa-108">要引发 $a $ 的数字。</span><span class="sxs-lookup"><span data-stu-id="406aa-108">The number $a$ that is to be raised.</span></span>


### <a name="power--int"></a><span data-ttu-id="406aa-109">幂： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="406aa-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="406aa-110">$A $ 应引发的 power $b $。</span><span class="sxs-lookup"><span data-stu-id="406aa-110">The power $b$ to which $a$ should be raised.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="406aa-111">输出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="406aa-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="406aa-112">Power $a ^ b $</span><span class="sxs-lookup"><span data-stu-id="406aa-112">The power $a^b$</span></span>