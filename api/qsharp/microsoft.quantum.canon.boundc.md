---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 6b640c0dab14778336f42098e699e7e68cc726df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841047"
---
# <a name="boundc-function"></a><span data-ttu-id="a985f-102">BoundC 函数</span><span class="sxs-lookup"><span data-stu-id="a985f-102">BoundC function</span></span>

<span data-ttu-id="a985f-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a985f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a985f-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a985f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a985f-105">给定针对单个输入的操作数组时，将生成一个按顺序执行每个给定操作的新操作。</span><span class="sxs-lookup"><span data-stu-id="a985f-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="a985f-106">修饰符 `C` 指示数组中的所有操作都可控制。</span><span class="sxs-lookup"><span data-stu-id="a985f-106">The modifier `C` indicates that all operations in the array are controllable.</span></span>

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="a985f-107">输入</span><span class="sxs-lookup"><span data-stu-id="a985f-107">Input</span></span>

### <a name="operations--t--unit--is-ctl"></a><span data-ttu-id="a985f-108">操作：不 => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl []</span><span class="sxs-lookup"><span data-stu-id="a985f-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="a985f-109">要对给定输入执行的一系列操作。</span><span class="sxs-lookup"><span data-stu-id="a985f-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="a985f-110">输出：不 => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="a985f-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="a985f-111">一项新的操作，它对其输入按顺序执行每个给定的操作。</span><span class="sxs-lookup"><span data-stu-id="a985f-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a985f-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="a985f-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a985f-113">找</span><span class="sxs-lookup"><span data-stu-id="a985f-113">'T</span></span>

<span data-ttu-id="a985f-114">数组中的每个操作的作用。</span><span class="sxs-lookup"><span data-stu-id="a985f-114">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="a985f-115">示例</span><span class="sxs-lookup"><span data-stu-id="a985f-115">Example</span></span>

<span data-ttu-id="a985f-116">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="a985f-116">The following are equivalent:</span></span>

```qsharp
let bound = BoundC([U, V]);
bound(x);
```

<span data-ttu-id="a985f-117">和</span><span class="sxs-lookup"><span data-stu-id="a985f-117">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="a985f-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a985f-118">See Also</span></span>

- [<span data-ttu-id="a985f-119">Canon。</span><span class="sxs-lookup"><span data-stu-id="a985f-119">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)