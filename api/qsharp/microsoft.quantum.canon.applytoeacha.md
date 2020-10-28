---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: ApplyToEachA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 9485c6549ed4e1a6fb3abdfa3f85ba35579d8b0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696255"
---
# <a name="applytoeacha-operation"></a><span data-ttu-id="3a38f-102">ApplyToEachA 操作</span><span class="sxs-lookup"><span data-stu-id="3a38f-102">ApplyToEachA operation</span></span>

<span data-ttu-id="3a38f-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3a38f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3a38f-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3a38f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3a38f-105">对寄存器中的每个元素应用 qubit 操作。</span><span class="sxs-lookup"><span data-stu-id="3a38f-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="3a38f-106">修饰符 `A` 指示 qubit 操作是 adjointable。</span><span class="sxs-lookup"><span data-stu-id="3a38f-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="3a38f-107">输入</span><span class="sxs-lookup"><span data-stu-id="3a38f-107">Input</span></span>

### <a name="singleelementoperation--t--unit-adj"></a><span data-ttu-id="3a38f-108">singleElementOperation：不等于> [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="3a38f-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="3a38f-109">要应用到每个 qubit 的操作。</span><span class="sxs-lookup"><span data-stu-id="3a38f-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="3a38f-110">注册： t []</span><span class="sxs-lookup"><span data-stu-id="3a38f-110">register : 'T[]</span></span>

<span data-ttu-id="3a38f-111">要在其上应用给定操作的 qubits 数组。</span><span class="sxs-lookup"><span data-stu-id="3a38f-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3a38f-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3a38f-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3a38f-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="3a38f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3a38f-114">找</span><span class="sxs-lookup"><span data-stu-id="3a38f-114">'T</span></span>

<span data-ttu-id="3a38f-115">操作的目标。</span><span class="sxs-lookup"><span data-stu-id="3a38f-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a38f-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a38f-116">See Also</span></span>

- [<span data-ttu-id="3a38f-117">Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="3a38f-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)