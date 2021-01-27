---
uid: Microsoft.Quantum.MachineLearning.ApproximateInputEncoder
title: ApproximateInputEncoder 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApproximateInputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.
ms.openlocfilehash: 035c353c34362aa3486a7df9e7bb1bc95a6f63be
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856166"
---
# <a name="approximateinputencoder-function"></a>ApproximateInputEncoder 函数

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


给定一组系数和公差后，将返回状态准备操作，以便将每个系数准备为计算基础状态的相应波幅，直到达到给定的公差。

```qsharp
function ApproximateInputEncoder (tolerance : Double, coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a>输入

### <a name="tolerance--double"></a>容差： [Double](xref:microsoft.quantum.lang-ref.double)

将给定系数编码为输入状态时使用的近似容差。


### <a name="coefficients--double"></a>系数： [Double](xref:microsoft.quantum.lang-ref.double)[]

要编码为输入状态的系数。



## <a name="output--stategenerator"></a>输出： [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

准备将给定的系数作为给定寄存器上的输入状态的状态准备操作。