---
uid: Microsoft.Quantum.Canon.OperationPowA
title: OperationPowA 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 66df354c6de7e48624712276882759043b78466c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695989"
---
# <a name="operationpowa-function"></a><span data-ttu-id="00958-102">OperationPowA 函数</span><span class="sxs-lookup"><span data-stu-id="00958-102">OperationPowA function</span></span>

<span data-ttu-id="00958-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="00958-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="00958-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="00958-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="00958-105">引发幂运算。</span><span class="sxs-lookup"><span data-stu-id="00958-105">Raises an operation to a power.</span></span>
<span data-ttu-id="00958-106">修饰符 `A` 指示操作为 adjointable。</span><span class="sxs-lookup"><span data-stu-id="00958-106">The modifier `A` indicates that the operation is adjointable.</span></span>

<span data-ttu-id="00958-107">也就是说，在给定一个表示入口 $U $ 的操作的情况下，将为 power $m $ $U ^ m $ 返回一个新操作。</span><span class="sxs-lookup"><span data-stu-id="00958-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowA<'T> (op : ('T => Unit is Adj), power : Int) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="00958-108">输入</span><span class="sxs-lookup"><span data-stu-id="00958-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="00958-109">op： t => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="00958-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="00958-110">操作 $U $，表示要重复的入口。</span><span class="sxs-lookup"><span data-stu-id="00958-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="00958-111">幂： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="00958-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="00958-112">重复 $U $ 的次数。</span><span class="sxs-lookup"><span data-stu-id="00958-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit-adj"></a><span data-ttu-id="00958-113">输出：不 => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="00958-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="00958-114">表示 $U ^ m $，其中 $m = \texttt{power} $ 的新操作。</span><span class="sxs-lookup"><span data-stu-id="00958-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="00958-115">类型参数</span><span class="sxs-lookup"><span data-stu-id="00958-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="00958-116">找</span><span class="sxs-lookup"><span data-stu-id="00958-116">'T</span></span>

<span data-ttu-id="00958-117">要为其提供支持的操作的类型。</span><span class="sxs-lookup"><span data-stu-id="00958-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="00958-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00958-118">See Also</span></span>

- [<span data-ttu-id="00958-119">Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="00958-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)