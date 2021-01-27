---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: ApplyToHead 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 4e627b467e9354e774c2ead8b89ddd3ff3a42ef7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841337"
---
# <a name="applytohead-operation"></a><span data-ttu-id="331ae-102">ApplyToHead 操作</span><span class="sxs-lookup"><span data-stu-id="331ae-102">ApplyToHead operation</span></span>

<span data-ttu-id="331ae-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="331ae-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="331ae-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="331ae-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="331ae-105">将操作应用到数组的第一个元素。</span><span class="sxs-lookup"><span data-stu-id="331ae-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHead<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="331ae-106">说明</span><span class="sxs-lookup"><span data-stu-id="331ae-106">Description</span></span>

<span data-ttu-id="331ae-107">给定一个操作 `op` 和一个目标数组 `targets` ，适用于 `op(Head(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="331ae-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="331ae-108">输入</span><span class="sxs-lookup"><span data-stu-id="331ae-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="331ae-109">op： t => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="331ae-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="331ae-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="331ae-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="331ae-111">目标： t []</span><span class="sxs-lookup"><span data-stu-id="331ae-111">targets : 'T[]</span></span>

<span data-ttu-id="331ae-112">要应用第一个目标的目标数组 `op` 。</span><span class="sxs-lookup"><span data-stu-id="331ae-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="331ae-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="331ae-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="331ae-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="331ae-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="331ae-115">找</span><span class="sxs-lookup"><span data-stu-id="331ae-115">'T</span></span>

<span data-ttu-id="331ae-116">要应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="331ae-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="331ae-117">示例</span><span class="sxs-lookup"><span data-stu-id="331ae-117">Example</span></span>

<span data-ttu-id="331ae-118">以下 Q # 代码段是等效的：</span><span class="sxs-lookup"><span data-stu-id="331ae-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToHead(H, register);
H(Head(register));
```

## <a name="see-also"></a><span data-ttu-id="331ae-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="331ae-119">See Also</span></span>

- [<span data-ttu-id="331ae-120">Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="331ae-120">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="331ae-121">Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="331ae-121">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="331ae-122">Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="331ae-122">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)