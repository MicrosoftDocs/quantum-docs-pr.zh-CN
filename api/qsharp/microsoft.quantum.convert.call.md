---
uid: Microsoft.Quantum.Convert.Call
title: 调用操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 8630f846b4b9823ce1c1dfd61dc8ca81e468517d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695677"
---
# <a name="call-operation"></a><span data-ttu-id="8aebd-102">调用操作</span><span class="sxs-lookup"><span data-stu-id="8aebd-102">Call operation</span></span>

<span data-ttu-id="8aebd-103">命名空间 [：](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="8aebd-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="8aebd-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8aebd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8aebd-105">调用具有给定输入的函数。</span><span class="sxs-lookup"><span data-stu-id="8aebd-105">Calls a function with a given input.</span></span>

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a><span data-ttu-id="8aebd-106">说明</span><span class="sxs-lookup"><span data-stu-id="8aebd-106">Description</span></span>

<span data-ttu-id="8aebd-107">给定函数和该函数的输入时，将调用函数并返回其输出。</span><span class="sxs-lookup"><span data-stu-id="8aebd-107">Given a function and an input to that function, calls the function and returns its output.</span></span>

## <a name="input"></a><span data-ttu-id="8aebd-108">输入</span><span class="sxs-lookup"><span data-stu-id="8aebd-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="8aebd-109">fn： "输入 >" 输出</span><span class="sxs-lookup"><span data-stu-id="8aebd-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="8aebd-110">要调用的函数。</span><span class="sxs-lookup"><span data-stu-id="8aebd-110">A function to be called.</span></span>


### <a name="input--input"></a><span data-ttu-id="8aebd-111">输入： "输入</span><span class="sxs-lookup"><span data-stu-id="8aebd-111">input : 'Input</span></span>

<span data-ttu-id="8aebd-112">要传递给函数的输入。</span><span class="sxs-lookup"><span data-stu-id="8aebd-112">The input to be passed to the function.</span></span>



## <a name="output--output"></a><span data-ttu-id="8aebd-113">Output： "Output</span><span class="sxs-lookup"><span data-stu-id="8aebd-113">Output : 'Output</span></span>

<span data-ttu-id="8aebd-114">调用 `fn` 的结果。</span><span class="sxs-lookup"><span data-stu-id="8aebd-114">The result of calling `fn`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8aebd-115">类型参数</span><span class="sxs-lookup"><span data-stu-id="8aebd-115">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="8aebd-116">' 输入</span><span class="sxs-lookup"><span data-stu-id="8aebd-116">'Input</span></span>


### <a name="output"></a><span data-ttu-id="8aebd-117">' Output</span><span class="sxs-lookup"><span data-stu-id="8aebd-117">'Output</span></span>



## <a name="remarks"></a><span data-ttu-id="8aebd-118">注解</span><span class="sxs-lookup"><span data-stu-id="8aebd-118">Remarks</span></span>

<span data-ttu-id="8aebd-119">此操作主要适用于强制在操作内的特定位置调用函数，或用于调用应执行操作的函数。</span><span class="sxs-lookup"><span data-stu-id="8aebd-119">This operation is mainly useful for forcing a function to be called at a specific place within an operation, or for calling a function where an operation is expected.</span></span>