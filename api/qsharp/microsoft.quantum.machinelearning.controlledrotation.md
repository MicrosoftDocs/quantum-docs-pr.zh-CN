---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: ControlledRotation 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: afc425c16ab550fd414e656484c9ff6f0f8f3ef4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695367"
---
# <a name="controlledrotation-user-defined-type"></a><span data-ttu-id="c3171-102">ControlledRotation 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="c3171-102">ControlledRotation user defined type</span></span>

<span data-ttu-id="c3171-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c3171-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="c3171-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c3171-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c3171-105">描述在其目标和控件索引、旋转轴和模型参数向量的索引方面的受控旋转。</span><span class="sxs-lookup"><span data-stu-id="c3171-105">Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.</span></span>

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a><span data-ttu-id="c3171-106">命名项</span><span class="sxs-lookup"><span data-stu-id="c3171-106">Named Items</span></span>

### <a name="targetindex--int"></a><span data-ttu-id="c3171-107">TargetIndex： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c3171-107">TargetIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c3171-108">此受控旋转的目标 qubit 的索引。</span><span class="sxs-lookup"><span data-stu-id="c3171-108">Index of the target qubit for this controlled rotation.</span></span>
### <a name="controlindices--int"></a><span data-ttu-id="c3171-109">ControlIndices： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c3171-109">ControlIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c3171-110">此旋转的控件 qubit 索引的数组。</span><span class="sxs-lookup"><span data-stu-id="c3171-110">An array of the control qubit indices for this rotation.</span></span>
### <a name="axis--pauli"></a><span data-ttu-id="c3171-111">轴： [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="c3171-111">Axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="c3171-112">此旋转的轴。</span><span class="sxs-lookup"><span data-stu-id="c3171-112">The axis for this rotation.</span></span>
### <a name="parameterindex--int"></a><span data-ttu-id="c3171-113">ParameterIndex： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c3171-113">ParameterIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c3171-114">用于描述此旋转角度的模型参数向量的索引。</span><span class="sxs-lookup"><span data-stu-id="c3171-114">An index into a model parameter vector describing the angle for this rotation.</span></span>

## <a name="remarks"></a><span data-ttu-id="c3171-115">注解</span><span class="sxs-lookup"><span data-stu-id="c3171-115">Remarks</span></span>

<span data-ttu-id="c3171-116">通过将设置 `ControlIndices` 为空的索引数组，可以表示无法控制的旋转 `new Int[0]` 。</span><span class="sxs-lookup"><span data-stu-id="c3171-116">An uncontrolled rotation can be represented by setting `ControlIndices` to an empty array of indexes, `new Int[0]`.</span></span>