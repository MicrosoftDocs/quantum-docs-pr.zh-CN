---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubit
title: ApplyToFirstQubit 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubit
qsharp.summary: Applies an operation to the first qubit in the register.
ms.openlocfilehash: 381f8d689fba1984ba7fa287d658578bd5b6c48c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850736"
---
# <a name="applytofirstqubit-operation"></a><span data-ttu-id="ba571-102">ApplyToFirstQubit 操作</span><span class="sxs-lookup"><span data-stu-id="ba571-102">ApplyToFirstQubit operation</span></span>

<span data-ttu-id="ba571-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ba571-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ba571-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ba571-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ba571-105">将操作应用于寄存器中的第一个 qubit。</span><span class="sxs-lookup"><span data-stu-id="ba571-105">Applies an operation to the first qubit in the register.</span></span>

```qsharp
operation ApplyToFirstQubit (op : (Qubit => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="ba571-106">输入</span><span class="sxs-lookup"><span data-stu-id="ba571-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="ba571-107">op： [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ba571-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ba571-108">要应用于第一个 qubit 的操作</span><span class="sxs-lookup"><span data-stu-id="ba571-108">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="ba571-109">register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ba571-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ba571-110">Qubit 数组到应用操作的第一个 Qubit</span><span class="sxs-lookup"><span data-stu-id="ba571-110">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="ba571-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ba571-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="ba571-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba571-112">See Also</span></span>

- [<span data-ttu-id="ba571-113">Canon. ApplyToFirstQubitA</span><span class="sxs-lookup"><span data-stu-id="ba571-113">Microsoft.Quantum.Canon.ApplyToFirstQubitA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubitA)
- [<span data-ttu-id="ba571-114">Canon. ApplyToFirstQubitC</span><span class="sxs-lookup"><span data-stu-id="ba571-114">Microsoft.Quantum.Canon.ApplyToFirstQubitC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubitC)
- [<span data-ttu-id="ba571-115">Canon. ApplyToFirstQubitCA</span><span class="sxs-lookup"><span data-stu-id="ba571-115">Microsoft.Quantum.Canon.ApplyToFirstQubitCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubitCA)