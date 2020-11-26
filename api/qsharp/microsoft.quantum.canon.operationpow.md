---
uid: Microsoft.Quantum.Canon.OperationPow
title: OperationPow 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 808001200d276ca21cc5a70140d5d84d96da3496
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205807"
---
# <a name="operationpow-function"></a><span data-ttu-id="cca6e-102">OperationPow 函数</span><span class="sxs-lookup"><span data-stu-id="cca6e-102">OperationPow function</span></span>

<span data-ttu-id="cca6e-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cca6e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cca6e-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cca6e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cca6e-105">引发幂运算。</span><span class="sxs-lookup"><span data-stu-id="cca6e-105">Raises an operation to a power.</span></span>

<span data-ttu-id="cca6e-106">也就是说，在给定一个表示入口 $U $ 的操作的情况下，将为 power $m $ $U ^ m $ 返回一个新操作。</span><span class="sxs-lookup"><span data-stu-id="cca6e-106">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="cca6e-107">输入</span><span class="sxs-lookup"><span data-stu-id="cca6e-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="cca6e-108">op： t => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cca6e-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="cca6e-109">操作 $U $，表示要重复的入口。</span><span class="sxs-lookup"><span data-stu-id="cca6e-109">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="cca6e-110">幂： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cca6e-110">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cca6e-111">重复 $U $ 的次数。</span><span class="sxs-lookup"><span data-stu-id="cca6e-111">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="cca6e-112">输出：不等于> [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cca6e-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="cca6e-113">表示 $U ^ m $，其中 $m = \texttt{power} $ 的新操作。</span><span class="sxs-lookup"><span data-stu-id="cca6e-113">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="cca6e-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="cca6e-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cca6e-115">找</span><span class="sxs-lookup"><span data-stu-id="cca6e-115">'T</span></span>

<span data-ttu-id="cca6e-116">要为其提供支持的操作的类型。</span><span class="sxs-lookup"><span data-stu-id="cca6e-116">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="cca6e-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cca6e-117">See Also</span></span>

- [<span data-ttu-id="cca6e-118">Canon. OperationPowC</span><span class="sxs-lookup"><span data-stu-id="cca6e-118">Microsoft.Quantum.Canon.OperationPowC</span></span>](xref:Microsoft.Quantum.Canon.OperationPowC)
- [<span data-ttu-id="cca6e-119">Canon. OperationPowA</span><span class="sxs-lookup"><span data-stu-id="cca6e-119">Microsoft.Quantum.Canon.OperationPowA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowA)
- [<span data-ttu-id="cca6e-120">Canon. OperationPowCA</span><span class="sxs-lookup"><span data-stu-id="cca6e-120">Microsoft.Quantum.Canon.OperationPowCA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowCA)