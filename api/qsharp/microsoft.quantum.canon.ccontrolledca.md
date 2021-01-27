---
uid: Microsoft.Quantum.Canon.CControlledCA
title: CControlledCA 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledCA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 740461ee17bdda281a6bd8572a15d27b17be9535
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840959"
---
# <a name="ccontrolledca-function"></a><span data-ttu-id="0ba81-102">CControlledCA 函数</span><span class="sxs-lookup"><span data-stu-id="0ba81-102">CControlledCA function</span></span>

<span data-ttu-id="0ba81-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0ba81-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0ba81-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0ba81-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0ba81-105">给定操作 op，返回一个新操作，该操作将应用操作（如果古典控制位为 true）。</span><span class="sxs-lookup"><span data-stu-id="0ba81-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="0ba81-106">如果为，则不 `false` 执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="0ba81-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="0ba81-107">修饰符 `CA` 指示该操作是可控制的且 adjointable。</span><span class="sxs-lookup"><span data-stu-id="0ba81-107">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
function CControlledCA<'T> (op : ('T => Unit is Ctl + Adj)) : ((Bool, 'T) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="0ba81-108">输入</span><span class="sxs-lookup"><span data-stu-id="0ba81-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="0ba81-109">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="0ba81-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="0ba81-110">要有条件地应用的操作。</span><span class="sxs-lookup"><span data-stu-id="0ba81-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit--is-adj--ctl"></a><span data-ttu-id="0ba81-111">Output： ([Bool](xref:microsoft.quantum.lang-ref.bool)，不) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="0ba81-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="0ba81-112">如果经典控制位为 true，则为 op 的新操作。</span><span class="sxs-lookup"><span data-stu-id="0ba81-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0ba81-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="0ba81-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0ba81-114">找</span><span class="sxs-lookup"><span data-stu-id="0ba81-114">'T</span></span>

<span data-ttu-id="0ba81-115">要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="0ba81-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="0ba81-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0ba81-116">See Also</span></span>

- [<span data-ttu-id="0ba81-117">Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="0ba81-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)