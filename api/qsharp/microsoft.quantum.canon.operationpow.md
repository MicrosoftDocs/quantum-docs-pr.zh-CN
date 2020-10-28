---
uid: Microsoft.Quantum.Canon.OperationPow
title: OperationPow 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 5cf9017175f44a8a0b8f865624a6c312d25aded1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695997"
---
# <a name="operationpow-function"></a><span data-ttu-id="a3c9a-102">OperationPow 函数</span><span class="sxs-lookup"><span data-stu-id="a3c9a-102">OperationPow function</span></span>

<span data-ttu-id="a3c9a-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a3c9a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a3c9a-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a3c9a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a3c9a-105">引发幂运算。</span><span class="sxs-lookup"><span data-stu-id="a3c9a-105">Raises an operation to a power.</span></span>

<span data-ttu-id="a3c9a-106">也就是说，在给定一个表示入口 $U $ 的操作的情况下，将为 power $m $ $U ^ m $ 返回一个新操作。</span><span class="sxs-lookup"><span data-stu-id="a3c9a-106">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="a3c9a-107">输入</span><span class="sxs-lookup"><span data-stu-id="a3c9a-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="a3c9a-108">op： t => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a3c9a-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a3c9a-109">操作 $U $，表示要重复的入口。</span><span class="sxs-lookup"><span data-stu-id="a3c9a-109">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="a3c9a-110">幂： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a3c9a-110">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a3c9a-111">重复 $U $ 的次数。</span><span class="sxs-lookup"><span data-stu-id="a3c9a-111">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="a3c9a-112">输出：不等于> [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a3c9a-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a3c9a-113">表示 $U ^ m $，其中 $m = \texttt{power} $ 的新操作。</span><span class="sxs-lookup"><span data-stu-id="a3c9a-113">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a3c9a-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="a3c9a-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a3c9a-115">找</span><span class="sxs-lookup"><span data-stu-id="a3c9a-115">'T</span></span>

<span data-ttu-id="a3c9a-116">要为其提供支持的操作的类型。</span><span class="sxs-lookup"><span data-stu-id="a3c9a-116">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="a3c9a-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3c9a-117">See Also</span></span>

- [<span data-ttu-id="a3c9a-118">Canon. OperationPowC</span><span class="sxs-lookup"><span data-stu-id="a3c9a-118">Microsoft.Quantum.Canon.OperationPowC</span></span>](xref:Microsoft.Quantum.Canon.OperationPowC)
- [<span data-ttu-id="a3c9a-119">Canon. OperationPowA</span><span class="sxs-lookup"><span data-stu-id="a3c9a-119">Microsoft.Quantum.Canon.OperationPowA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowA)
- [<span data-ttu-id="a3c9a-120">Canon. OperationPowCA</span><span class="sxs-lookup"><span data-stu-id="a3c9a-120">Microsoft.Quantum.Canon.OperationPowCA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowCA)