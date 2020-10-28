---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubits
title: ApplyToFirstThreeQubits 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubits
qsharp.summary: Applies an operation to the first three qubits in the register.
ms.openlocfilehash: 61330f9e9b1f6b9f3965c9240505814b295aaefe
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696227"
---
# <a name="applytofirstthreequbits-operation"></a><span data-ttu-id="10c66-102">ApplyToFirstThreeQubits 操作</span><span class="sxs-lookup"><span data-stu-id="10c66-102">ApplyToFirstThreeQubits operation</span></span>

<span data-ttu-id="10c66-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="10c66-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="10c66-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="10c66-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="10c66-105">将操作应用于寄存器中的前三个 qubits。</span><span class="sxs-lookup"><span data-stu-id="10c66-105">Applies an operation to the first three qubits in the register.</span></span>

```qsharp
operation ApplyToFirstThreeQubits (op : ((Qubit, Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="10c66-106">输入</span><span class="sxs-lookup"><span data-stu-id="10c66-106">Input</span></span>

### <a name="op--qubitqubitqubit--unit"></a><span data-ttu-id="10c66-107">op： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)，[Qubit](xref:microsoft.quantum.lang-ref.qubit)，[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="10c66-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="10c66-108">要应用于前三个 qubits 的操作</span><span class="sxs-lookup"><span data-stu-id="10c66-108">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="10c66-109">register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="10c66-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="10c66-110">Qubit 数组到应用操作的前三个 qubits。</span><span class="sxs-lookup"><span data-stu-id="10c66-110">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="10c66-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="10c66-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="10c66-112">注解</span><span class="sxs-lookup"><span data-stu-id="10c66-112">Remarks</span></span>

<span data-ttu-id="10c66-113">这等效于：</span><span class="sxs-lookup"><span data-stu-id="10c66-113">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="10c66-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10c66-114">See Also</span></span>

- [<span data-ttu-id="10c66-115">Canon. ApplyToFirstThreeQubitsC</span><span class="sxs-lookup"><span data-stu-id="10c66-115">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC)
- [<span data-ttu-id="10c66-116">Canon. ApplyToFirstThreeQubitsA</span><span class="sxs-lookup"><span data-stu-id="10c66-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA)
- [<span data-ttu-id="10c66-117">Canon. ApplyToFirstThreeQubitsCA</span><span class="sxs-lookup"><span data-stu-id="10c66-117">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA)