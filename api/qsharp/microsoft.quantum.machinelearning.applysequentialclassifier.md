---
uid: Microsoft.Quantum.MachineLearning.ApplySequentialClassifier
title: ApplySequentialClassifier 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApplySequentialClassifier
qsharp.summary: Given the structure and parameterization of a sequential classifier, applies the classifier to a register of qubits.
ms.openlocfilehash: 1b4b4853491489f11f222507bb14b48e941e7859
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696735"
---
# <a name="applysequentialclassifier-operation"></a><span data-ttu-id="0522e-102">ApplySequentialClassifier 操作</span><span class="sxs-lookup"><span data-stu-id="0522e-102">ApplySequentialClassifier operation</span></span>

<span data-ttu-id="0522e-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="0522e-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="0522e-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0522e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0522e-105">给定顺序分类器的结构和参数化，将分类器应用到 qubits 的寄存器。</span><span class="sxs-lookup"><span data-stu-id="0522e-105">Given the structure and parameterization of a sequential classifier, applies the classifier to a register of qubits.</span></span>

```qsharp
operation ApplySequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="0522e-106">输入</span><span class="sxs-lookup"><span data-stu-id="0522e-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="0522e-107">模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="0522e-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>




### <a name="qubits--qubit"></a><span data-ttu-id="0522e-108">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0522e-108">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0522e-109">应应用分类器的目标寄存器。</span><span class="sxs-lookup"><span data-stu-id="0522e-109">A target register to which the classifier should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0522e-110">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0522e-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

