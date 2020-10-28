---
uid: Microsoft.Quantum.Canon.ApplyToSubregister
title: ApplyToSubregister 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregister
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices.
ms.openlocfilehash: c9181b8962d36b20f7a9140eb7aaef11aee7faa0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696177"
---
# <a name="applytosubregister-operation"></a><span data-ttu-id="979e9-102">ApplyToSubregister 操作</span><span class="sxs-lookup"><span data-stu-id="979e9-102">ApplyToSubregister operation</span></span>

<span data-ttu-id="979e9-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="979e9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="979e9-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="979e9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="979e9-105">将操作应用于寄存器的 subregister，其 qubits 由其索引数组指定。</span><span class="sxs-lookup"><span data-stu-id="979e9-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>

```qsharp
operation ApplyToSubregister (op : (Qubit[] => Unit), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="979e9-106">输入</span><span class="sxs-lookup"><span data-stu-id="979e9-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="979e9-107">op： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="979e9-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="979e9-108">要应用到 subregister 的操作。</span><span class="sxs-lookup"><span data-stu-id="979e9-108">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="979e9-109">idxs： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="979e9-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="979e9-110">索引数组，指示将应用操作的 qubits。</span><span class="sxs-lookup"><span data-stu-id="979e9-110">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="979e9-111">target： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="979e9-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="979e9-112">注册操作所针对的。</span><span class="sxs-lookup"><span data-stu-id="979e9-112">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="979e9-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="979e9-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="979e9-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="979e9-114">See Also</span></span>

- [<span data-ttu-id="979e9-115">Canon. ApplyToSubregisterA</span><span class="sxs-lookup"><span data-stu-id="979e9-115">Microsoft.Quantum.Canon.ApplyToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterA)
- [<span data-ttu-id="979e9-116">Canon. ApplyToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="979e9-116">Microsoft.Quantum.Canon.ApplyToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterC)
- [<span data-ttu-id="979e9-117">Canon. ApplyToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="979e9-117">Microsoft.Quantum.Canon.ApplyToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterCA)