---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: CCNOT 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: 715796ddd915d80036933e3f1ceefa97aa62cecf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212471"
---
# <a name="ccnot-operation"></a><span data-ttu-id="61f92-102">CCNOT 操作</span><span class="sxs-lookup"><span data-stu-id="61f92-102">CCNOT operation</span></span>

<span data-ttu-id="61f92-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="61f92-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="61f92-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="61f92-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="61f92-105">将双向受控– NOT (CCNOT) 入口应用到三 qubits。</span><span class="sxs-lookup"><span data-stu-id="61f92-105">Applies the doubly controlled–NOT (CCNOT) gate to three qubits.</span></span>

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="61f92-106">输入</span><span class="sxs-lookup"><span data-stu-id="61f92-106">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="61f92-107">control1： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="61f92-107">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="61f92-108">CCNOT 入口的第一个控件 qubit。</span><span class="sxs-lookup"><span data-stu-id="61f92-108">First control qubit for the CCNOT gate.</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="61f92-109">control2： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="61f92-109">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="61f92-110">CCNOT 入口的第二个控件 qubit。</span><span class="sxs-lookup"><span data-stu-id="61f92-110">Second control qubit for the CCNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="61f92-111">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="61f92-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="61f92-112">CCNOT 入口的目标 qubit。</span><span class="sxs-lookup"><span data-stu-id="61f92-112">Target qubit for the CCNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="61f92-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="61f92-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="61f92-114">备注</span><span class="sxs-lookup"><span data-stu-id="61f92-114">Remarks</span></span>

<span data-ttu-id="61f92-115">等效于：</span><span class="sxs-lookup"><span data-stu-id="61f92-115">Equivalent to:</span></span>

```qsharp
Controlled X([control1, control2], target);
```