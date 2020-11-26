---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: ecbc66a8851f23187e0c0ea53ce121442323733b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227295"
---
# <a name="squarednorm-function"></a>SquaredNorm 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回向量的2平方标准。

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a>描述

返回向量的2平方值;也就是说，如果输入 $ \vec{x} $，则返回 x_i ^ 2 $ 的 $ \ sum_i。

## <a name="input"></a>输入

### <a name="array--double"></a>array： [Double](xref:microsoft.quantum.lang-ref.double)[]

要返回其方形2标准的向量。



## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)

的2平方标准 `array` 。