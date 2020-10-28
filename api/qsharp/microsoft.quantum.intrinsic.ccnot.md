---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: CCNOT 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: bf20ff1e9d25d72e7e8e0207ab947a57dc394cf4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695392"
---
# <a name="ccnot-operation"></a><span data-ttu-id="1003f-102">CCNOT 操作</span><span class="sxs-lookup"><span data-stu-id="1003f-102">CCNOT operation</span></span>

<span data-ttu-id="1003f-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="1003f-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="1003f-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1003f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1003f-105">将双向受控– NOT (CCNOT) 入口应用到三 qubits。</span><span class="sxs-lookup"><span data-stu-id="1003f-105">Applies the doubly controlled–NOT (CCNOT) gate to three qubits.</span></span>

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="1003f-106">输入</span><span class="sxs-lookup"><span data-stu-id="1003f-106">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="1003f-107">control1： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1003f-107">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1003f-108">CCNOT 入口的第一个控件 qubit。</span><span class="sxs-lookup"><span data-stu-id="1003f-108">First control qubit for the CCNOT gate.</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="1003f-109">control2： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1003f-109">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1003f-110">CCNOT 入口的第二个控件 qubit。</span><span class="sxs-lookup"><span data-stu-id="1003f-110">Second control qubit for the CCNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="1003f-111">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1003f-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1003f-112">CCNOT 入口的目标 qubit。</span><span class="sxs-lookup"><span data-stu-id="1003f-112">Target qubit for the CCNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1003f-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1003f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1003f-114">注解</span><span class="sxs-lookup"><span data-stu-id="1003f-114">Remarks</span></span>

<span data-ttu-id="1003f-115">等效于：</span><span class="sxs-lookup"><span data-stu-id="1003f-115">Equivalent to:</span></span>

```qsharp
Controlled X([control1, control2], target);
```