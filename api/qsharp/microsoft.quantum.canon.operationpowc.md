---
uid: Microsoft.Quantum.Canon.OperationPowC
title: OperationPowC 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 71f66dd0098ab58d327fc33dbe5af191df0d3dc3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205722"
---
# <a name="operationpowc-function"></a><span data-ttu-id="f2237-102">OperationPowC 函数</span><span class="sxs-lookup"><span data-stu-id="f2237-102">OperationPowC function</span></span>

<span data-ttu-id="f2237-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f2237-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f2237-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f2237-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f2237-105">引发幂运算。</span><span class="sxs-lookup"><span data-stu-id="f2237-105">Raises an operation to a power.</span></span>
<span data-ttu-id="f2237-106">修饰符 `C` 指示操作可控制。</span><span class="sxs-lookup"><span data-stu-id="f2237-106">The modifier `C` indicates that the operation is controllable.</span></span>

<span data-ttu-id="f2237-107">也就是说，在给定一个表示入口 $U $ 的操作的情况下，将为 power $m $ $U ^ m $ 返回一个新操作。</span><span class="sxs-lookup"><span data-stu-id="f2237-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="f2237-108">输入</span><span class="sxs-lookup"><span data-stu-id="f2237-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="f2237-109">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="f2237-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="f2237-110">操作 $U $，表示要重复的入口。</span><span class="sxs-lookup"><span data-stu-id="f2237-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="f2237-111">幂： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f2237-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f2237-112">重复 $U $ 的次数。</span><span class="sxs-lookup"><span data-stu-id="f2237-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="f2237-113">输出：不 => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="f2237-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="f2237-114">表示 $U ^ m $，其中 $m = \texttt{power} $ 的新操作。</span><span class="sxs-lookup"><span data-stu-id="f2237-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f2237-115">类型参数</span><span class="sxs-lookup"><span data-stu-id="f2237-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f2237-116">找</span><span class="sxs-lookup"><span data-stu-id="f2237-116">'T</span></span>

<span data-ttu-id="f2237-117">要为其提供支持的操作的类型。</span><span class="sxs-lookup"><span data-stu-id="f2237-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2237-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2237-118">See Also</span></span>

- [<span data-ttu-id="f2237-119">Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="f2237-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)