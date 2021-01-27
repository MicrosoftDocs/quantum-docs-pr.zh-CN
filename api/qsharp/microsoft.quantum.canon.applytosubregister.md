---
uid: Microsoft.Quantum.Canon.ApplyToSubregister
title: ApplyToSubregister 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregister
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices.
ms.openlocfilehash: be820c87ee19230713d6c3e5681bbe3678040e95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850470"
---
# <a name="applytosubregister-operation"></a><span data-ttu-id="8a222-102">ApplyToSubregister 操作</span><span class="sxs-lookup"><span data-stu-id="8a222-102">ApplyToSubregister operation</span></span>

<span data-ttu-id="8a222-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8a222-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8a222-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8a222-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8a222-105">将操作应用于寄存器的 subregister，其 qubits 由其索引数组指定。</span><span class="sxs-lookup"><span data-stu-id="8a222-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>

```qsharp
operation ApplyToSubregister (op : (Qubit[] => Unit), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="8a222-106">输入</span><span class="sxs-lookup"><span data-stu-id="8a222-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="8a222-107">op： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8a222-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="8a222-108">要应用到 subregister 的操作。</span><span class="sxs-lookup"><span data-stu-id="8a222-108">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="8a222-109">idxs： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8a222-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="8a222-110">索引数组，指示将应用操作的 qubits。</span><span class="sxs-lookup"><span data-stu-id="8a222-110">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="8a222-111">target： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8a222-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8a222-112">注册操作所针对的。</span><span class="sxs-lookup"><span data-stu-id="8a222-112">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8a222-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8a222-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="8a222-114">示例</span><span class="sxs-lookup"><span data-stu-id="8a222-114">Example</span></span>

<span data-ttu-id="8a222-115">Create 三个 qubit state $ \frac {1} {\sqrt {2} } \ket {0} \_ 2 ( \ket {0} \_ 1 \ 票证 {0} _3 + \ket {1} \_ 1 \ 票证 {1} _3) $：</span><span class="sxs-lookup"><span data-stu-id="8a222-115">Create three qubit state $\frac{1}{\sqrt{2}}\ket{0}\_2(\ket{0}\_1\ket{0}_3+\ket{1}\_1\ket{1}_3)$:</span></span>

```qsharp
    using (register = Qubit[3]) {
        ApplyToSubregister(Exp([PauliX,PauliY],PI() / 4.0,_), [1,3], register);
    }
```

## <a name="see-also"></a><span data-ttu-id="8a222-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a222-116">See Also</span></span>

- [<span data-ttu-id="8a222-117">Canon. ApplyToSubregisterA</span><span class="sxs-lookup"><span data-stu-id="8a222-117">Microsoft.Quantum.Canon.ApplyToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterA)
- [<span data-ttu-id="8a222-118">Canon. ApplyToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="8a222-118">Microsoft.Quantum.Canon.ApplyToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterC)
- [<span data-ttu-id="8a222-119">Canon. ApplyToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="8a222-119">Microsoft.Quantum.Canon.ApplyToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterCA)