---
uid: Microsoft.Quantum.Canon.CControlledCA
title: CControlledCA 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledCA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 20a8c9ccf931261f7bc6e347ccc144c92f0d0545
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696111"
---
# <a name="ccontrolledca-function"></a><span data-ttu-id="d0e7b-102">CControlledCA 函数</span><span class="sxs-lookup"><span data-stu-id="d0e7b-102">CControlledCA function</span></span>

<span data-ttu-id="d0e7b-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d0e7b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d0e7b-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d0e7b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d0e7b-105">给定操作 op，返回一个新操作，该操作将应用操作（如果古典控制位为 true）。</span><span class="sxs-lookup"><span data-stu-id="d0e7b-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="d0e7b-106">如果为，则不 `false` 执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="d0e7b-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="d0e7b-107">修饰符 `CA` 指示该操作是可控制的且 adjointable。</span><span class="sxs-lookup"><span data-stu-id="d0e7b-107">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
function CControlledCA<'T> (op : ('T => Unit is Ctl + Adj)) : ((Bool, 'T) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="d0e7b-108">输入</span><span class="sxs-lookup"><span data-stu-id="d0e7b-108">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="d0e7b-109">op： t => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容词</span><span class="sxs-lookup"><span data-stu-id="d0e7b-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="d0e7b-110">要有条件地应用的操作。</span><span class="sxs-lookup"><span data-stu-id="d0e7b-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-ctl--adj"></a><span data-ttu-id="d0e7b-111">Output： ([Bool](xref:microsoft.quantum.lang-ref.bool)，不) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容词</span><span class="sxs-lookup"><span data-stu-id="d0e7b-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="d0e7b-112">如果经典控制位为 true，则为 op 的新操作。</span><span class="sxs-lookup"><span data-stu-id="d0e7b-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d0e7b-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="d0e7b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d0e7b-114">找</span><span class="sxs-lookup"><span data-stu-id="d0e7b-114">'T</span></span>

<span data-ttu-id="d0e7b-115">要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="d0e7b-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0e7b-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0e7b-116">See Also</span></span>

- [<span data-ttu-id="d0e7b-117">Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="d0e7b-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)