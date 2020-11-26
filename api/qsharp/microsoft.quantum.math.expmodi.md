---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 197f7351ce76ebb7684ca8014cab9ab65d9c784c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228484"
---
# <a name="expmodi-function"></a><span data-ttu-id="1175b-102">ExpModI 函数</span><span class="sxs-lookup"><span data-stu-id="1175b-102">ExpModI function</span></span>

<span data-ttu-id="1175b-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="1175b-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="1175b-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1175b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1175b-105">返回一个整数，该整数针对给定的模数引发了给定的幂。</span><span class="sxs-lookup"><span data-stu-id="1175b-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a><span data-ttu-id="1175b-106">描述</span><span class="sxs-lookup"><span data-stu-id="1175b-106">Description</span></span>

<span data-ttu-id="1175b-107">让我们通过 $N $ $p $ 和模数来表示 $x expBase。</span><span class="sxs-lookup"><span data-stu-id="1175b-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="1175b-108">该函数返回 $x ^ p \operatorname{mod} N $。</span><span class="sxs-lookup"><span data-stu-id="1175b-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="1175b-109">假定 $N $，$x $ 为正，且 power 为非负数。</span><span class="sxs-lookup"><span data-stu-id="1175b-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="1175b-110">输入</span><span class="sxs-lookup"><span data-stu-id="1175b-110">Input</span></span>

### <a name="expbase--int"></a><span data-ttu-id="1175b-111">expBase： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1175b-111">expBase : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="power--int"></a><span data-ttu-id="1175b-112">幂： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1175b-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="modulus--int"></a><span data-ttu-id="1175b-113">取模： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1175b-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="1175b-114">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1175b-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="remarks"></a><span data-ttu-id="1175b-115">备注</span><span class="sxs-lookup"><span data-stu-id="1175b-115">Remarks</span></span>

<span data-ttu-id="1175b-116">与中的位数成正比，而 `power` 不是 `power` 本身。</span><span class="sxs-lookup"><span data-stu-id="1175b-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>