---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: a7c7dae5cd9e82d66bb98313f4200838006ca291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196321"
---
# <a name="labeledsample-user-defined-type"></a>LabeledSample 用户定义的类型

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


一个示例，使用该示例所属的类进行标记。

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a>命名项

### <a name="features--double"></a>功能： [Double](xref:microsoft.quantum.lang-ref.double)[]

给定示例的功能矢量。
### <a name="label--int"></a>标签： [Int](xref:microsoft.quantum.lang-ref.int)

此示例所属类的整数标签。