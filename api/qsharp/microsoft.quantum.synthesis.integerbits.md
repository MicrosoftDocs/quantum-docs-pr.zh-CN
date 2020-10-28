---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: ab459cd841cdac116cf0e98c094834f628b6a2d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696618"
---
# <a name="integerbits-function"></a>IntegerBits 函数

命名空间 [：](xref:Microsoft.Quantum.Synthesis)

软件包 [](https://nuget.org/packages/)


返回在其中设置整数位的所有位置。

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a>输入

### <a name="value--int"></a>值： [Int](xref:microsoft.quantum.lang-ref.int)

非负数。


### <a name="length--int"></a>长度： [Int](xref:microsoft.quantum.lang-ref.int)

的二进制扩展中的位数 `value` 。



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)[]

一个包含所有位位置的数组， (从 0) 开始，该数组在 `value` 考虑所有位向上定位的二进制扩展中为 1 `length - 1` 。  所有位置都按位置按递增顺序排列在数组中。