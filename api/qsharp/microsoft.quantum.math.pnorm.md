---
uid: Microsoft.Quantum.Math.PNorm
title: PNorm 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: 3fe029bd893fc4d11aaf351f7ea566256cac5a9e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194723"
---
# <a name="pnorm-function"></a>PNorm 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回 `L(p)` 向量的标准 `Double` 。

也就是说，给定类型的数组 $x $ `Double[]` ，这将返回 $p $-标准 $ \| x \| \_ p = ( \ sum_ {j} | x_j | ^ {p} ) ^ {1/p} $。

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a>输入

### <a name="p--double"></a>p： [Double](xref:microsoft.quantum.lang-ref.double)

指数 $p $ $p $-标准。


### <a name="array--double"></a>array： [Double](xref:microsoft.quantum.lang-ref.double)[]





## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)

$P $-标准 $ \| x \| _p $。