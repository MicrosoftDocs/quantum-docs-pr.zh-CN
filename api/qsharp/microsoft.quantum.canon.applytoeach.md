---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: ApplyToEach 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: 61dda69751989ef8a98fa8fb01d832014ec4ad35
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844619"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="cbff1-102">ApplyToEach 操作</span><span class="sxs-lookup"><span data-stu-id="cbff1-102">ApplyToEach operation</span></span>

<span data-ttu-id="cbff1-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cbff1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cbff1-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cbff1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cbff1-105">对寄存器中的每个元素应用 qubit 操作。</span><span class="sxs-lookup"><span data-stu-id="cbff1-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="cbff1-106">输入</span><span class="sxs-lookup"><span data-stu-id="cbff1-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="cbff1-107">singleElementOperation：不等于> [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cbff1-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="cbff1-108">要应用到每个 qubit 的操作。</span><span class="sxs-lookup"><span data-stu-id="cbff1-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="cbff1-109">注册： t []</span><span class="sxs-lookup"><span data-stu-id="cbff1-109">register : 'T[]</span></span>

<span data-ttu-id="cbff1-110">要在其上应用给定操作的 qubits 数组。</span><span class="sxs-lookup"><span data-stu-id="cbff1-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cbff1-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cbff1-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="cbff1-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="cbff1-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cbff1-113">找</span><span class="sxs-lookup"><span data-stu-id="cbff1-113">'T</span></span>

<span data-ttu-id="cbff1-114">操作的目标。</span><span class="sxs-lookup"><span data-stu-id="cbff1-114">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="cbff1-115">示例</span><span class="sxs-lookup"><span data-stu-id="cbff1-115">Example</span></span>

<span data-ttu-id="cbff1-116">准备 qubit $ \ket{+} $ 状态：</span><span class="sxs-lookup"><span data-stu-id="cbff1-116">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="cbff1-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cbff1-117">See Also</span></span>

- [<span data-ttu-id="cbff1-118">Canon. ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="cbff1-118">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="cbff1-119">Canon. ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="cbff1-119">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="cbff1-120">Canon. ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="cbff1-120">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)