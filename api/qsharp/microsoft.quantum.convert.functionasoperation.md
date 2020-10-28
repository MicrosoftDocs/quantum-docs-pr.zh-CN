---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 90e9f0c922a77fbb6d6faf8945d4f5d1c8ff33b7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695674"
---
# <a name="functionasoperation-function"></a><span data-ttu-id="e6571-102">FunctionAsOperation 函数</span><span class="sxs-lookup"><span data-stu-id="e6571-102">FunctionAsOperation function</span></span>

<span data-ttu-id="e6571-103">命名空间 [：](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="e6571-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="e6571-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e6571-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e6571-105">将函数转换为操作。</span><span class="sxs-lookup"><span data-stu-id="e6571-105">Converts functions to operations.</span></span>

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a><span data-ttu-id="e6571-106">说明</span><span class="sxs-lookup"><span data-stu-id="e6571-106">Description</span></span>

<span data-ttu-id="e6571-107">给定函数后，将返回调用该函数的操作，该操作不执行任何其他操作。</span><span class="sxs-lookup"><span data-stu-id="e6571-107">Given a function, returns an operation which calls that function, and which does nothing else.</span></span>

## <a name="input"></a><span data-ttu-id="e6571-108">输入</span><span class="sxs-lookup"><span data-stu-id="e6571-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="e6571-109">fn： "输入 >" 输出</span><span class="sxs-lookup"><span data-stu-id="e6571-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="e6571-110">要转换为操作的函数。</span><span class="sxs-lookup"><span data-stu-id="e6571-110">A function to be converted to an operation.</span></span>



## <a name="output--input--output"></a><span data-ttu-id="e6571-111">输出： "Input =>" 输出</span><span class="sxs-lookup"><span data-stu-id="e6571-111">Output : 'Input => 'Output</span></span> 

<span data-ttu-id="e6571-112">与 `op` `op(input)` 所有相同的操作 `fn(input)` `input` 。</span><span class="sxs-lookup"><span data-stu-id="e6571-112">An operation `op` such that `op(input)` is identical to `fn(input)` for all `input`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e6571-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="e6571-113">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="e6571-114">' 输入</span><span class="sxs-lookup"><span data-stu-id="e6571-114">'Input</span></span>

<span data-ttu-id="e6571-115">要转换的函数的输入类型。</span><span class="sxs-lookup"><span data-stu-id="e6571-115">Input type of the function to be converted.</span></span>
### <a name="output"></a><span data-ttu-id="e6571-116">' Output</span><span class="sxs-lookup"><span data-stu-id="e6571-116">'Output</span></span>

<span data-ttu-id="e6571-117">要转换的函数的输出类型。</span><span class="sxs-lookup"><span data-stu-id="e6571-117">Output type of the function to be converted.</span></span>

## <a name="remarks"></a><span data-ttu-id="e6571-118">注解</span><span class="sxs-lookup"><span data-stu-id="e6571-118">Remarks</span></span>

<span data-ttu-id="e6571-119">这主要用于将函数传递到需要操作作为输入的函数或操作。</span><span class="sxs-lookup"><span data-stu-id="e6571-119">This is mainly useful for passing functions to functions or operations which expect an operation as input.</span></span>