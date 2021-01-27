---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 2754e901d74175c1841a38d795f5de02dabc9b8d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848428"
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