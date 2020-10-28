---
uid: Microsoft.Quantum.Canon.ApplyPauli
title: ApplyPauli 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauli
qsharp.summary: Given a multi-qubit Pauli operator, applies the corresponding operation to a register.
ms.openlocfilehash: ccf8e1b3dbe5d4cd916a581aeab190ab0cff2021
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696289"
---
# <a name="applypauli-operation"></a><span data-ttu-id="614c2-102">ApplyPauli 操作</span><span class="sxs-lookup"><span data-stu-id="614c2-102">ApplyPauli operation</span></span>

<span data-ttu-id="614c2-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="614c2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="614c2-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="614c2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="614c2-105">给定多 qubit Pauli 运算符，将相应的操作应用于寄存器。</span><span class="sxs-lookup"><span data-stu-id="614c2-105">Given a multi-qubit Pauli operator, applies the corresponding operation to a register.</span></span>

```qsharp
operation ApplyPauli (pauli : Pauli[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="614c2-106">输入</span><span class="sxs-lookup"><span data-stu-id="614c2-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="614c2-107">pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="614c2-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="614c2-108">多 qubit Pauli 运算符，表示为单个 qubit Pauli 运算符的数组。</span><span class="sxs-lookup"><span data-stu-id="614c2-108">A multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="614c2-109">target： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="614c2-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="614c2-110">注册以在上应用给定的 Pauli 操作。</span><span class="sxs-lookup"><span data-stu-id="614c2-110">Register to apply the given Pauli operation on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="614c2-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="614c2-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

