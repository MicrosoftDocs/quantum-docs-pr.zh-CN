---
uid: Microsoft.Quantum.Math.AbsComplex
title: AbsComplex 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplex
qsharp.summary: Returns the absolute value of a complex number of type `Complex`.
ms.openlocfilehash: d47e04616d4bcf49273bec31fc22990a8244962b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700685"
---
# <a name="abscomplex-function"></a>AbsComplex 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

软件包 [](https://nuget.org/packages/)


返回类型的复数的绝对值 `Complex` 。

```qsharp
function AbsComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a>输入

### <a name="input--complex"></a>输入： [复杂](xref:Microsoft.Quantum.Math.Complex)

复数 $c = x + i y $。



## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)

绝对值 $ | c |= \sqrt{x ^ 2 + y ^ 2} $。