---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: OperationPowCA 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 753063452616747309e3e228ce8a702f4378c61f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695983"
---
# <a name="operationpowca-function"></a><span data-ttu-id="322b7-102">OperationPowCA 函数</span><span class="sxs-lookup"><span data-stu-id="322b7-102">OperationPowCA function</span></span>

<span data-ttu-id="322b7-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="322b7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="322b7-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="322b7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="322b7-105">引发幂运算。</span><span class="sxs-lookup"><span data-stu-id="322b7-105">Raises an operation to a power.</span></span>
<span data-ttu-id="322b7-106">修饰符 `A` 指示该操作是可控制的且 adjointable。</span><span class="sxs-lookup"><span data-stu-id="322b7-106">The modifier `A` indicates that the operation is controllable and adjointable.</span></span>

<span data-ttu-id="322b7-107">也就是说，在给定一个表示入口 $U $ 的操作的情况下，将为 power $m $ $U ^ m $ 返回一个新操作。</span><span class="sxs-lookup"><span data-stu-id="322b7-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="322b7-108">输入</span><span class="sxs-lookup"><span data-stu-id="322b7-108">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="322b7-109">op： t => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容词</span><span class="sxs-lookup"><span data-stu-id="322b7-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="322b7-110">操作 $U $，表示要重复的入口。</span><span class="sxs-lookup"><span data-stu-id="322b7-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="322b7-111">幂： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="322b7-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="322b7-112">重复 $U $ 的次数。</span><span class="sxs-lookup"><span data-stu-id="322b7-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit-ctl--adj"></a><span data-ttu-id="322b7-113">输出：不 => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容词</span><span class="sxs-lookup"><span data-stu-id="322b7-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="322b7-114">表示 $U ^ m $，其中 $m = \texttt{power} $ 的新操作。</span><span class="sxs-lookup"><span data-stu-id="322b7-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="322b7-115">类型参数</span><span class="sxs-lookup"><span data-stu-id="322b7-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="322b7-116">找</span><span class="sxs-lookup"><span data-stu-id="322b7-116">'T</span></span>

<span data-ttu-id="322b7-117">要为其提供支持的操作的类型。</span><span class="sxs-lookup"><span data-stu-id="322b7-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="322b7-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="322b7-118">See Also</span></span>

- [<span data-ttu-id="322b7-119">Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="322b7-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)