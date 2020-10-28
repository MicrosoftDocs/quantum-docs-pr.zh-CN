---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 8f7c47c7547e7a0ac1672f308de445c1b46461e1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700513"
---
# <a name="featureregistersize-function"></a>FeatureRegisterSize 函数

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

软件包 [](https://nuget.org/packages/)


返回对特定功能向量进行编码所需的 qubits 的数目。

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a>输入

### <a name="sample--double"></a>示例： [Double](xref:microsoft.quantum.lang-ref.double)[]

要编码到 qubit 寄存器中的示例功能向量。



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

编码为 qubit 寄存器所需的大小 `sample` ，以 qubits 数表示。