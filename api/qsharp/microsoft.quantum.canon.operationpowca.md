---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: OperationPowCA 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 338c40f8eb9d6f1782989f2a91c86df561d480bf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852311"
---
# <a name="operationpowca-function"></a><span data-ttu-id="78082-102">OperationPowCA 函数</span><span class="sxs-lookup"><span data-stu-id="78082-102">OperationPowCA function</span></span>

<span data-ttu-id="78082-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="78082-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="78082-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="78082-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="78082-105">引发幂运算。</span><span class="sxs-lookup"><span data-stu-id="78082-105">Raises an operation to a power.</span></span>
<span data-ttu-id="78082-106">修饰符 `A` 指示该操作是可控制的且 adjointable。</span><span class="sxs-lookup"><span data-stu-id="78082-106">The modifier `A` indicates that the operation is controllable and adjointable.</span></span>

<span data-ttu-id="78082-107">也就是说，在给定一个表示入口 $U $ 的操作的情况下，将为 power $m $ $U ^ m $ 返回一个新操作。</span><span class="sxs-lookup"><span data-stu-id="78082-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="78082-108">输入</span><span class="sxs-lookup"><span data-stu-id="78082-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="78082-109">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="78082-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="78082-110">操作 $U $，表示要重复的入口。</span><span class="sxs-lookup"><span data-stu-id="78082-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="78082-111">幂： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="78082-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="78082-112">重复 $U $ 的次数。</span><span class="sxs-lookup"><span data-stu-id="78082-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit--is-adj--ctl"></a><span data-ttu-id="78082-113">输出：不 => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="78082-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="78082-114">表示 $U ^ m $，其中 $m = \texttt{power} $ 的新操作。</span><span class="sxs-lookup"><span data-stu-id="78082-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="78082-115">类型参数</span><span class="sxs-lookup"><span data-stu-id="78082-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="78082-116">找</span><span class="sxs-lookup"><span data-stu-id="78082-116">'T</span></span>

<span data-ttu-id="78082-117">要为其提供支持的操作的类型。</span><span class="sxs-lookup"><span data-stu-id="78082-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="78082-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78082-118">See Also</span></span>

- [<span data-ttu-id="78082-119">Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="78082-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)