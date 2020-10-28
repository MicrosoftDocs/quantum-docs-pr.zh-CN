---
uid: Microsoft.Quantum.Canon.Compose
title: 撰写函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 02cff7eef4d55d27d5d72e6219a90b7d8f5beb3b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696100"
---
# <a name="compose-function"></a><span data-ttu-id="370b9-102">撰写函数</span><span class="sxs-lookup"><span data-stu-id="370b9-102">Compose function</span></span>

<span data-ttu-id="370b9-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="370b9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="370b9-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="370b9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="370b9-105">返回两个函数的组合。</span><span class="sxs-lookup"><span data-stu-id="370b9-105">Returns the composition of two functions.</span></span>

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a><span data-ttu-id="370b9-106">说明</span><span class="sxs-lookup"><span data-stu-id="370b9-106">Description</span></span>

<span data-ttu-id="370b9-107">如果 $g $ $f 两个函数，则返回一个表示 $f \circ g $ 的新函数。</span><span class="sxs-lookup"><span data-stu-id="370b9-107">Given two functions $f$ and $g$, returns a new function representing $f \circ g$.</span></span>

## <a name="input"></a><span data-ttu-id="370b9-108">输入</span><span class="sxs-lookup"><span data-stu-id="370b9-108">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="370b9-109">外部： "U->" V</span><span class="sxs-lookup"><span data-stu-id="370b9-109">outer : 'U -> 'V</span></span>

<span data-ttu-id="370b9-110">要应用的第二个函数。</span><span class="sxs-lookup"><span data-stu-id="370b9-110">The second function to be applied.</span></span>


### <a name="inner--t---u"></a><span data-ttu-id="370b9-111">内部：不 > "U</span><span class="sxs-lookup"><span data-stu-id="370b9-111">inner : 'T -> 'U</span></span>

<span data-ttu-id="370b9-112">要应用的第一个函数。</span><span class="sxs-lookup"><span data-stu-id="370b9-112">The first function to be applied.</span></span>



## <a name="output--t---v"></a><span data-ttu-id="370b9-113">输出：不 > "V</span><span class="sxs-lookup"><span data-stu-id="370b9-113">Output : 'T -> 'V</span></span>

<span data-ttu-id="370b9-114">新函数 $h $，以便所有输入 $x $，$f (g (x) # A3 = h (x) $。</span><span class="sxs-lookup"><span data-stu-id="370b9-114">A new function $h$ such that for all inputs $x$, $f(g(x)) = h(x)$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="370b9-115">类型参数</span><span class="sxs-lookup"><span data-stu-id="370b9-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="370b9-116">找</span><span class="sxs-lookup"><span data-stu-id="370b9-116">'T</span></span>

<span data-ttu-id="370b9-117">要应用的第一个函数的输入类型。</span><span class="sxs-lookup"><span data-stu-id="370b9-117">The input type of the first function to be applied.</span></span>
### <a name="u"></a><span data-ttu-id="370b9-118">' U</span><span class="sxs-lookup"><span data-stu-id="370b9-118">'U</span></span>

<span data-ttu-id="370b9-119">要应用的第一个函数的输出类型以及要应用的第二个函数的输入类型。</span><span class="sxs-lookup"><span data-stu-id="370b9-119">The output type of the first function to be applied and the input type of the second function to be applied.</span></span>
### <a name="v"></a><span data-ttu-id="370b9-120">' V</span><span class="sxs-lookup"><span data-stu-id="370b9-120">'V</span></span>

<span data-ttu-id="370b9-121">要应用的第二个函数的输出类型。</span><span class="sxs-lookup"><span data-stu-id="370b9-121">The output type of the second function to be applied.</span></span>