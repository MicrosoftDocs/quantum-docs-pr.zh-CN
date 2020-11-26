---
uid: Microsoft.Quantum.Canon.CControlledC
title: CControlledC 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledC
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 25ac2b35047b1c33a89149eae6d40f6f7ae3b454
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216908"
---
# <a name="ccontrolledc-function"></a><span data-ttu-id="5f2d1-102">CControlledC 函数</span><span class="sxs-lookup"><span data-stu-id="5f2d1-102">CControlledC function</span></span>

<span data-ttu-id="5f2d1-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5f2d1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5f2d1-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5f2d1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5f2d1-105">给定操作 op，返回一个新操作，该操作将应用操作（如果古典控制位为 true）。</span><span class="sxs-lookup"><span data-stu-id="5f2d1-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="5f2d1-106">如果为，则不 `false` 执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="5f2d1-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="5f2d1-107">修饰符 `C` 指示操作可控制。</span><span class="sxs-lookup"><span data-stu-id="5f2d1-107">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
function CControlledC<'T> (op : ('T => Unit is Ctl)) : ((Bool, 'T) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="5f2d1-108">输入</span><span class="sxs-lookup"><span data-stu-id="5f2d1-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="5f2d1-109">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="5f2d1-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="5f2d1-110">要有条件地应用的操作。</span><span class="sxs-lookup"><span data-stu-id="5f2d1-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit--is-ctl"></a><span data-ttu-id="5f2d1-111">Output： ([Bool](xref:microsoft.quantum.lang-ref.bool)，不) => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="5f2d1-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="5f2d1-112">如果经典控制位为 true，则为 op 的新操作。</span><span class="sxs-lookup"><span data-stu-id="5f2d1-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5f2d1-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="5f2d1-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5f2d1-114">找</span><span class="sxs-lookup"><span data-stu-id="5f2d1-114">'T</span></span>

<span data-ttu-id="5f2d1-115">要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="5f2d1-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f2d1-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f2d1-116">See Also</span></span>

- [<span data-ttu-id="5f2d1-117">Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="5f2d1-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)