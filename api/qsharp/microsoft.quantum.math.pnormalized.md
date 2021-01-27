---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: ea6a88d07d3b246f666b793f0b10ab6598ea4ff6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854848"
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