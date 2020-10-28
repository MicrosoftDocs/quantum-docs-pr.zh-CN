---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterCA
title: RestrictedToSubregisterCA 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterCA
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: e81193a85451b72a69a595fa81a9fb07f3038c22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695962"
---
# <a name="restrictedtosubregisterca-function"></a><span data-ttu-id="2b3d1-102">RestrictedToSubregisterCA 函数</span><span class="sxs-lookup"><span data-stu-id="2b3d1-102">RestrictedToSubregisterCA function</span></span>

<span data-ttu-id="2b3d1-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2b3d1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2b3d1-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2b3d1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2b3d1-105">将操作限制为寄存器的索引数组，即，subregister。</span><span class="sxs-lookup"><span data-stu-id="2b3d1-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>
<span data-ttu-id="2b3d1-106">修饰符 `CA` 指示该操作是可控制的且 adjointable。</span><span class="sxs-lookup"><span data-stu-id="2b3d1-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
function RestrictedToSubregisterCA (op : (Qubit[] => Unit is Adj + Ctl), idxs : Int[]) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="2b3d1-107">输入</span><span class="sxs-lookup"><span data-stu-id="2b3d1-107">Input</span></span>

### <a name="op--qubit--unit-adj--ctl"></a><span data-ttu-id="2b3d1-108">op： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="2b3d1-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="2b3d1-109">要限制为 subregister 的操作。</span><span class="sxs-lookup"><span data-stu-id="2b3d1-109">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="2b3d1-110">idxs： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2b3d1-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2b3d1-111">索引数组，指示将对操作限制的 qubits。</span><span class="sxs-lookup"><span data-stu-id="2b3d1-111">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="2b3d1-112">Output： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="2b3d1-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="see-also"></a><span data-ttu-id="2b3d1-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b3d1-113">See Also</span></span>

- [<span data-ttu-id="2b3d1-114">Canon. RestrictedToSubregister</span><span class="sxs-lookup"><span data-stu-id="2b3d1-114">Microsoft.Quantum.Canon.RestrictedToSubregister</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)