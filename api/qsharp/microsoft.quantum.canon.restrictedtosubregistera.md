---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterA
title: RestrictedToSubregisterA 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterA
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: d45c43caed35df8fb89d9d38e540faf5a21ea064
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695963"
---
# <a name="restrictedtosubregistera-function"></a><span data-ttu-id="3c384-102">RestrictedToSubregisterA 函数</span><span class="sxs-lookup"><span data-stu-id="3c384-102">RestrictedToSubregisterA function</span></span>

<span data-ttu-id="3c384-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3c384-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3c384-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3c384-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3c384-105">将操作限制为寄存器的索引数组，即，subregister。</span><span class="sxs-lookup"><span data-stu-id="3c384-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>
<span data-ttu-id="3c384-106">修饰符 `A` 指示操作为 adjointable。</span><span class="sxs-lookup"><span data-stu-id="3c384-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
function RestrictedToSubregisterA (op : (Qubit[] => Unit is Adj), idxs : Int[]) : (Qubit[] => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="3c384-107">输入</span><span class="sxs-lookup"><span data-stu-id="3c384-107">Input</span></span>

### <a name="op--qubit--unit-adj"></a><span data-ttu-id="3c384-108">op： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="3c384-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="3c384-109">要限制为 subregister 的操作。</span><span class="sxs-lookup"><span data-stu-id="3c384-109">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="3c384-110">idxs： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="3c384-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="3c384-111">索引数组，指示将对操作限制的 qubits。</span><span class="sxs-lookup"><span data-stu-id="3c384-111">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit-adj"></a><span data-ttu-id="3c384-112">Output： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="3c384-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>



## <a name="see-also"></a><span data-ttu-id="3c384-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3c384-113">See Also</span></span>

- [<span data-ttu-id="3c384-114">Canon. RestrictedToSubregister</span><span class="sxs-lookup"><span data-stu-id="3c384-114">Microsoft.Quantum.Canon.RestrictedToSubregister</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)