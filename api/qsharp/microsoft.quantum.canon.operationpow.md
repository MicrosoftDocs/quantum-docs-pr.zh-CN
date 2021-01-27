---
uid: Microsoft.Quantum.Canon.OperationPow
title: OperationPow 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 9ed0d32c084f183527cac0586ad699417f51df29
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852378"
---
# <a name="operationpow-function"></a><span data-ttu-id="006a4-102">OperationPow 函数</span><span class="sxs-lookup"><span data-stu-id="006a4-102">OperationPow function</span></span>

<span data-ttu-id="006a4-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="006a4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="006a4-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="006a4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="006a4-105">引发幂运算。</span><span class="sxs-lookup"><span data-stu-id="006a4-105">Raises an operation to a power.</span></span>

<span data-ttu-id="006a4-106">也就是说，在给定一个表示入口 $U $ 的操作的情况下，将为 power $m $ $U ^ m $ 返回一个新操作。</span><span class="sxs-lookup"><span data-stu-id="006a4-106">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="006a4-107">输入</span><span class="sxs-lookup"><span data-stu-id="006a4-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="006a4-108">op： t => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="006a4-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="006a4-109">操作 $U $，表示要重复的入口。</span><span class="sxs-lookup"><span data-stu-id="006a4-109">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="006a4-110">幂： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="006a4-110">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="006a4-111">重复 $U $ 的次数。</span><span class="sxs-lookup"><span data-stu-id="006a4-111">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="006a4-112">输出：不等于> [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="006a4-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="006a4-113">表示 $U ^ m $，其中 $m = \texttt{power} $ 的新操作。</span><span class="sxs-lookup"><span data-stu-id="006a4-113">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="006a4-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="006a4-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="006a4-115">找</span><span class="sxs-lookup"><span data-stu-id="006a4-115">'T</span></span>

<span data-ttu-id="006a4-116">要为其提供支持的操作的类型。</span><span class="sxs-lookup"><span data-stu-id="006a4-116">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="006a4-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="006a4-117">See Also</span></span>

- [<span data-ttu-id="006a4-118">Canon. OperationPowC</span><span class="sxs-lookup"><span data-stu-id="006a4-118">Microsoft.Quantum.Canon.OperationPowC</span></span>](xref:Microsoft.Quantum.Canon.OperationPowC)
- [<span data-ttu-id="006a4-119">Canon. OperationPowA</span><span class="sxs-lookup"><span data-stu-id="006a4-119">Microsoft.Quantum.Canon.OperationPowA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowA)
- [<span data-ttu-id="006a4-120">Canon. OperationPowCA</span><span class="sxs-lookup"><span data-stu-id="006a4-120">Microsoft.Quantum.Canon.OperationPowCA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowCA)