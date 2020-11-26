---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationA
title: ApplyWithInputTransformationA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 8d65af33a0bc8ce3c08da54b34e68b4e22b710ca
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207881"
---
# <a name="applywithinputtransformationa-operation"></a><span data-ttu-id="86f09-102">ApplyWithInputTransformationA 操作</span><span class="sxs-lookup"><span data-stu-id="86f09-102">ApplyWithInputTransformationA operation</span></span>

<span data-ttu-id="86f09-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="86f09-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="86f09-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="86f09-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="86f09-105">给定接受某些输入的操作，返回与该操作兼容的输出的函数以及该函数的输入将使用函数将输入转换为操作所需的格式。</span><span class="sxs-lookup"><span data-stu-id="86f09-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj), input : 'U) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="86f09-106">输入</span><span class="sxs-lookup"><span data-stu-id="86f09-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="86f09-107">fn： ' U-></span><span class="sxs-lookup"><span data-stu-id="86f09-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="86f09-108">将给定输入转换为操作所需的格式的函数。</span><span class="sxs-lookup"><span data-stu-id="86f09-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="86f09-109">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="86f09-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="86f09-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="86f09-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="86f09-111">输入： U</span><span class="sxs-lookup"><span data-stu-id="86f09-111">input : 'U</span></span>

<span data-ttu-id="86f09-112">函数的输入。</span><span class="sxs-lookup"><span data-stu-id="86f09-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="86f09-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="86f09-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="86f09-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="86f09-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="86f09-115">找</span><span class="sxs-lookup"><span data-stu-id="86f09-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="86f09-116">' U</span><span class="sxs-lookup"><span data-stu-id="86f09-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="86f09-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86f09-117">See Also</span></span>

- [<span data-ttu-id="86f09-118">Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="86f09-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="86f09-119">Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="86f09-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="86f09-120">Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="86f09-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="86f09-121">Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="86f09-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)