---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: IsCoprimeL 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 7c077d508c93672d58a52a1403b3c5d73df75471
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700233"
---
# <a name="iscoprimel-function"></a><span data-ttu-id="cc48a-102">IsCoprimeL 函数</span><span class="sxs-lookup"><span data-stu-id="cc48a-102">IsCoprimeL function</span></span>

<span data-ttu-id="cc48a-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="cc48a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="cc48a-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cc48a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cc48a-105">如果 $a $ 和 $b $ 是共同质数，则返回 true; 否则返回 false。</span><span class="sxs-lookup"><span data-stu-id="cc48a-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="cc48a-106">输入</span><span class="sxs-lookup"><span data-stu-id="cc48a-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="cc48a-107">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cc48a-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cc48a-108">正在测试的 primality 的第一个数字</span><span class="sxs-lookup"><span data-stu-id="cc48a-108">the first number of which co-primality is being tested</span></span>


### <a name="b--bigint"></a><span data-ttu-id="cc48a-109">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cc48a-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cc48a-110">正在测试的 primality 的第二个数字</span><span class="sxs-lookup"><span data-stu-id="cc48a-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="cc48a-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="cc48a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cc48a-112">如果 $a $ 和 $b $ 是共同质数 (例如，其最大公因数为 1 ) ，则为 True; 否则为 false。</span><span class="sxs-lookup"><span data-stu-id="cc48a-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>