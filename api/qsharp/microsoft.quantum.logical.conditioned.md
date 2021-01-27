---
uid: Microsoft.Quantum.Logical.Conditioned
title: 可调函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: ea3b8eba960acceb6540978c6fccd9f796b0f67d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817289"
---
# <a name="conditioned-function"></a><span data-ttu-id="5b599-102">可调函数</span><span class="sxs-lookup"><span data-stu-id="5b599-102">Conditioned function</span></span>

<span data-ttu-id="5b599-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="5b599-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="5b599-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5b599-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5b599-105">根据布尔条件的值返回两个值中的一个值。</span><span class="sxs-lookup"><span data-stu-id="5b599-105">Returns one of two values, depending on the value of a Boolean condition.</span></span>

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a><span data-ttu-id="5b599-106">输入</span><span class="sxs-lookup"><span data-stu-id="5b599-106">Input</span></span>

### <a name="condition--bool"></a><span data-ttu-id="5b599-107">condition： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5b599-107">condition : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5b599-108">用于控制返回的输入的条件。</span><span class="sxs-lookup"><span data-stu-id="5b599-108">A condition used to control which input is returned.</span></span>


### <a name="iftrue--t"></a><span data-ttu-id="5b599-109">ifTrue： t</span><span class="sxs-lookup"><span data-stu-id="5b599-109">ifTrue : 'T</span></span>

<span data-ttu-id="5b599-110">当为时要返回的 `condition` 值 `true` 。</span><span class="sxs-lookup"><span data-stu-id="5b599-110">The value to be returned when `condition` is `true`.</span></span>


### <a name="iffalse--t"></a><span data-ttu-id="5b599-111">ifFalse： t</span><span class="sxs-lookup"><span data-stu-id="5b599-111">ifFalse : 'T</span></span>

<span data-ttu-id="5b599-112">当为时要返回的 `condition` 值 `false` 。</span><span class="sxs-lookup"><span data-stu-id="5b599-112">The value to be returned when `condition` is `false`.</span></span>



## <a name="output--t"></a><span data-ttu-id="5b599-113">输出：不</span><span class="sxs-lookup"><span data-stu-id="5b599-113">Output : 'T</span></span>

<span data-ttu-id="5b599-114">`ifTrue` 如果 `condition` 为，则为; `true` `ifFalse` 否则为。</span><span class="sxs-lookup"><span data-stu-id="5b599-114">`ifTrue` if `condition` is `true`, and `ifFalse` otherwise.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5b599-115">类型参数</span><span class="sxs-lookup"><span data-stu-id="5b599-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5b599-116">找</span><span class="sxs-lookup"><span data-stu-id="5b599-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="5b599-117">备注</span><span class="sxs-lookup"><span data-stu-id="5b599-117">Remarks</span></span>

<span data-ttu-id="5b599-118">与 `?|` 运算符不同，此函数不会进行短路，因此，这两个输入都是完全计算的。</span><span class="sxs-lookup"><span data-stu-id="5b599-118">Unlike the `?|` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="5b599-119">最多短路行为，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5b599-119">Up to short-circuiting behavior, the following are equivalent:</span></span>

```qsharp
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```