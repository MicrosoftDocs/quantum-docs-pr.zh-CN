---
uid: Microsoft.Quantum.Canon.CControlledC
title: CControlledC 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledC
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e5975455385e182236d7e2864e26ca00795a40c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696112"
---
# <a name="ccontrolledc-function"></a><span data-ttu-id="5c47d-102">CControlledC 函数</span><span class="sxs-lookup"><span data-stu-id="5c47d-102">CControlledC function</span></span>

<span data-ttu-id="5c47d-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5c47d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5c47d-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5c47d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5c47d-105">给定操作 op，返回一个新操作，该操作将应用操作（如果古典控制位为 true）。</span><span class="sxs-lookup"><span data-stu-id="5c47d-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="5c47d-106">如果为，则不 `false` 执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="5c47d-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="5c47d-107">修饰符 `C` 指示操作可控制。</span><span class="sxs-lookup"><span data-stu-id="5c47d-107">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
function CControlledC<'T> (op : ('T => Unit is Ctl)) : ((Bool, 'T) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="5c47d-108">输入</span><span class="sxs-lookup"><span data-stu-id="5c47d-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="5c47d-109">op： t => [单元](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="5c47d-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="5c47d-110">要有条件地应用的操作。</span><span class="sxs-lookup"><span data-stu-id="5c47d-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-ctl"></a><span data-ttu-id="5c47d-111">Output： ([Bool](xref:microsoft.quantum.lang-ref.bool)，不) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="5c47d-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="5c47d-112">如果经典控制位为 true，则为 op 的新操作。</span><span class="sxs-lookup"><span data-stu-id="5c47d-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5c47d-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="5c47d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5c47d-114">找</span><span class="sxs-lookup"><span data-stu-id="5c47d-114">'T</span></span>

<span data-ttu-id="5c47d-115">要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="5c47d-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="5c47d-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c47d-116">See Also</span></span>

- [<span data-ttu-id="5c47d-117">Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="5c47d-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)