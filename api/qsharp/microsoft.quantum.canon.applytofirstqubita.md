---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitA
title: ApplyToFirstQubitA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitA
qsharp.summary: Applies an operation to the first qubit in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 00dbff0b562f90653c8569589e838f11e6c938e8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696230"
---
# <a name="applytofirstqubita-operation"></a><span data-ttu-id="8d5af-102">ApplyToFirstQubitA 操作</span><span class="sxs-lookup"><span data-stu-id="8d5af-102">ApplyToFirstQubitA operation</span></span>

<span data-ttu-id="8d5af-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8d5af-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8d5af-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8d5af-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8d5af-105">将操作应用于寄存器中的第一个 qubit。</span><span class="sxs-lookup"><span data-stu-id="8d5af-105">Applies an operation to the first qubit in the register.</span></span>
<span data-ttu-id="8d5af-106">修饰符 `A` 指示操作为 adjointable。</span><span class="sxs-lookup"><span data-stu-id="8d5af-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitA (op : (Qubit => Unit is Adj), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="8d5af-107">输入</span><span class="sxs-lookup"><span data-stu-id="8d5af-107">Input</span></span>

### <a name="op--qubit--unit-adj"></a><span data-ttu-id="8d5af-108">op： [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="8d5af-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="8d5af-109">要应用于第一个 qubit 的操作</span><span class="sxs-lookup"><span data-stu-id="8d5af-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="8d5af-110">register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8d5af-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8d5af-111">Qubit 数组到应用操作的第一个 Qubit</span><span class="sxs-lookup"><span data-stu-id="8d5af-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="8d5af-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8d5af-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="8d5af-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d5af-113">See Also</span></span>

- [<span data-ttu-id="8d5af-114">Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="8d5af-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)