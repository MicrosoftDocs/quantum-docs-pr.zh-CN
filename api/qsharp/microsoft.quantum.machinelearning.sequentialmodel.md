---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: SequentialModel 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: a425d2155489384ca81ef1c00a5e842bcfb40ae7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700257"
---
# <a name="sequentialmodel-user-defined-type"></a><span data-ttu-id="5e219-102">SequentialModel 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="5e219-102">SequentialModel user defined type</span></span>

<span data-ttu-id="5e219-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="5e219-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="5e219-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5e219-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5e219-105">描述一种量程分类器模型，该模型由一系列参数化和控制旋转、旋转角度的赋值和模型所识别的两个类之间的偏差构成。</span><span class="sxs-lookup"><span data-stu-id="5e219-105">Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.</span></span>

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a><span data-ttu-id="5e219-106">命名项</span><span class="sxs-lookup"><span data-stu-id="5e219-106">Named Items</span></span>

### <a name="structure--controlledrotation"></a><span data-ttu-id="5e219-107">结构： [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="5e219-107">Structure : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="5e219-108">用于对输入进行分类的受控旋转序列。</span><span class="sxs-lookup"><span data-stu-id="5e219-108">The sequence of controlled rotations used to classify inputs.</span></span>
### <a name="parameters--double"></a><span data-ttu-id="5e219-109">参数： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="5e219-109">Parameters : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="5e219-110">向给定分类结构分配旋转角度。</span><span class="sxs-lookup"><span data-stu-id="5e219-110">An assignment of rotation angles to the given classification structure.</span></span>
### <a name="bias--double"></a><span data-ttu-id="5e219-111">偏置： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5e219-111">Bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5e219-112">此分类器识别的两个类之间的偏差。</span><span class="sxs-lookup"><span data-stu-id="5e219-112">The bias between the two classes recognized by this classifier.</span></span>

## <a name="references"></a><span data-ttu-id="5e219-113">参考</span><span class="sxs-lookup"><span data-stu-id="5e219-113">References</span></span>

- [<span data-ttu-id="5e219-114">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="5e219-114">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)