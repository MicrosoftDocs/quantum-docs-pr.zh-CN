---
uid: Microsoft.Quantum.Canon.CControlled
title: CControlled 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: f4d91471eae859b7018c9e7ea0c1c853619c484d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841009"
---
# <a name="ccontrolled-function"></a><span data-ttu-id="6414e-102">CControlled 函数</span><span class="sxs-lookup"><span data-stu-id="6414e-102">CControlled function</span></span>

<span data-ttu-id="6414e-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6414e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6414e-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6414e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6414e-105">给定操作 op，返回一个新操作，该操作将应用操作（如果古典控制位为 true）。</span><span class="sxs-lookup"><span data-stu-id="6414e-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="6414e-106">如果为，则不 `false` 执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="6414e-106">If `false`, nothing happens.</span></span>

```qsharp
function CControlled<'T> (op : ('T => Unit)) : ((Bool, 'T) => Unit)
```


## <a name="input"></a><span data-ttu-id="6414e-107">输入</span><span class="sxs-lookup"><span data-stu-id="6414e-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="6414e-108">op： t => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6414e-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6414e-109">要有条件地应用的操作。</span><span class="sxs-lookup"><span data-stu-id="6414e-109">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit"></a><span data-ttu-id="6414e-110">Output： ([Bool](xref:microsoft.quantum.lang-ref.bool)，不) => [单位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6414e-110">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6414e-111">如果经典控制位为 true，则为 op 的新操作。</span><span class="sxs-lookup"><span data-stu-id="6414e-111">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6414e-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="6414e-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6414e-113">找</span><span class="sxs-lookup"><span data-stu-id="6414e-113">'T</span></span>

<span data-ttu-id="6414e-114">要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="6414e-114">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="6414e-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6414e-115">See Also</span></span>

- [<span data-ttu-id="6414e-116">Canon. CControlledC</span><span class="sxs-lookup"><span data-stu-id="6414e-116">Microsoft.Quantum.Canon.CControlledC</span></span>](xref:Microsoft.Quantum.Canon.CControlledC)
- [<span data-ttu-id="6414e-117">Canon. CControlledA</span><span class="sxs-lookup"><span data-stu-id="6414e-117">Microsoft.Quantum.Canon.CControlledA</span></span>](xref:Microsoft.Quantum.Canon.CControlledA)
- [<span data-ttu-id="6414e-118">Canon. CControlledCA</span><span class="sxs-lookup"><span data-stu-id="6414e-118">Microsoft.Quantum.Canon.CControlledCA</span></span>](xref:Microsoft.Quantum.Canon.CControlledCA)