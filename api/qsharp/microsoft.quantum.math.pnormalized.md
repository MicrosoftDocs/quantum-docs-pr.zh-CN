---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: 196bdab67528aa8672a010ac3830459e27276ce9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227516"
---
# <a name="pnormalized-function"></a>PNormalized 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


规范化中的向量 `Double` `L(p)` 。

也就是说，给定类型的数组 $x $ `Double[]` ，这将返回一个数组，其中所有元素均除以 $p $-标准 $ \| x \| _p $。

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a>输入

### <a name="p--double"></a>p： [Double](xref:microsoft.quantum.lang-ref.double)

指数 $p $ $p $-标准。


### <a name="array--double"></a>array： [Double](xref:microsoft.quantum.lang-ref.double)[]





## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)[]

由 $p $-标准 $ \| x _p $ 标准化 $x $ 的数组 \| 。

## <a name="see-also"></a>另请参阅

- [PNorm。](xref:Microsoft.Quantum.Math.PNorm)