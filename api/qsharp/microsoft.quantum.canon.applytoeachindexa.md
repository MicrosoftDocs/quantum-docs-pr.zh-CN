---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexA
title: ApplyToEachIndexA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: e3ff812f14181e676fddf436af8a14f9a58271ec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217588"
---
# <a name="applytoeachindexa-operation"></a><span data-ttu-id="0834f-102">ApplyToEachIndexA 操作</span><span class="sxs-lookup"><span data-stu-id="0834f-102">ApplyToEachIndexA operation</span></span>

<span data-ttu-id="0834f-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0834f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0834f-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0834f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0834f-105">将单 qubit 操作应用于寄存器中的每个索引元素。</span><span class="sxs-lookup"><span data-stu-id="0834f-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="0834f-106">修饰符 `A` 指示 qubit 操作是 adjointable。</span><span class="sxs-lookup"><span data-stu-id="0834f-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachIndexA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="0834f-107">输入</span><span class="sxs-lookup"><span data-stu-id="0834f-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-adj"></a><span data-ttu-id="0834f-108">singleElementOperation： ([Int](xref:microsoft.quantum.lang-ref.int)，is) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="0834f-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="0834f-109">要应用到每个 qubit 的操作。</span><span class="sxs-lookup"><span data-stu-id="0834f-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="0834f-110">注册： t []</span><span class="sxs-lookup"><span data-stu-id="0834f-110">register : 'T[]</span></span>

<span data-ttu-id="0834f-111">要在其上应用给定操作的 qubits 数组。</span><span class="sxs-lookup"><span data-stu-id="0834f-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0834f-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0834f-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0834f-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="0834f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0834f-114">找</span><span class="sxs-lookup"><span data-stu-id="0834f-114">'T</span></span>

<span data-ttu-id="0834f-115">每个操作操作的目标。</span><span class="sxs-lookup"><span data-stu-id="0834f-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="0834f-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0834f-116">See Also</span></span>

- [<span data-ttu-id="0834f-117">Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="0834f-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)