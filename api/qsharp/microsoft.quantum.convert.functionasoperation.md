---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: cf4f8c97bf38b3a64eb952d0a502bc21c29c579c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833842"
---
# <a name="functionasoperation-function"></a><span data-ttu-id="157c2-102">FunctionAsOperation 函数</span><span class="sxs-lookup"><span data-stu-id="157c2-102">FunctionAsOperation function</span></span>

<span data-ttu-id="157c2-103">命名空间 [：](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="157c2-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="157c2-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="157c2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="157c2-105">将函数转换为操作。</span><span class="sxs-lookup"><span data-stu-id="157c2-105">Converts functions to operations.</span></span>

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a><span data-ttu-id="157c2-106">说明</span><span class="sxs-lookup"><span data-stu-id="157c2-106">Description</span></span>

<span data-ttu-id="157c2-107">给定函数后，将返回调用该函数的操作，该操作不执行任何其他操作。</span><span class="sxs-lookup"><span data-stu-id="157c2-107">Given a function, returns an operation which calls that function, and which does nothing else.</span></span>

## <a name="input"></a><span data-ttu-id="157c2-108">输入</span><span class="sxs-lookup"><span data-stu-id="157c2-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="157c2-109">fn： "输入 >" 输出</span><span class="sxs-lookup"><span data-stu-id="157c2-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="157c2-110">要转换为操作的函数。</span><span class="sxs-lookup"><span data-stu-id="157c2-110">A function to be converted to an operation.</span></span>



## <a name="output--input--output"></a><span data-ttu-id="157c2-111">输出： "Input =>" 输出</span><span class="sxs-lookup"><span data-stu-id="157c2-111">Output : 'Input => 'Output</span></span> 

<span data-ttu-id="157c2-112">与 `op` `op(input)` 所有相同的操作 `fn(input)` `input` 。</span><span class="sxs-lookup"><span data-stu-id="157c2-112">An operation `op` such that `op(input)` is identical to `fn(input)` for all `input`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="157c2-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="157c2-113">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="157c2-114">' 输入</span><span class="sxs-lookup"><span data-stu-id="157c2-114">'Input</span></span>

<span data-ttu-id="157c2-115">要转换的函数的输入类型。</span><span class="sxs-lookup"><span data-stu-id="157c2-115">Input type of the function to be converted.</span></span>
### <a name="output"></a><span data-ttu-id="157c2-116">' Output</span><span class="sxs-lookup"><span data-stu-id="157c2-116">'Output</span></span>

<span data-ttu-id="157c2-117">要转换的函数的输出类型。</span><span class="sxs-lookup"><span data-stu-id="157c2-117">Output type of the function to be converted.</span></span>

## <a name="remarks"></a><span data-ttu-id="157c2-118">备注</span><span class="sxs-lookup"><span data-stu-id="157c2-118">Remarks</span></span>

<span data-ttu-id="157c2-119">这主要用于将函数传递到需要操作作为输入的函数或操作。</span><span class="sxs-lookup"><span data-stu-id="157c2-119">This is mainly useful for passing functions to functions or operations which expect an operation as input.</span></span>