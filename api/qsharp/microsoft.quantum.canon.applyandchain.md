---
uid: Microsoft.Quantum.Canon.ApplyAndChain
title: ApplyAndChain 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAndChain
qsharp.summary: Computes a chain of AND gates
ms.openlocfilehash: 3991ded1a9c70bf4b58d19b0304a1df3b31896d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842006"
---
# <a name="applyandchain-operation"></a><span data-ttu-id="e376e-102">ApplyAndChain 操作</span><span class="sxs-lookup"><span data-stu-id="e376e-102">ApplyAndChain operation</span></span>

<span data-ttu-id="e376e-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e376e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e376e-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e376e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e376e-105">计算和入口链</span><span class="sxs-lookup"><span data-stu-id="e376e-105">Computes a chain of AND gates</span></span>

```qsharp
operation ApplyAndChain (auxRegister : Qubit[], ctrlRegister : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="e376e-106">说明</span><span class="sxs-lookup"><span data-stu-id="e376e-106">Description</span></span>

<span data-ttu-id="e376e-107">必须显式指定用于计算临时结果的辅助 qubits。</span><span class="sxs-lookup"><span data-stu-id="e376e-107">The auxiliary qubits to compute temporary results must be specified explicitly.</span></span>
<span data-ttu-id="e376e-108">如果至少有两个控件，则该寄存器的长度为 `Length(ctrlRegister) - 2` ，否则长度为0。</span><span class="sxs-lookup"><span data-stu-id="e376e-108">The length of that register is `Length(ctrlRegister) - 2`, if there are at least two controls, otherwise the length is 0.</span></span>

## <a name="input"></a><span data-ttu-id="e376e-109">输入</span><span class="sxs-lookup"><span data-stu-id="e376e-109">Input</span></span>

### <a name="auxregister--qubit"></a><span data-ttu-id="e376e-110">auxRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e376e-110">auxRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="ctrlregister--qubit"></a><span data-ttu-id="e376e-111">ctrlRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e376e-111">ctrlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="e376e-112">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e376e-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="e376e-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e376e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

