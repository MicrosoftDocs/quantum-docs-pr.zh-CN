---
uid: Microsoft.Quantum.Logical.Conditioned
title: 可调函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: c0f55d4db95ad1f0d2b7f291cbc6ba8ae704cb81
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198480"
---
# <a name="conditioned-function"></a><span data-ttu-id="e9b43-102">可调函数</span><span class="sxs-lookup"><span data-stu-id="e9b43-102">Conditioned function</span></span>

<span data-ttu-id="e9b43-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e9b43-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e9b43-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e9b43-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e9b43-105">根据布尔条件的值返回两个值中的一个值。</span><span class="sxs-lookup"><span data-stu-id="e9b43-105">Returns one of two values, depending on the value of a Boolean condition.</span></span>

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a><span data-ttu-id="e9b43-106">输入</span><span class="sxs-lookup"><span data-stu-id="e9b43-106">Input</span></span>

### <a name="condition--bool"></a><span data-ttu-id="e9b43-107">condition： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e9b43-107">condition : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e9b43-108">用于控制返回的输入的条件。</span><span class="sxs-lookup"><span data-stu-id="e9b43-108">A condition used to control which input is returned.</span></span>


### <a name="iftrue--t"></a><span data-ttu-id="e9b43-109">ifTrue： t</span><span class="sxs-lookup"><span data-stu-id="e9b43-109">ifTrue : 'T</span></span>

<span data-ttu-id="e9b43-110">当为时要返回的 `condition` 值 `true` 。</span><span class="sxs-lookup"><span data-stu-id="e9b43-110">The value to be returned when `condition` is `true`.</span></span>


### <a name="iffalse--t"></a><span data-ttu-id="e9b43-111">ifFalse： t</span><span class="sxs-lookup"><span data-stu-id="e9b43-111">ifFalse : 'T</span></span>

<span data-ttu-id="e9b43-112">当为时要返回的 `condition` 值 `false` 。</span><span class="sxs-lookup"><span data-stu-id="e9b43-112">The value to be returned when `condition` is `false`.</span></span>



## <a name="output--t"></a><span data-ttu-id="e9b43-113">输出：不</span><span class="sxs-lookup"><span data-stu-id="e9b43-113">Output : 'T</span></span>

<span data-ttu-id="e9b43-114">`ifTrue` 如果 `condition` 为，则为; `true` `ifFalse` 否则为。</span><span class="sxs-lookup"><span data-stu-id="e9b43-114">`ifTrue` if `condition` is `true`, and `ifFalse` otherwise.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e9b43-115">类型参数</span><span class="sxs-lookup"><span data-stu-id="e9b43-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e9b43-116">找</span><span class="sxs-lookup"><span data-stu-id="e9b43-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="e9b43-117">备注</span><span class="sxs-lookup"><span data-stu-id="e9b43-117">Remarks</span></span>

<span data-ttu-id="e9b43-118">与 `?|` 运算符不同，此函数不会进行短路，因此，这两个输入都是完全计算的。</span><span class="sxs-lookup"><span data-stu-id="e9b43-118">Unlike the `?|` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="e9b43-119">最多短路行为，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e9b43-119">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```