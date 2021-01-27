---
uid: Microsoft.Quantum.Canon.ApplyToRest
title: ApplyToRest 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRest
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: f18536a056935220feedc4ea50531c5def61d650
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850517"
---
# <a name="applytorest-operation"></a><span data-ttu-id="6b396-102">ApplyToRest 操作</span><span class="sxs-lookup"><span data-stu-id="6b396-102">ApplyToRest operation</span></span>

<span data-ttu-id="6b396-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6b396-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6b396-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6b396-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6b396-105">将操作应用到数组中除第一个元素之外的所有元素。</span><span class="sxs-lookup"><span data-stu-id="6b396-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRest<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="6b396-106">说明</span><span class="sxs-lookup"><span data-stu-id="6b396-106">Description</span></span>

<span data-ttu-id="6b396-107">给定一个操作 `op` 和一个目标数组 `targets` ，适用于 `op(Rest(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="6b396-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="6b396-108">输入</span><span class="sxs-lookup"><span data-stu-id="6b396-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="6b396-109">op： t [] => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6b396-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6b396-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="6b396-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="6b396-111">目标： t []</span><span class="sxs-lookup"><span data-stu-id="6b396-111">targets : 'T[]</span></span>

<span data-ttu-id="6b396-112">目标数组，其中除第一个以外的所有将应用于 `op` 。</span><span class="sxs-lookup"><span data-stu-id="6b396-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6b396-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6b396-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6b396-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="6b396-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6b396-115">找</span><span class="sxs-lookup"><span data-stu-id="6b396-115">'T</span></span>

<span data-ttu-id="6b396-116">要应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="6b396-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="6b396-117">示例</span><span class="sxs-lookup"><span data-stu-id="6b396-117">Example</span></span>

<span data-ttu-id="6b396-118">以下 Q # 代码段是等效的：</span><span class="sxs-lookup"><span data-stu-id="6b396-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToRest(ApplyCNOTChain, register);
ApplyCNOTChain(Rest(register));
```

## <a name="see-also"></a><span data-ttu-id="6b396-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b396-119">See Also</span></span>

- [<span data-ttu-id="6b396-120">Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="6b396-120">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="6b396-121">Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="6b396-121">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="6b396-122">Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="6b396-122">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)