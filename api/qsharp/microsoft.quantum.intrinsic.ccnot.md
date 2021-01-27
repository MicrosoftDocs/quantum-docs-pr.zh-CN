---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: CCNOT 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: a9186269a868c2ac9d2f15727a3b0ed1bfec3fa4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98819025"
---
# <a name="ccnot-operation"></a><span data-ttu-id="b63b8-102">CCNOT 操作</span><span class="sxs-lookup"><span data-stu-id="b63b8-102">CCNOT operation</span></span>

<span data-ttu-id="b63b8-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="b63b8-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="b63b8-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b63b8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b63b8-105">将双向受控– NOT (CCNOT) 入口应用到三 qubits。</span><span class="sxs-lookup"><span data-stu-id="b63b8-105">Applies the doubly controlled–NOT (CCNOT) gate to three qubits.</span></span>

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b63b8-106">输入</span><span class="sxs-lookup"><span data-stu-id="b63b8-106">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="b63b8-107">control1： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b63b8-107">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b63b8-108">CCNOT 入口的第一个控件 qubit。</span><span class="sxs-lookup"><span data-stu-id="b63b8-108">First control qubit for the CCNOT gate.</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="b63b8-109">control2： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b63b8-109">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b63b8-110">CCNOT 入口的第二个控件 qubit。</span><span class="sxs-lookup"><span data-stu-id="b63b8-110">Second control qubit for the CCNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="b63b8-111">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b63b8-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b63b8-112">CCNOT 入口的目标 qubit。</span><span class="sxs-lookup"><span data-stu-id="b63b8-112">Target qubit for the CCNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b63b8-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b63b8-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b63b8-114">备注</span><span class="sxs-lookup"><span data-stu-id="b63b8-114">Remarks</span></span>

<span data-ttu-id="b63b8-115">等效于：</span><span class="sxs-lookup"><span data-stu-id="b63b8-115">Equivalent to:</span></span>

```qsharp
Controlled X([control1, control2], target);
```