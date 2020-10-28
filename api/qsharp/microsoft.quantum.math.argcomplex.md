---
uid: Microsoft.Quantum.Math.ArgComplex
title: ArgComplex 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: 629aa32ad80e5aa3d6f5ff75ac65df9b1a96fc15
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700508"
---
# <a name="argcomplex-function"></a>ArgComplex 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

软件包 [](https://nuget.org/packages/)


返回类型为的复数的相位 `Complex` 。

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a>输入

### <a name="input--complex"></a>输入： [复杂](xref:Microsoft.Quantum.Math.Complex)

复数 $c = x + i y $。



## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)

阶段 $ \text{Arg} [c] = \text{ArcTan} (y，x) \in (-\pi，\pi] $。