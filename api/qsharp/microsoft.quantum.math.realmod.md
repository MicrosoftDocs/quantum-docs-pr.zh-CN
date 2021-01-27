---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 56da313fabb20655ec358120b8d9b435e4971159
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848347"
---
# <a name="realmod-function"></a>RealMod 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="example"></a>示例

```qsharp
    // Returns 3 π / 2.
    let y = RealMod(5.5 * PI(), 2.0 * PI(), 0.0);
    // Returns -1.2, since +3.6 and -1.2 are 4.8 apart on the real line,
    // which is a multiple of 2.4.
    let z = RealMod(3.6, 2.4, -1.2);
```

## <a name="remarks"></a>备注

此函数通过包装关于单位圆的实际行，然后查找与输入对应的单位圆上的角度来计算实际的模数。
`minValue`然后，输入有效地指定要将单位圆剪切到何处。