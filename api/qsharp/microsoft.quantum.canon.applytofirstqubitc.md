---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitC
title: ApplyToFirstQubitC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitC
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e2c137ad4a8252731acf94d6f2343f8fd386b8e3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696231"
---
# <a name="applytofirstqubitc-operation"></a><span data-ttu-id="e3b56-102">ApplyToFirstQubitC 操作</span><span class="sxs-lookup"><span data-stu-id="e3b56-102">ApplyToFirstQubitC operation</span></span>

<span data-ttu-id="e3b56-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e3b56-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e3b56-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e3b56-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e3b56-105">将操作 op 应用于寄存器中的第一个 qubit。</span><span class="sxs-lookup"><span data-stu-id="e3b56-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="e3b56-106">修饰符 `C` 指示操作可控制。</span><span class="sxs-lookup"><span data-stu-id="e3b56-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstQubitC (op : (Qubit => Unit is Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="e3b56-107">输入</span><span class="sxs-lookup"><span data-stu-id="e3b56-107">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="e3b56-108">op： [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="e3b56-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="e3b56-109">要应用于第一个 qubit 的操作</span><span class="sxs-lookup"><span data-stu-id="e3b56-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="e3b56-110">register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e3b56-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e3b56-111">Qubit 数组到应用操作的第一个 Qubit</span><span class="sxs-lookup"><span data-stu-id="e3b56-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="e3b56-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e3b56-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="e3b56-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3b56-113">See Also</span></span>

- [<span data-ttu-id="e3b56-114">Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="e3b56-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)