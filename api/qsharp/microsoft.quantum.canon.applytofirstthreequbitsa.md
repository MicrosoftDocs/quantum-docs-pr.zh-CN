---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA
title: ApplyToFirstThreeQubitsA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsA
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 502d876df0ed643c40ce6ee48eaf496a90b0f5dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696225"
---
# <a name="applytofirstthreequbitsa-operation"></a><span data-ttu-id="438e6-102">ApplyToFirstThreeQubitsA 操作</span><span class="sxs-lookup"><span data-stu-id="438e6-102">ApplyToFirstThreeQubitsA operation</span></span>

<span data-ttu-id="438e6-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="438e6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="438e6-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="438e6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="438e6-105">将操作应用于寄存器中的前三个 qubits。</span><span class="sxs-lookup"><span data-stu-id="438e6-105">Applies an operation to the first three qubits in the register.</span></span>
<span data-ttu-id="438e6-106">修饰符 `A` 指示操作为 adjointable。</span><span class="sxs-lookup"><span data-stu-id="438e6-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstThreeQubitsA (op : ((Qubit, Qubit, Qubit) => Unit is Adj), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="438e6-107">输入</span><span class="sxs-lookup"><span data-stu-id="438e6-107">Input</span></span>

### <a name="op--qubitqubitqubit--unit-adj"></a><span data-ttu-id="438e6-108">op： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)，[Qubit](xref:microsoft.quantum.lang-ref.qubit)，[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="438e6-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="438e6-109">要应用于前三个 qubits 的操作</span><span class="sxs-lookup"><span data-stu-id="438e6-109">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="438e6-110">register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="438e6-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="438e6-111">Qubit 数组到应用操作的前三个 qubits。</span><span class="sxs-lookup"><span data-stu-id="438e6-111">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="438e6-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="438e6-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="438e6-113">注解</span><span class="sxs-lookup"><span data-stu-id="438e6-113">Remarks</span></span>

<span data-ttu-id="438e6-114">这等效于：</span><span class="sxs-lookup"><span data-stu-id="438e6-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="438e6-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="438e6-115">See Also</span></span>

- [<span data-ttu-id="438e6-116">Canon. ApplyToFirstThreeQubits</span><span class="sxs-lookup"><span data-stu-id="438e6-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)