---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: ApplyToEachA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: da901db2bb3c70186bfe0c8812b5710198d1dff3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844605"
---
# <a name="applytoeacha-operation"></a><span data-ttu-id="6bf8a-102">ApplyToEachA 操作</span><span class="sxs-lookup"><span data-stu-id="6bf8a-102">ApplyToEachA operation</span></span>

<span data-ttu-id="6bf8a-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6bf8a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6bf8a-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6bf8a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6bf8a-105">对寄存器中的每个元素应用 qubit 操作。</span><span class="sxs-lookup"><span data-stu-id="6bf8a-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="6bf8a-106">修饰符 `A` 指示 qubit 操作是 adjointable。</span><span class="sxs-lookup"><span data-stu-id="6bf8a-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="6bf8a-107">输入</span><span class="sxs-lookup"><span data-stu-id="6bf8a-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj"></a><span data-ttu-id="6bf8a-108">singleElementOperation： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="6bf8a-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="6bf8a-109">要应用到每个 qubit 的操作。</span><span class="sxs-lookup"><span data-stu-id="6bf8a-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="6bf8a-110">注册： t []</span><span class="sxs-lookup"><span data-stu-id="6bf8a-110">register : 'T[]</span></span>

<span data-ttu-id="6bf8a-111">要在其上应用给定操作的 qubits 数组。</span><span class="sxs-lookup"><span data-stu-id="6bf8a-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6bf8a-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6bf8a-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6bf8a-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="6bf8a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6bf8a-114">找</span><span class="sxs-lookup"><span data-stu-id="6bf8a-114">'T</span></span>

<span data-ttu-id="6bf8a-115">操作的目标。</span><span class="sxs-lookup"><span data-stu-id="6bf8a-115">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="6bf8a-116">示例</span><span class="sxs-lookup"><span data-stu-id="6bf8a-116">Example</span></span>

<span data-ttu-id="6bf8a-117">准备 qubit $ \ket{+} $ 状态：</span><span class="sxs-lookup"><span data-stu-id="6bf8a-117">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="6bf8a-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6bf8a-118">See Also</span></span>

- [<span data-ttu-id="6bf8a-119">Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="6bf8a-119">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)