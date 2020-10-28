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
# <a name="applysequentialclassifier-operation"></a>ApplySequentialClassifier 操作

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

软件包 [](https://nuget.org/packages/)


给定顺序分类器的结构和参数化，将分类器应用到 qubits 的寄存器。

```qsharp
operation ApplySequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, qubits : Qubit[]) : Unit
```


## <a name="input"></a>输入

### <a name="model--sequentialmodel"></a>模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)




### <a name="qubits--qubit"></a>qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

应应用分类器的目标寄存器。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

