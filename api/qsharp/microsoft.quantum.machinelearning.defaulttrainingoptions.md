---
uid: Microsoft.Quantum.MachineLearning.DefaultTrainingOptions
title: DefaultTrainingOptions 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: DefaultTrainingOptions
qsharp.summary: Returns a default set of options for training classifiers.
ms.openlocfilehash: 474683ce5b9ec22bec686fb29d87728afe24d23a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855997"
---
# <a name="defaulttrainingoptions-function"></a>DefaultTrainingOptions 函数

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


返回用于定型分类器的一组默认选项。

```qsharp
function DefaultTrainingOptions () : Microsoft.Quantum.MachineLearning.TrainingOptions
```


## <a name="output--trainingoptions"></a>输出： [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

训练分类器时使用的一组合理的默认定型选项。

## <a name="example"></a>示例

若要使用默认选项，但使用其他度量值，请使用 `w/` 运算符：

```qsharp
let options = DefaultTrainingOptions()
    w/ NMeasurements <- 1000000;
```