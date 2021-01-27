---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationCA
title: ApplyWithInputTransformationCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationCA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: b31ed1b3da0d5467588f4cb2e4368e68f0dbe9d5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841116"
---
# <a name="applywithinputtransformationca-operation"></a><span data-ttu-id="d0192-102">ApplyWithInputTransformationCA 操作</span><span class="sxs-lookup"><span data-stu-id="d0192-102">ApplyWithInputTransformationCA operation</span></span>

<span data-ttu-id="d0192-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d0192-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d0192-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d0192-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d0192-105">给定接受某些输入的操作，返回与该操作兼容的输出的函数以及该函数的输入将使用函数将输入转换为操作所需的格式。</span><span class="sxs-lookup"><span data-stu-id="d0192-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl), input : 'U) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d0192-106">输入</span><span class="sxs-lookup"><span data-stu-id="d0192-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="d0192-107">fn： ' U-></span><span class="sxs-lookup"><span data-stu-id="d0192-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="d0192-108">将给定输入转换为操作所需的格式的函数。</span><span class="sxs-lookup"><span data-stu-id="d0192-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="d0192-109">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="d0192-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="d0192-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="d0192-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="d0192-111">输入： U</span><span class="sxs-lookup"><span data-stu-id="d0192-111">input : 'U</span></span>

<span data-ttu-id="d0192-112">函数的输入。</span><span class="sxs-lookup"><span data-stu-id="d0192-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d0192-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d0192-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d0192-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="d0192-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d0192-115">找</span><span class="sxs-lookup"><span data-stu-id="d0192-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="d0192-116">' U</span><span class="sxs-lookup"><span data-stu-id="d0192-116">'U</span></span>



## <a name="example"></a><span data-ttu-id="d0192-117">示例</span><span class="sxs-lookup"><span data-stu-id="d0192-117">Example</span></span>

<span data-ttu-id="d0192-118">以下调用使用将 @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" 为输入设计的操作应用于 @"Microsoft.Quantum.Arithmetic.BigEndian" 类型的输入 @"Microsoft.Quantum.Arithmetic.LittleEndian" ：</span><span class="sxs-lookup"><span data-stu-id="d0192-118">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to apply an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs to an input of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
ApplyWithInputTransformation(LittleEndianAsBigEndian, ApplyXorInPlaceBE, LittleEndian(qubits));
```

## <a name="see-also"></a><span data-ttu-id="d0192-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0192-119">See Also</span></span>

- [<span data-ttu-id="d0192-120">Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="d0192-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="d0192-121">Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="d0192-121">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="d0192-122">Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="d0192-122">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="d0192-123">Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="d0192-123">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)