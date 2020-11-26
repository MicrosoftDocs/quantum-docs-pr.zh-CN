---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: ApplyToEachA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 9819e78760caf6180edc5c2ca5e402060e3029a5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217792"
---
# <a name="applytoeacha-operation"></a><span data-ttu-id="63ff7-102">ApplyToEachA 操作</span><span class="sxs-lookup"><span data-stu-id="63ff7-102">ApplyToEachA operation</span></span>

<span data-ttu-id="63ff7-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="63ff7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="63ff7-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="63ff7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="63ff7-105">对寄存器中的每个元素应用 qubit 操作。</span><span class="sxs-lookup"><span data-stu-id="63ff7-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="63ff7-106">修饰符 `A` 指示 qubit 操作是 adjointable。</span><span class="sxs-lookup"><span data-stu-id="63ff7-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="63ff7-107">输入</span><span class="sxs-lookup"><span data-stu-id="63ff7-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj"></a><span data-ttu-id="63ff7-108">singleElementOperation： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="63ff7-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="63ff7-109">要应用到每个 qubit 的操作。</span><span class="sxs-lookup"><span data-stu-id="63ff7-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="63ff7-110">注册： t []</span><span class="sxs-lookup"><span data-stu-id="63ff7-110">register : 'T[]</span></span>

<span data-ttu-id="63ff7-111">要在其上应用给定操作的 qubits 数组。</span><span class="sxs-lookup"><span data-stu-id="63ff7-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="63ff7-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="63ff7-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="63ff7-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="63ff7-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="63ff7-114">找</span><span class="sxs-lookup"><span data-stu-id="63ff7-114">'T</span></span>

<span data-ttu-id="63ff7-115">操作的目标。</span><span class="sxs-lookup"><span data-stu-id="63ff7-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="63ff7-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="63ff7-116">See Also</span></span>

- [<span data-ttu-id="63ff7-117">Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="63ff7-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)