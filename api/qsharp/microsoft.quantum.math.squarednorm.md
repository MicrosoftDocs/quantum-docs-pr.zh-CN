---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 4165a761753f336cb7b94ad36b11ac324ad4e5c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701009"
---
# <a name="squarednorm-function"></a>SquaredNorm 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

软件包 [](https://nuget.org/packages/)


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