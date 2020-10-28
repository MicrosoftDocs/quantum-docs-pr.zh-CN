---
uid: Microsoft.Quantum.Canon.ApplyToRestA
title: ApplyToRestA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 99a18e835115491cc3451a4e3b44a6ff70e9dc6c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696184"
---
# <a name="applytoresta-operation"></a><span data-ttu-id="4a0b1-102">ApplyToRestA 操作</span><span class="sxs-lookup"><span data-stu-id="4a0b1-102">ApplyToRestA operation</span></span>

<span data-ttu-id="4a0b1-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4a0b1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4a0b1-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4a0b1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4a0b1-105">将操作应用到数组中除第一个元素之外的所有元素。</span><span class="sxs-lookup"><span data-stu-id="4a0b1-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="4a0b1-106">说明</span><span class="sxs-lookup"><span data-stu-id="4a0b1-106">Description</span></span>

<span data-ttu-id="4a0b1-107">给定一个操作 `op` 和一个目标数组 `targets` ，适用于 `op(Rest(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="4a0b1-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="4a0b1-108">输入</span><span class="sxs-lookup"><span data-stu-id="4a0b1-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="4a0b1-109">op： t [] => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="4a0b1-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="4a0b1-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="4a0b1-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="4a0b1-111">目标： t []</span><span class="sxs-lookup"><span data-stu-id="4a0b1-111">targets : 'T[]</span></span>

<span data-ttu-id="4a0b1-112">目标数组，其中除第一个以外的所有将应用于 `op` 。</span><span class="sxs-lookup"><span data-stu-id="4a0b1-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4a0b1-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4a0b1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4a0b1-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="4a0b1-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4a0b1-115">找</span><span class="sxs-lookup"><span data-stu-id="4a0b1-115">'T</span></span>

<span data-ttu-id="4a0b1-116">要应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="4a0b1-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a0b1-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a0b1-117">See Also</span></span>

- [<span data-ttu-id="4a0b1-118">Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="4a0b1-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="4a0b1-119">Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="4a0b1-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="4a0b1-120">Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="4a0b1-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)