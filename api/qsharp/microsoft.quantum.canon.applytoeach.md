---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: ApplyToEach 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: 11f9363feb38676df3f805496c74036aa96160c1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217860"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="c1ff1-102">ApplyToEach 操作</span><span class="sxs-lookup"><span data-stu-id="c1ff1-102">ApplyToEach operation</span></span>

<span data-ttu-id="c1ff1-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c1ff1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c1ff1-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c1ff1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c1ff1-105">对寄存器中的每个元素应用 qubit 操作。</span><span class="sxs-lookup"><span data-stu-id="c1ff1-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c1ff1-106">输入</span><span class="sxs-lookup"><span data-stu-id="c1ff1-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="c1ff1-107">singleElementOperation：不等于> [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c1ff1-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c1ff1-108">要应用到每个 qubit 的操作。</span><span class="sxs-lookup"><span data-stu-id="c1ff1-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="c1ff1-109">注册： t []</span><span class="sxs-lookup"><span data-stu-id="c1ff1-109">register : 'T[]</span></span>

<span data-ttu-id="c1ff1-110">要在其上应用给定操作的 qubits 数组。</span><span class="sxs-lookup"><span data-stu-id="c1ff1-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c1ff1-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c1ff1-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c1ff1-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="c1ff1-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c1ff1-113">找</span><span class="sxs-lookup"><span data-stu-id="c1ff1-113">'T</span></span>

<span data-ttu-id="c1ff1-114">操作的目标。</span><span class="sxs-lookup"><span data-stu-id="c1ff1-114">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="c1ff1-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c1ff1-115">See Also</span></span>

- [<span data-ttu-id="c1ff1-116">Canon. ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="c1ff1-116">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="c1ff1-117">Canon. ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="c1ff1-117">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="c1ff1-118">Canon. ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="c1ff1-118">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)