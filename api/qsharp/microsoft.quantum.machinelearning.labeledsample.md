---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: b357aae20b5bddb968ce1906fed3c1001efbfde7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846975"
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