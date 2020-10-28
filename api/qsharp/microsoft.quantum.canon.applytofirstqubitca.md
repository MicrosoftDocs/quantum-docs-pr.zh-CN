---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitCA
title: ApplyToFirstQubitCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitCA
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 2e1db23ad819a85df99a826f406d9b0fbcc7a175
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696229"
---
# <a name="applytofirstqubitca-operation"></a><span data-ttu-id="36134-102">ApplyToFirstQubitCA 操作</span><span class="sxs-lookup"><span data-stu-id="36134-102">ApplyToFirstQubitCA operation</span></span>

<span data-ttu-id="36134-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="36134-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="36134-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="36134-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="36134-105">将操作 op 应用于寄存器中的第一个 qubit。</span><span class="sxs-lookup"><span data-stu-id="36134-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="36134-106">修饰符 `CA` 指示该操作是可控制的且 adjointable。</span><span class="sxs-lookup"><span data-stu-id="36134-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitCA (op : (Qubit => Unit is Adj + Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="36134-107">输入</span><span class="sxs-lookup"><span data-stu-id="36134-107">Input</span></span>

### <a name="op--qubit--unit-adj--ctl"></a><span data-ttu-id="36134-108">op： [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="36134-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="36134-109">要应用于第一个 qubit 的操作</span><span class="sxs-lookup"><span data-stu-id="36134-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="36134-110">register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="36134-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="36134-111">Qubit 数组到应用操作的第一个 Qubit</span><span class="sxs-lookup"><span data-stu-id="36134-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="36134-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="36134-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="36134-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36134-113">See Also</span></span>

- [<span data-ttu-id="36134-114">Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="36134-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)