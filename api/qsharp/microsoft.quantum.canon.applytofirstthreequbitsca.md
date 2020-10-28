---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA
title: ApplyToFirstThreeQubitsCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsCA
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: bd7a3ac260d370aae9da8691fcd34a8b6221d451
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696222"
---
# <a name="applytofirstthreequbitsca-operation"></a><span data-ttu-id="aa5fc-102">ApplyToFirstThreeQubitsCA 操作</span><span class="sxs-lookup"><span data-stu-id="aa5fc-102">ApplyToFirstThreeQubitsCA operation</span></span>

<span data-ttu-id="aa5fc-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="aa5fc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="aa5fc-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aa5fc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aa5fc-105">将操作应用于寄存器中的前三个 qubits。</span><span class="sxs-lookup"><span data-stu-id="aa5fc-105">Applies an operation to the first three qubits in the register.</span></span>
<span data-ttu-id="aa5fc-106">修饰符 `CA` 指示该操作是可控制的且 adjointable。</span><span class="sxs-lookup"><span data-stu-id="aa5fc-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstThreeQubitsCA (op : ((Qubit, Qubit, Qubit) => Unit is Adj + Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="aa5fc-107">输入</span><span class="sxs-lookup"><span data-stu-id="aa5fc-107">Input</span></span>

### <a name="op--qubitqubitqubit--unit-adj--ctl"></a><span data-ttu-id="aa5fc-108">op： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)，[Qubit](xref:microsoft.quantum.lang-ref.qubit)，[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="aa5fc-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="aa5fc-109">要应用于前三个 qubits 的操作</span><span class="sxs-lookup"><span data-stu-id="aa5fc-109">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="aa5fc-110">register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="aa5fc-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="aa5fc-111">Qubit 数组到应用操作的前三个 qubits。</span><span class="sxs-lookup"><span data-stu-id="aa5fc-111">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aa5fc-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aa5fc-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="aa5fc-113">注解</span><span class="sxs-lookup"><span data-stu-id="aa5fc-113">Remarks</span></span>

<span data-ttu-id="aa5fc-114">这等效于：</span><span class="sxs-lookup"><span data-stu-id="aa5fc-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="aa5fc-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aa5fc-115">See Also</span></span>

- [<span data-ttu-id="aa5fc-116">Canon. ApplyToFirstThreeQubits</span><span class="sxs-lookup"><span data-stu-id="aa5fc-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)