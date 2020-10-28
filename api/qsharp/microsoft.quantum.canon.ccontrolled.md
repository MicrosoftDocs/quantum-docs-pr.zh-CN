---
uid: Microsoft.Quantum.Canon.CControlled
title: CControlled 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: a155b00806b17258b3f87629659bc7d786e4e11d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696114"
---
# <a name="ccontrolled-function"></a><span data-ttu-id="81e25-102">CControlled 函数</span><span class="sxs-lookup"><span data-stu-id="81e25-102">CControlled function</span></span>

<span data-ttu-id="81e25-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="81e25-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="81e25-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="81e25-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="81e25-105">给定操作 op，返回一个新操作，该操作将应用操作（如果古典控制位为 true）。</span><span class="sxs-lookup"><span data-stu-id="81e25-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="81e25-106">如果为，则不 `false` 执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="81e25-106">If `false`, nothing happens.</span></span>

```qsharp
function CControlled<'T> (op : ('T => Unit)) : ((Bool, 'T) => Unit)
```


## <a name="input"></a><span data-ttu-id="81e25-107">输入</span><span class="sxs-lookup"><span data-stu-id="81e25-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="81e25-108">op： t => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="81e25-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="81e25-109">要有条件地应用的操作。</span><span class="sxs-lookup"><span data-stu-id="81e25-109">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit"></a><span data-ttu-id="81e25-110">Output： ([Bool](xref:microsoft.quantum.lang-ref.bool)，不) => [单位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="81e25-110">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="81e25-111">如果经典控制位为 true，则为 op 的新操作。</span><span class="sxs-lookup"><span data-stu-id="81e25-111">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="81e25-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="81e25-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="81e25-113">找</span><span class="sxs-lookup"><span data-stu-id="81e25-113">'T</span></span>

<span data-ttu-id="81e25-114">要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="81e25-114">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="81e25-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81e25-115">See Also</span></span>

- [<span data-ttu-id="81e25-116">Canon. CControlledC</span><span class="sxs-lookup"><span data-stu-id="81e25-116">Microsoft.Quantum.Canon.CControlledC</span></span>](xref:Microsoft.Quantum.Canon.CControlledC)
- [<span data-ttu-id="81e25-117">Canon. CControlledA</span><span class="sxs-lookup"><span data-stu-id="81e25-117">Microsoft.Quantum.Canon.CControlledA</span></span>](xref:Microsoft.Quantum.Canon.CControlledA)
- [<span data-ttu-id="81e25-118">Canon. CControlledCA</span><span class="sxs-lookup"><span data-stu-id="81e25-118">Microsoft.Quantum.Canon.CControlledCA</span></span>](xref:Microsoft.Quantum.Canon.CControlledCA)