---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 6ec799885bd2f0d35314ed727356499efbe9fcf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696711"
---
# <a name="realmod-function"></a>RealMod 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

软件包 [](https://nuget.org/packages/)


计算两个实数之间的模数。

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a>输入

### <a name="value--double"></a>值： [Double](xref:microsoft.quantum.lang-ref.double)

一个实数 $x $ 来取的模数。


### <a name="modulo--double"></a>取模： [Double](xref:microsoft.quantum.lang-ref.double)

要对其求 $x $ 的模数的实数。


### <a name="minvalue--double"></a>minValue： [Double](xref:microsoft.quantum.lang-ref.double)

此函数将返回的最小值。



## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>注解

此函数通过包装关于单位圆的实际行，然后查找与输入对应的单位圆上的角度来计算实际的模数。
`minValue`然后，输入有效地指定要将单位圆剪切到何处。