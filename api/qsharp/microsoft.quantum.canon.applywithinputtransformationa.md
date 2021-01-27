---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationA
title: ApplyWithInputTransformationA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 3ab07f301f310e3ec380981bdb53201fc74bd289
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841126"
---
# <a name="applywithinputtransformationa-operation"></a><span data-ttu-id="8d3ce-102">ApplyWithInputTransformationA 操作</span><span class="sxs-lookup"><span data-stu-id="8d3ce-102">ApplyWithInputTransformationA operation</span></span>

<span data-ttu-id="8d3ce-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8d3ce-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8d3ce-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8d3ce-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8d3ce-105">给定接受某些输入的操作，返回与该操作兼容的输出的函数以及该函数的输入将使用函数将输入转换为操作所需的格式。</span><span class="sxs-lookup"><span data-stu-id="8d3ce-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj), input : 'U) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="8d3ce-106">输入</span><span class="sxs-lookup"><span data-stu-id="8d3ce-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="8d3ce-107">fn： ' U-></span><span class="sxs-lookup"><span data-stu-id="8d3ce-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="8d3ce-108">将给定输入转换为操作所需的格式的函数。</span><span class="sxs-lookup"><span data-stu-id="8d3ce-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="8d3ce-109">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="8d3ce-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="8d3ce-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="8d3ce-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="8d3ce-111">输入： U</span><span class="sxs-lookup"><span data-stu-id="8d3ce-111">input : 'U</span></span>

<span data-ttu-id="8d3ce-112">函数的输入。</span><span class="sxs-lookup"><span data-stu-id="8d3ce-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8d3ce-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8d3ce-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8d3ce-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="8d3ce-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8d3ce-115">找</span><span class="sxs-lookup"><span data-stu-id="8d3ce-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="8d3ce-116">' U</span><span class="sxs-lookup"><span data-stu-id="8d3ce-116">'U</span></span>



## <a name="example"></a><span data-ttu-id="8d3ce-117">示例</span><span class="sxs-lookup"><span data-stu-id="8d3ce-117">Example</span></span>

<span data-ttu-id="8d3ce-118">以下调用使用将 @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" 为输入设计的操作应用于 @"Microsoft.Quantum.Arithmetic.BigEndian" 类型的输入 @"Microsoft.Quantum.Arithmetic.LittleEndian" ：</span><span class="sxs-lookup"><span data-stu-id="8d3ce-118">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to apply an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs to an input of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
ApplyWithInputTransformation(LittleEndianAsBigEndian, ApplyXorInPlaceBE, LittleEndian(qubits));
```

## <a name="see-also"></a><span data-ttu-id="8d3ce-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d3ce-119">See Also</span></span>

- [<span data-ttu-id="8d3ce-120">Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="8d3ce-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="8d3ce-121">Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="8d3ce-121">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="8d3ce-122">Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="8d3ce-122">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="8d3ce-123">Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="8d3ce-123">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)