---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: InputEncoder 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: 771cf01866498f4662864939e6946526c2b5827a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695137"
---
# <a name="inputencoder-function"></a>InputEncoder 函数

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

软件包 [](https://nuget.org/packages/)


给定一组系数和公差后，将返回状态准备操作，以便将每个系数准备为计算基础状态的相应波幅。

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a>输入

### <a name="coefficients--double"></a>系数： [Double](xref:microsoft.quantum.lang-ref.double)[]

要编码为输入状态的系数。



## <a name="output--stategenerator"></a>输出： [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

准备将给定的系数作为给定寄存器上的输入状态的状态准备操作。