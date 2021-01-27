---
uid: Microsoft.Quantum.Canon.OperationPowC
title: OperationPowC 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 05b0d5b286e16c308d8c3df8fb8fa1ac8c9868ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852348"
---
# <a name="operationpowc-function"></a><span data-ttu-id="32fce-102">OperationPowC 函数</span><span class="sxs-lookup"><span data-stu-id="32fce-102">OperationPowC function</span></span>

<span data-ttu-id="32fce-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="32fce-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="32fce-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="32fce-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="32fce-105">引发幂运算。</span><span class="sxs-lookup"><span data-stu-id="32fce-105">Raises an operation to a power.</span></span>
<span data-ttu-id="32fce-106">修饰符 `C` 指示操作可控制。</span><span class="sxs-lookup"><span data-stu-id="32fce-106">The modifier `C` indicates that the operation is controllable.</span></span>

<span data-ttu-id="32fce-107">也就是说，在给定一个表示入口 $U $ 的操作的情况下，将为 power $m $ $U ^ m $ 返回一个新操作。</span><span class="sxs-lookup"><span data-stu-id="32fce-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="32fce-108">输入</span><span class="sxs-lookup"><span data-stu-id="32fce-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="32fce-109">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="32fce-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="32fce-110">操作 $U $，表示要重复的入口。</span><span class="sxs-lookup"><span data-stu-id="32fce-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="32fce-111">幂： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="32fce-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="32fce-112">重复 $U $ 的次数。</span><span class="sxs-lookup"><span data-stu-id="32fce-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="32fce-113">输出：不 => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="32fce-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="32fce-114">表示 $U ^ m $，其中 $m = \texttt{power} $ 的新操作。</span><span class="sxs-lookup"><span data-stu-id="32fce-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="32fce-115">类型参数</span><span class="sxs-lookup"><span data-stu-id="32fce-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="32fce-116">找</span><span class="sxs-lookup"><span data-stu-id="32fce-116">'T</span></span>

<span data-ttu-id="32fce-117">要为其提供支持的操作的类型。</span><span class="sxs-lookup"><span data-stu-id="32fce-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="32fce-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="32fce-118">See Also</span></span>

- [<span data-ttu-id="32fce-119">Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="32fce-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)