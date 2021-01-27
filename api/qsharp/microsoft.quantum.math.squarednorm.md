---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 72ae8266492bef64eaec34cd70c5fe725ee1e8c9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848219"
---
# <a name="squarednorm-function"></a>SquaredNorm 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回向量的2平方标准。

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a>说明

返回向量的2平方值;也就是说，如果输入 $ \vec{x} $，则返回 x_i ^ 2 $ 的 $ \ sum_i。

## <a name="input"></a>输入

### <a name="array--double"></a>array： [Double](xref:microsoft.quantum.lang-ref.double)[]

要返回其方形2标准的向量。



## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)

的2平方标准 `array` 。