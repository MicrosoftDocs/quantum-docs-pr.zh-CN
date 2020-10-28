---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: e31273702a9850d0162f160ca412ff6d50f38b28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700536"
---
# <a name="expmodi-function"></a><span data-ttu-id="ecbf4-102">ExpModI 函数</span><span class="sxs-lookup"><span data-stu-id="ecbf4-102">ExpModI function</span></span>

<span data-ttu-id="ecbf4-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="ecbf4-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="ecbf4-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ecbf4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ecbf4-105">返回一个整数，该整数针对给定的模数引发了给定的幂。</span><span class="sxs-lookup"><span data-stu-id="ecbf4-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a><span data-ttu-id="ecbf4-106">说明</span><span class="sxs-lookup"><span data-stu-id="ecbf4-106">Description</span></span>

<span data-ttu-id="ecbf4-107">让我们通过 $N $ $p $ 和模数来表示 $x expBase。</span><span class="sxs-lookup"><span data-stu-id="ecbf4-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="ecbf4-108">该函数返回 $x ^ p \operatorname{mod} N $。</span><span class="sxs-lookup"><span data-stu-id="ecbf4-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="ecbf4-109">假定 $N $，$x $ 为正，且 power 为非负数。</span><span class="sxs-lookup"><span data-stu-id="ecbf4-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="ecbf4-110">输入</span><span class="sxs-lookup"><span data-stu-id="ecbf4-110">Input</span></span>

### <a name="expbase--int"></a><span data-ttu-id="ecbf4-111">expBase： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ecbf4-111">expBase : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="power--int"></a><span data-ttu-id="ecbf4-112">幂： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ecbf4-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="modulus--int"></a><span data-ttu-id="ecbf4-113">取模： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ecbf4-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="ecbf4-114">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ecbf4-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="remarks"></a><span data-ttu-id="ecbf4-115">注解</span><span class="sxs-lookup"><span data-stu-id="ecbf4-115">Remarks</span></span>

<span data-ttu-id="ecbf4-116">与中的位数成正比，而 `power` 不是 `power` 本身。</span><span class="sxs-lookup"><span data-stu-id="ecbf4-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>