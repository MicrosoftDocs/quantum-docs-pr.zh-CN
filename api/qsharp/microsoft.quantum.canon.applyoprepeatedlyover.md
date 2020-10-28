---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver
title: ApplyOpRepeatedlyOver 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOver
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 09f54be33a7b5c58a317a949290f5cd6d54fe841
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696294"
---
# <a name="applyoprepeatedlyover-operation"></a><span data-ttu-id="ef779-102">ApplyOpRepeatedlyOver 操作</span><span class="sxs-lookup"><span data-stu-id="ef779-102">ApplyOpRepeatedlyOver operation</span></span>

<span data-ttu-id="ef779-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ef779-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ef779-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ef779-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ef779-105">多次对 qubit 寄存器应用相同的操作。</span><span class="sxs-lookup"><span data-stu-id="ef779-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOver (op : (Qubit[] => Unit), targets : Int[][], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="ef779-106">输入</span><span class="sxs-lookup"><span data-stu-id="ef779-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="ef779-107">op： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ef779-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ef779-108">要在 qubit 寄存器上多次应用的操作</span><span class="sxs-lookup"><span data-stu-id="ef779-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="ef779-109">目标： [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="ef779-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="ef779-110">描述 op 目标的嵌套数组。</span><span class="sxs-lookup"><span data-stu-id="ef779-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="ef779-111">每个数组都应包含一个整数列表，其中包含描述要使用的 qubits 的整数。</span><span class="sxs-lookup"><span data-stu-id="ef779-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="ef779-112">register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ef779-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ef779-113">要对其进行操作的 Qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="ef779-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ef779-114">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ef779-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="ef779-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ef779-115">See Also</span></span>

- [<span data-ttu-id="ef779-116">Canon. ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="ef779-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)