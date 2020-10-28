---
uid: Microsoft.Quantum.Math.ArgComplexPolar
title: ArgComplexPolar 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplexPolar
qsharp.summary: Returns the phase of a complex number of type `ComplexPolar`.
ms.openlocfilehash: b4f2b9a192770f453302b469c80f03a9e57cf891
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700493"
---
# <a name="argcomplexpolar-function"></a>ArgComplexPolar 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

软件包 [](https://nuget.org/packages/)


返回类型为的复数的相位 `ComplexPolar` 。

```qsharp
function ArgComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a>输入

### <a name="input--complexpolar"></a>输入： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

复数 $c = r e ^ {i t} $。



## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)

阶段 $ \text{Arg} [c] = t $。