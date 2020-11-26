---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: OperationPowCA 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 32de77cbd54cc8eeb8c4a967fd046dca709cd9ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205637"
---
# <a name="operationpowca-function"></a><span data-ttu-id="7cc93-102">OperationPowCA 函数</span><span class="sxs-lookup"><span data-stu-id="7cc93-102">OperationPowCA function</span></span>

<span data-ttu-id="7cc93-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7cc93-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7cc93-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7cc93-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7cc93-105">引发幂运算。</span><span class="sxs-lookup"><span data-stu-id="7cc93-105">Raises an operation to a power.</span></span>
<span data-ttu-id="7cc93-106">修饰符 `A` 指示该操作是可控制的且 adjointable。</span><span class="sxs-lookup"><span data-stu-id="7cc93-106">The modifier `A` indicates that the operation is controllable and adjointable.</span></span>

<span data-ttu-id="7cc93-107">也就是说，在给定一个表示入口 $U $ 的操作的情况下，将为 power $m $ $U ^ m $ 返回一个新操作。</span><span class="sxs-lookup"><span data-stu-id="7cc93-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="7cc93-108">输入</span><span class="sxs-lookup"><span data-stu-id="7cc93-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="7cc93-109">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="7cc93-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="7cc93-110">操作 $U $，表示要重复的入口。</span><span class="sxs-lookup"><span data-stu-id="7cc93-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="7cc93-111">幂： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7cc93-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7cc93-112">重复 $U $ 的次数。</span><span class="sxs-lookup"><span data-stu-id="7cc93-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit--is-adj--ctl"></a><span data-ttu-id="7cc93-113">输出：不 => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="7cc93-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="7cc93-114">表示 $U ^ m $，其中 $m = \texttt{power} $ 的新操作。</span><span class="sxs-lookup"><span data-stu-id="7cc93-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7cc93-115">类型参数</span><span class="sxs-lookup"><span data-stu-id="7cc93-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7cc93-116">找</span><span class="sxs-lookup"><span data-stu-id="7cc93-116">'T</span></span>

<span data-ttu-id="7cc93-117">要为其提供支持的操作的类型。</span><span class="sxs-lookup"><span data-stu-id="7cc93-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="7cc93-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7cc93-118">See Also</span></span>

- [<span data-ttu-id="7cc93-119">Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="7cc93-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)