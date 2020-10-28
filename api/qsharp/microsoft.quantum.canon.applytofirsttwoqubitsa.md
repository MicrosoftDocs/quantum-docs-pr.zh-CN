---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA
title: ApplyToFirstTwoQubitsA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 911e9bc3d02bf6c0395c30fa167a6cb730dc666e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696216"
---
# <a name="applytofirsttwoqubitsa-operation"></a><span data-ttu-id="20392-102">ApplyToFirstTwoQubitsA 操作</span><span class="sxs-lookup"><span data-stu-id="20392-102">ApplyToFirstTwoQubitsA operation</span></span>

<span data-ttu-id="20392-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="20392-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="20392-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="20392-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="20392-105">将操作应用于寄存器中的前两个 qubits。</span><span class="sxs-lookup"><span data-stu-id="20392-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="20392-106">修饰符 `A` 指示操作为 adjointable。</span><span class="sxs-lookup"><span data-stu-id="20392-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsA (op : ((Qubit, Qubit) => Unit is Adj), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="20392-107">输入</span><span class="sxs-lookup"><span data-stu-id="20392-107">Input</span></span>

### <a name="op--qubitqubit--unit-adj"></a><span data-ttu-id="20392-108">op： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)，[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="20392-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="20392-109">要应用于前两个 qubits 的操作</span><span class="sxs-lookup"><span data-stu-id="20392-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="20392-110">register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="20392-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="20392-111">Qubit 数组指向应用了该操作的前两个 qubits。</span><span class="sxs-lookup"><span data-stu-id="20392-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="20392-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="20392-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="20392-113">注解</span><span class="sxs-lookup"><span data-stu-id="20392-113">Remarks</span></span>

<span data-ttu-id="20392-114">这等效于：</span><span class="sxs-lookup"><span data-stu-id="20392-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="20392-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20392-115">See Also</span></span>

- [<span data-ttu-id="20392-116">Canon. ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="20392-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)