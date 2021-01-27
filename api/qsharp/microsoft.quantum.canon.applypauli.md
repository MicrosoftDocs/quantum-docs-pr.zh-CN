---
uid: Microsoft.Quantum.Canon.ApplyPauli
title: ApplyPauli 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauli
qsharp.summary: Given a multi-qubit Pauli operator, applies the corresponding operation to a register.
ms.openlocfilehash: b3557c6d8b5a90019f6d4cfa7b405475a3ab39fb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844740"
---
# <a name="applypauli-operation"></a><span data-ttu-id="27ca3-102">ApplyPauli 操作</span><span class="sxs-lookup"><span data-stu-id="27ca3-102">ApplyPauli operation</span></span>

<span data-ttu-id="27ca3-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="27ca3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="27ca3-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="27ca3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="27ca3-105">给定多 qubit Pauli 运算符，将相应的操作应用于寄存器。</span><span class="sxs-lookup"><span data-stu-id="27ca3-105">Given a multi-qubit Pauli operator, applies the corresponding operation to a register.</span></span>

```qsharp
operation ApplyPauli (pauli : Pauli[], target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="27ca3-106">输入</span><span class="sxs-lookup"><span data-stu-id="27ca3-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="27ca3-107">pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="27ca3-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="27ca3-108">多 qubit Pauli 运算符，表示为单个 qubit Pauli 运算符的数组。</span><span class="sxs-lookup"><span data-stu-id="27ca3-108">A multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="27ca3-109">target： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="27ca3-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="27ca3-110">注册以在上应用给定的 Pauli 操作。</span><span class="sxs-lookup"><span data-stu-id="27ca3-110">Register to apply the given Pauli operation on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="27ca3-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="27ca3-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="27ca3-112">示例</span><span class="sxs-lookup"><span data-stu-id="27ca3-112">Example</span></span>

<span data-ttu-id="27ca3-113">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="27ca3-113">The following are equivalent:</span></span>

```qsharp
ApplyPauli([PauliY, PauliZ, PauliX], target);
```

<span data-ttu-id="27ca3-114">和</span><span class="sxs-lookup"><span data-stu-id="27ca3-114">and</span></span>

```qsharp
Y(target[0]);
Z(target[1]);
X(target[2]);
```