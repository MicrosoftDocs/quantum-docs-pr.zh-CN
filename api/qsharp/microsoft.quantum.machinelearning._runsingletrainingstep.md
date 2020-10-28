---
uid: Microsoft.Quantum.MachineLearning._RunSingleTrainingStep
title: _RunSingleTrainingStep 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _RunSingleTrainingStep
qsharp.summary: attempts a single parameter update in the direction of mini batch gradient
ms.openlocfilehash: c40bf6f1ceecef2cb196846b4f5a1c49023f1f74
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696748"
---
# <a name="_runsingletrainingstep-operation"></a><span data-ttu-id="4cc17-102">_RunSingleTrainingStep 操作</span><span class="sxs-lookup"><span data-stu-id="4cc17-102">_RunSingleTrainingStep operation</span></span>

<span data-ttu-id="4cc17-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="4cc17-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="4cc17-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4cc17-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4cc17-105">尝试在小型批处理渐变方向上进行单个参数更新</span><span class="sxs-lookup"><span data-stu-id="4cc17-105">attempts a single parameter update in the direction of mini batch gradient</span></span>

```qsharp
operation _RunSingleTrainingStep (miniBatch : (Microsoft.Quantum.MachineLearning.LabeledSample, Microsoft.Quantum.MachineLearning.StateGenerator)[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, model : Microsoft.Quantum.MachineLearning.SequentialModel) : (Double, Microsoft.Quantum.MachineLearning.SequentialModel)
```


## <a name="input"></a><span data-ttu-id="4cc17-106">输入</span><span class="sxs-lookup"><span data-stu-id="4cc17-106">Input</span></span>

### <a name="minibatch--labeledsamplestategenerator"></a><span data-ttu-id="4cc17-107">miniBatch： ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)，[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)) []</span><span class="sxs-lookup"><span data-stu-id="4cc17-107">miniBatch : ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator))[]</span></span>

<span data-ttu-id="4cc17-108">小型批处理中带标记的示例的容器</span><span class="sxs-lookup"><span data-stu-id="4cc17-108">container of labeled samples in the mini batch</span></span>


### <a name="options--trainingoptions"></a><span data-ttu-id="4cc17-109">选项： [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="4cc17-109">options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>




### <a name="model--sequentialmodel"></a><span data-ttu-id="4cc17-110">模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="4cc17-110">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>





## <a name="output--doublesequentialmodel"></a><span data-ttu-id="4cc17-111">输出： ([Double](xref:microsoft.quantum.lang-ref.double)、[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)) </span><span class="sxs-lookup"><span data-stu-id="4cc17-111">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))</span></span>

<span data-ttu-id="4cc17-112"> (实用工具， (new) 参数) 对</span><span class="sxs-lookup"><span data-stu-id="4cc17-112">(utility, (new)parameters) pair</span></span>