---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterC
title: RestrictedToSubregisterC 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterC
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 2ca32cf8c85f33f498a30f71833b3dd69db6da6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695960"
---
# <a name="restrictedtosubregisterc-function"></a><span data-ttu-id="39f60-102">RestrictedToSubregisterC 函数</span><span class="sxs-lookup"><span data-stu-id="39f60-102">RestrictedToSubregisterC function</span></span>

<span data-ttu-id="39f60-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="39f60-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="39f60-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="39f60-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="39f60-105">将操作限制为寄存器的索引数组，即，subregister。</span><span class="sxs-lookup"><span data-stu-id="39f60-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>
<span data-ttu-id="39f60-106">修饰符 `C` 指示操作可控制。</span><span class="sxs-lookup"><span data-stu-id="39f60-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
function RestrictedToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[]) : (Qubit[] => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="39f60-107">输入</span><span class="sxs-lookup"><span data-stu-id="39f60-107">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="39f60-108">op： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="39f60-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="39f60-109">要限制为 subregister 的操作。</span><span class="sxs-lookup"><span data-stu-id="39f60-109">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="39f60-110">idxs： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="39f60-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="39f60-111">索引数组，指示将对操作限制的 qubits。</span><span class="sxs-lookup"><span data-stu-id="39f60-111">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit-ctl"></a><span data-ttu-id="39f60-112">Output： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="39f60-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>



## <a name="see-also"></a><span data-ttu-id="39f60-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39f60-113">See Also</span></span>

- [<span data-ttu-id="39f60-114">Canon. RestrictedToSubregister</span><span class="sxs-lookup"><span data-stu-id="39f60-114">Microsoft.Quantum.Canon.RestrictedToSubregister</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)