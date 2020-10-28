---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubits
title: ApplyToFirstTwoQubits 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubits
qsharp.summary: Applies an operation to the first two qubits in the register.
ms.openlocfilehash: aad07889c0dbf2329304c98b06dbd0c225df8a81
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696217"
---
# <a name="applytofirsttwoqubits-operation"></a><span data-ttu-id="6b556-102">ApplyToFirstTwoQubits 操作</span><span class="sxs-lookup"><span data-stu-id="6b556-102">ApplyToFirstTwoQubits operation</span></span>

<span data-ttu-id="6b556-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6b556-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6b556-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6b556-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6b556-105">将操作应用于寄存器中的前两个 qubits。</span><span class="sxs-lookup"><span data-stu-id="6b556-105">Applies an operation to the first two qubits in the register.</span></span>

```qsharp
operation ApplyToFirstTwoQubits (op : ((Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="6b556-106">输入</span><span class="sxs-lookup"><span data-stu-id="6b556-106">Input</span></span>

### <a name="op--qubitqubit--unit"></a><span data-ttu-id="6b556-107">op： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)，[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6b556-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6b556-108">要应用于前两个 qubits 的操作</span><span class="sxs-lookup"><span data-stu-id="6b556-108">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="6b556-109">register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6b556-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6b556-110">Qubit 数组指向应用了该操作的前两个 qubits。</span><span class="sxs-lookup"><span data-stu-id="6b556-110">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6b556-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6b556-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6b556-112">注解</span><span class="sxs-lookup"><span data-stu-id="6b556-112">Remarks</span></span>

<span data-ttu-id="6b556-113">这等效于：</span><span class="sxs-lookup"><span data-stu-id="6b556-113">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="6b556-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b556-114">See Also</span></span>

- [<span data-ttu-id="6b556-115">Canon. ApplyToFirstTwoQubitsA</span><span class="sxs-lookup"><span data-stu-id="6b556-115">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA)
- [<span data-ttu-id="6b556-116">Canon. ApplyToFirstTwoQubitsC</span><span class="sxs-lookup"><span data-stu-id="6b556-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC)
- [<span data-ttu-id="6b556-117">Canon. ApplyToFirstTwoQubitsCA</span><span class="sxs-lookup"><span data-stu-id="6b556-117">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA)