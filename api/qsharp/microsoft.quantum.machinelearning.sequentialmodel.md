---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: SequentialModel 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: ab9c121884e489b5d056285008c91c1ad70bb053
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854896"
---
# <a name="sequentialmodel-user-defined-type"></a><span data-ttu-id="dc298-102">SequentialModel 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="dc298-102">SequentialModel user defined type</span></span>

<span data-ttu-id="dc298-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="dc298-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="dc298-104">Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="dc298-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="dc298-105">描述一种量程分类器模型，该模型由一系列参数化和控制旋转、旋转角度的赋值和模型所识别的两个类之间的偏差构成。</span><span class="sxs-lookup"><span data-stu-id="dc298-105">Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.</span></span>

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a><span data-ttu-id="dc298-106">命名项</span><span class="sxs-lookup"><span data-stu-id="dc298-106">Named Items</span></span>

### <a name="structure--controlledrotation"></a><span data-ttu-id="dc298-107">结构： [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="dc298-107">Structure : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="dc298-108">用于对输入进行分类的受控旋转序列。</span><span class="sxs-lookup"><span data-stu-id="dc298-108">The sequence of controlled rotations used to classify inputs.</span></span>
### <a name="parameters--double"></a><span data-ttu-id="dc298-109">参数： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="dc298-109">Parameters : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="dc298-110">向给定分类结构分配旋转角度。</span><span class="sxs-lookup"><span data-stu-id="dc298-110">An assignment of rotation angles to the given classification structure.</span></span>
### <a name="bias--double"></a><span data-ttu-id="dc298-111">偏置： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="dc298-111">Bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="dc298-112">此分类器识别的两个类之间的偏差。</span><span class="sxs-lookup"><span data-stu-id="dc298-112">The bias between the two classes recognized by this classifier.</span></span>

## <a name="references"></a><span data-ttu-id="dc298-113">参考</span><span class="sxs-lookup"><span data-stu-id="dc298-113">References</span></span>

- [<span data-ttu-id="dc298-114">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="dc298-114">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)