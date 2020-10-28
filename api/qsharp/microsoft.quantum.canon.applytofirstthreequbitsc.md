---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC
title: ApplyToFirstThreeQubitsC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsC
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 9450b084cd77f75511fe631cda9a4f9fc426142d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696226"
---
# <a name="applytofirstthreequbitsc-operation"></a><span data-ttu-id="ee53f-102">ApplyToFirstThreeQubitsC 操作</span><span class="sxs-lookup"><span data-stu-id="ee53f-102">ApplyToFirstThreeQubitsC operation</span></span>

<span data-ttu-id="ee53f-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ee53f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ee53f-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ee53f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ee53f-105">将操作应用于寄存器中的前三个 qubits。</span><span class="sxs-lookup"><span data-stu-id="ee53f-105">Applies an operation to the first three qubits in the register.</span></span>
<span data-ttu-id="ee53f-106">修饰符 `C` 指示操作可控制。</span><span class="sxs-lookup"><span data-stu-id="ee53f-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstThreeQubitsC (op : ((Qubit, Qubit, Qubit) => Unit is Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="ee53f-107">输入</span><span class="sxs-lookup"><span data-stu-id="ee53f-107">Input</span></span>

### <a name="op--qubitqubitqubit--unit-ctl"></a><span data-ttu-id="ee53f-108">op： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)，[Qubit](xref:microsoft.quantum.lang-ref.qubit)，[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="ee53f-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="ee53f-109">要应用于前三个 qubits 的操作</span><span class="sxs-lookup"><span data-stu-id="ee53f-109">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="ee53f-110">register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ee53f-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ee53f-111">Qubit 数组到应用操作的前三个 qubits。</span><span class="sxs-lookup"><span data-stu-id="ee53f-111">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ee53f-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ee53f-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ee53f-113">注解</span><span class="sxs-lookup"><span data-stu-id="ee53f-113">Remarks</span></span>

<span data-ttu-id="ee53f-114">这等效于：</span><span class="sxs-lookup"><span data-stu-id="ee53f-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="ee53f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee53f-115">See Also</span></span>

- [<span data-ttu-id="ee53f-116">Canon. ApplyToFirstThreeQubits</span><span class="sxs-lookup"><span data-stu-id="ee53f-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)