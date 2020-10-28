---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: ReflectAboutInteger 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: e034f0a24d5c2f0465ebd1914b28cb8c695d978c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696596"
---
# <a name="reflectaboutinteger-operation"></a><span data-ttu-id="506c5-102">ReflectAboutInteger 操作</span><span class="sxs-lookup"><span data-stu-id="506c5-102">ReflectAboutInteger operation</span></span>

<span data-ttu-id="506c5-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="506c5-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="506c5-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="506c5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="506c5-105">反映给定的传统整数的量程寄存器。</span><span class="sxs-lookup"><span data-stu-id="506c5-105">Reflects a quantum register about a given classical integer.</span></span>

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="506c5-106">说明</span><span class="sxs-lookup"><span data-stu-id="506c5-106">Description</span></span>

<span data-ttu-id="506c5-107">给定一个量程寄存器，最初处于状态 $ \ sum_i \ alpha_i \ket{i} $，其中每个 $ \ket{i} $ 是表示整数 $i $ 的基本状态，它反映了给定整数 $ \ket{j} $，$ $ \ sum_i ( 的基本状态的寄存器状态，) ^ {\ delta_ {ij}} \ alpha_i \ket{i} $ $</span><span class="sxs-lookup"><span data-stu-id="506c5-107">Given a quantum register initially in the state $\sum_i \alpha_i \ket{i}$, where each $\ket{i}$ is a basis state representing an integer $i$, reflects the state of the register about the basis state for a given integer $\ket{j}$, $$ \sum_i (-1)^{ \delta_{ij} } \alpha_i \ket{i} $$</span></span>

## <a name="input"></a><span data-ttu-id="506c5-108">输入</span><span class="sxs-lookup"><span data-stu-id="506c5-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="506c5-109">索引： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="506c5-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="506c5-110">对要反射的基础状态的传统整数进行索引。</span><span class="sxs-lookup"><span data-stu-id="506c5-110">The classical integer indexing the basis state about which to reflect.</span></span>


### <a name="reg--littleendian"></a><span data-ttu-id="506c5-111">reg： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="506c5-111">reg : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="506c5-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="506c5-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="506c5-113">注解</span><span class="sxs-lookup"><span data-stu-id="506c5-113">Remarks</span></span>

<span data-ttu-id="506c5-114">此操作就地实现，无需显式分配额外的辅助 qubits。</span><span class="sxs-lookup"><span data-stu-id="506c5-114">This operation is implemented in-place, without explicit allocation of additional auxiliary qubits.</span></span>