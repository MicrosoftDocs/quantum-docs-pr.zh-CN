---
uid: Microsoft.Quantum.Math.ArgComplexPolar
title: ArgComplexPolar 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplexPolar
qsharp.summary: Returns the phase of a complex number of type `ComplexPolar`.
ms.openlocfilehash: 5809b5463e6bf8ee73d095dfe4eafedfbb5e0702
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852899"
---
# <a name="argcomplexpolar-function"></a>ArgComplexPolar 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回类型为的复数的相位 `ComplexPolar` 。

```qsharp
function ArgComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a>输入

### <a name="input--complexpolar"></a>输入： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

复数 $c = r e ^ {i t} $。



## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)

阶段 $ \text{Arg} [c] = t $。