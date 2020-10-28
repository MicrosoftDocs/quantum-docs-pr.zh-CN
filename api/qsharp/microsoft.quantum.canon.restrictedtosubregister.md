---
uid: Microsoft.Quantum.Canon.RestrictedToSubregister
title: RestrictedToSubregister 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregister
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister.
ms.openlocfilehash: a8b599035de6fede10bdaf8cef17f2124a59f064
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695964"
---
# <a name="restrictedtosubregister-function"></a><span data-ttu-id="0b609-102">RestrictedToSubregister 函数</span><span class="sxs-lookup"><span data-stu-id="0b609-102">RestrictedToSubregister function</span></span>

<span data-ttu-id="0b609-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0b609-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0b609-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0b609-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0b609-105">将操作限制为寄存器的索引数组，即，subregister。</span><span class="sxs-lookup"><span data-stu-id="0b609-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>

```qsharp
function RestrictedToSubregister (op : (Qubit[] => Unit), idxs : Int[]) : (Qubit[] => Unit)
```


## <a name="input"></a><span data-ttu-id="0b609-106">输入</span><span class="sxs-lookup"><span data-stu-id="0b609-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="0b609-107">op： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0b609-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0b609-108">要限制为 subregister 的操作。</span><span class="sxs-lookup"><span data-stu-id="0b609-108">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="0b609-109">idxs： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0b609-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0b609-110">索引数组，指示将对操作限制的 qubits。</span><span class="sxs-lookup"><span data-stu-id="0b609-110">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit"></a><span data-ttu-id="0b609-111">Output： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0b609-111">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 



## <a name="see-also"></a><span data-ttu-id="0b609-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b609-112">See Also</span></span>

- [<span data-ttu-id="0b609-113">Canon. RestrictedToSubregisterA</span><span class="sxs-lookup"><span data-stu-id="0b609-113">Microsoft.Quantum.Canon.RestrictedToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterA)
- [<span data-ttu-id="0b609-114">Canon. RestrictedToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="0b609-114">Microsoft.Quantum.Canon.RestrictedToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterC)
- [<span data-ttu-id="0b609-115">Canon. RestrictedToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="0b609-115">Microsoft.Quantum.Canon.RestrictedToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterCA)