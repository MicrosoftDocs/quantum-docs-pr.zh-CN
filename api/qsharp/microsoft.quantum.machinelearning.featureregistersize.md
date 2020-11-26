---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: bc5d5a23cfb431f9506b15bc404ab6955d1c2a35
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196406"
---
# <a name="featureregistersize-function"></a>FeatureRegisterSize 函数

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


返回对特定功能向量进行编码所需的 qubits 的数目。

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a>输入

### <a name="sample--double"></a>示例： [Double](xref:microsoft.quantum.lang-ref.double)[]

要编码到 qubit 寄存器中的示例功能向量。



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

编码为 qubit 寄存器所需的大小 `sample` ，以 qubits 数表示。