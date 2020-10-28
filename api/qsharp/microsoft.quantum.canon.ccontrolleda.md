---
uid: Microsoft.Quantum.Canon.CControlledA
title: CControlledA 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 30b5e3408fa6e5a79b2f3d63cccc11899c0405ef
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696113"
---
# <a name="ccontrolleda-function"></a><span data-ttu-id="0b87f-102">CControlledA 函数</span><span class="sxs-lookup"><span data-stu-id="0b87f-102">CControlledA function</span></span>

<span data-ttu-id="0b87f-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0b87f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0b87f-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0b87f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0b87f-105">给定操作 op，返回一个新操作，该操作将应用操作（如果古典控制位为 true）。</span><span class="sxs-lookup"><span data-stu-id="0b87f-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="0b87f-106">如果为，则不 `false` 执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="0b87f-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="0b87f-107">修饰符 `A` 指示操作为 adjointable。</span><span class="sxs-lookup"><span data-stu-id="0b87f-107">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
function CControlledA<'T> (op : ('T => Unit is Adj)) : ((Bool, 'T) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="0b87f-108">输入</span><span class="sxs-lookup"><span data-stu-id="0b87f-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="0b87f-109">op： t => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="0b87f-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="0b87f-110">要有条件地应用的操作。</span><span class="sxs-lookup"><span data-stu-id="0b87f-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-adj"></a><span data-ttu-id="0b87f-111">Output： ([Bool](xref:microsoft.quantum.lang-ref.bool)，不) => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="0b87f-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="0b87f-112">如果经典控制位为 true，则为 op 的新操作。</span><span class="sxs-lookup"><span data-stu-id="0b87f-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0b87f-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="0b87f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0b87f-114">找</span><span class="sxs-lookup"><span data-stu-id="0b87f-114">'T</span></span>

<span data-ttu-id="0b87f-115">要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="0b87f-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b87f-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b87f-116">See Also</span></span>

- [<span data-ttu-id="0b87f-117">Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="0b87f-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)