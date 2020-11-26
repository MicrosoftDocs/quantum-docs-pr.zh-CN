---
uid: Microsoft.Quantum.Canon.ApplyAndChain
title: ApplyAndChain 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAndChain
qsharp.summary: Computes a chain of AND gates
ms.openlocfilehash: c53bca6ecf964f4358b0a7ff1c61d4e8e195cd7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219356"
---
# <a name="applyandchain-operation"></a><span data-ttu-id="b55a5-102">ApplyAndChain 操作</span><span class="sxs-lookup"><span data-stu-id="b55a5-102">ApplyAndChain operation</span></span>

<span data-ttu-id="b55a5-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b55a5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b55a5-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b55a5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b55a5-105">计算和入口链</span><span class="sxs-lookup"><span data-stu-id="b55a5-105">Computes a chain of AND gates</span></span>

```qsharp
operation ApplyAndChain (auxRegister : Qubit[], ctrlRegister : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="b55a5-106">描述</span><span class="sxs-lookup"><span data-stu-id="b55a5-106">Description</span></span>

<span data-ttu-id="b55a5-107">必须显式指定用于计算临时结果的辅助 qubits。</span><span class="sxs-lookup"><span data-stu-id="b55a5-107">The auxiliary qubits to compute temporary results must be specified explicitly.</span></span>
<span data-ttu-id="b55a5-108">如果至少有两个控件，则该寄存器的长度为 `Length(ctrlRegister) - 2` ，否则长度为0。</span><span class="sxs-lookup"><span data-stu-id="b55a5-108">The length of that register is `Length(ctrlRegister) - 2`, if there are at least two controls, otherwise the length is 0.</span></span>

## <a name="input"></a><span data-ttu-id="b55a5-109">输入</span><span class="sxs-lookup"><span data-stu-id="b55a5-109">Input</span></span>

### <a name="auxregister--qubit"></a><span data-ttu-id="b55a5-110">auxRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b55a5-110">auxRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="ctrlregister--qubit"></a><span data-ttu-id="b55a5-111">ctrlRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b55a5-111">ctrlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="b55a5-112">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b55a5-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="b55a5-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b55a5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

