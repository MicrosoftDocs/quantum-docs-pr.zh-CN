---
uid: Microsoft.Quantum.Math.AbsComplex
title: AbsComplex 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplex
qsharp.summary: Returns the absolute value of a complex number of type `Complex`.
ms.openlocfilehash: 2bb4caa140bef36d893da834eac1c94b8dd8b0e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846065"
---
# <a name="abscomplex-function"></a>AbsComplex 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回类型的复数的绝对值 `Complex` 。

```qsharp
function AbsComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a>输入

### <a name="input--complex"></a>输入： [复杂](xref:Microsoft.Quantum.Math.Complex)

复数 $c = x + i y $。



## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)

绝对值 $ | c |= \sqrt{x ^ 2 + y ^ 2} $。