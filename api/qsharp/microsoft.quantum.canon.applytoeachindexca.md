---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: ApplyToEachIndexCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: 5046edc54576420bd8919ca52947076aed17cbce
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850801"
---
# <a name="applytoeachindexca-operation"></a><span data-ttu-id="2d737-102">ApplyToEachIndexCA 操作</span><span class="sxs-lookup"><span data-stu-id="2d737-102">ApplyToEachIndexCA operation</span></span>

<span data-ttu-id="2d737-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2d737-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2d737-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2d737-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2d737-105">将单 qubit 操作应用于寄存器中的每个索引元素。</span><span class="sxs-lookup"><span data-stu-id="2d737-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="2d737-106">修饰符 `CA` 指示 qubit 操作是 adjointable 和可控制的。</span><span class="sxs-lookup"><span data-stu-id="2d737-106">The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.</span></span>

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2d737-107">输入</span><span class="sxs-lookup"><span data-stu-id="2d737-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-adj--ctl"></a><span data-ttu-id="2d737-108">singleElementOperation： ([Int](xref:microsoft.quantum.lang-ref.int)，is) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="2d737-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="2d737-109">要应用到每个 qubit 的操作。</span><span class="sxs-lookup"><span data-stu-id="2d737-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="2d737-110">注册： t []</span><span class="sxs-lookup"><span data-stu-id="2d737-110">register : 'T[]</span></span>

<span data-ttu-id="2d737-111">要在其上应用给定操作的 qubits 数组。</span><span class="sxs-lookup"><span data-stu-id="2d737-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2d737-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2d737-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2d737-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="2d737-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2d737-114">找</span><span class="sxs-lookup"><span data-stu-id="2d737-114">'T</span></span>

<span data-ttu-id="2d737-115">每个操作操作的目标。</span><span class="sxs-lookup"><span data-stu-id="2d737-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="2d737-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d737-116">See Also</span></span>

- [<span data-ttu-id="2d737-117">Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="2d737-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)