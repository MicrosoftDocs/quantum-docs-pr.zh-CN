---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: ControlledRotation 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: 231afe65da3640218cbc97b9d49eae21bf6e1786
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847396"
---
# <a name="controlledrotation-user-defined-type"></a><span data-ttu-id="413c3-102">ControlledRotation 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="413c3-102">ControlledRotation user defined type</span></span>

<span data-ttu-id="413c3-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="413c3-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="413c3-104">Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="413c3-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="413c3-105">描述在其目标和控件索引、旋转轴和模型参数向量的索引方面的受控旋转。</span><span class="sxs-lookup"><span data-stu-id="413c3-105">Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.</span></span>

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a><span data-ttu-id="413c3-106">命名项</span><span class="sxs-lookup"><span data-stu-id="413c3-106">Named Items</span></span>

### <a name="targetindex--int"></a><span data-ttu-id="413c3-107">TargetIndex： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="413c3-107">TargetIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="413c3-108">此受控旋转的目标 qubit 的索引。</span><span class="sxs-lookup"><span data-stu-id="413c3-108">Index of the target qubit for this controlled rotation.</span></span>
### <a name="controlindices--int"></a><span data-ttu-id="413c3-109">ControlIndices： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="413c3-109">ControlIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="413c3-110">此旋转的控件 qubit 索引的数组。</span><span class="sxs-lookup"><span data-stu-id="413c3-110">An array of the control qubit indices for this rotation.</span></span>
### <a name="axis--pauli"></a><span data-ttu-id="413c3-111">轴： [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="413c3-111">Axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="413c3-112">此旋转的轴。</span><span class="sxs-lookup"><span data-stu-id="413c3-112">The axis for this rotation.</span></span>
### <a name="parameterindex--int"></a><span data-ttu-id="413c3-113">ParameterIndex： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="413c3-113">ParameterIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="413c3-114">用于描述此旋转角度的模型参数向量的索引。</span><span class="sxs-lookup"><span data-stu-id="413c3-114">An index into a model parameter vector describing the angle for this rotation.</span></span>

## <a name="example"></a><span data-ttu-id="413c3-115">示例</span><span class="sxs-lookup"><span data-stu-id="413c3-115">Example</span></span>

<span data-ttu-id="413c3-116">以下内容表示对寄存器中第一个 qubit 的 $X $ 轴的旋转，在第二个 qubit 上控制，以及在顺序模型中使用第四个参数提供的角度：</span><span class="sxs-lookup"><span data-stu-id="413c3-116">The following represents a rotation about the $X$-axis of the first qubit in a register, controlled on the second qubit, and with an angle given by the fourth parameter in a sequential model:</span></span>

```qsharp
let controlledRotation = ControlledRotation(
    (0, [1]),
    PauliX,
    3
)
```

## <a name="remarks"></a><span data-ttu-id="413c3-117">备注</span><span class="sxs-lookup"><span data-stu-id="413c3-117">Remarks</span></span>

<span data-ttu-id="413c3-118">通过将设置 `ControlIndices` 为空的索引数组，可以表示无法控制的旋转 `new Int[0]` 。</span><span class="sxs-lookup"><span data-stu-id="413c3-118">An uncontrolled rotation can be represented by setting `ControlIndices` to an empty array of indexes, `new Int[0]`.</span></span>