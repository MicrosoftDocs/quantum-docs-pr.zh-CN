---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationC
title: ApplyWithInputTransformationC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationC
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: f166880d3ca8a7fc45635c0105aa5c83fe1b4f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696150"
---
# <a name="applywithinputtransformationc-operation"></a><span data-ttu-id="c2311-102">ApplyWithInputTransformationC 操作</span><span class="sxs-lookup"><span data-stu-id="c2311-102">ApplyWithInputTransformationC operation</span></span>

<span data-ttu-id="c2311-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c2311-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c2311-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c2311-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c2311-105">给定接受某些输入的操作，返回与该操作兼容的输出的函数以及该函数的输入将使用函数将输入转换为操作所需的格式。</span><span class="sxs-lookup"><span data-stu-id="c2311-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="c2311-106">输入</span><span class="sxs-lookup"><span data-stu-id="c2311-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="c2311-107">fn： ' U-></span><span class="sxs-lookup"><span data-stu-id="c2311-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="c2311-108">将给定输入转换为操作所需的格式的函数。</span><span class="sxs-lookup"><span data-stu-id="c2311-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit-ctl"></a><span data-ttu-id="c2311-109">op： t => [单元](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="c2311-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="c2311-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="c2311-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="c2311-111">输入： U</span><span class="sxs-lookup"><span data-stu-id="c2311-111">input : 'U</span></span>

<span data-ttu-id="c2311-112">函数的输入。</span><span class="sxs-lookup"><span data-stu-id="c2311-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c2311-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c2311-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c2311-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="c2311-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c2311-115">找</span><span class="sxs-lookup"><span data-stu-id="c2311-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="c2311-116">' U</span><span class="sxs-lookup"><span data-stu-id="c2311-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="c2311-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c2311-117">See Also</span></span>

- [<span data-ttu-id="c2311-118">Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="c2311-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="c2311-119">Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="c2311-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="c2311-120">Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="c2311-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="c2311-121">Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="c2311-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)