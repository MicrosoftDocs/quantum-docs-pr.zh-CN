---
uid: Microsoft.Quantum.Math.ArgComplex
title: ArgComplex 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: 259296f397207cde4a7d6dfe6cfb1a18e8055216
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211094"
---
# <a name="argcomplex-function"></a>ArgComplex 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回类型为的复数的相位 `Complex` 。

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a>输入

### <a name="input--complex"></a>输入： [复杂](xref:Microsoft.Quantum.Math.Complex)

复数 $c = x + i y $。



## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)

阶段 $ \text{Arg} [c] = \text{ArcTan} (y，x) \in (-\pi，\pi] $。