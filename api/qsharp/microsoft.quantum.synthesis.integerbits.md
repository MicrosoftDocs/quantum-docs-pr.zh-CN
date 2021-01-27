---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: 3352c1b3003ee387fb03b72461fedb400e29046d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855404"
---
# <a name="integerbits-function"></a>IntegerBits 函数

命名空间 [：](xref:Microsoft.Quantum.Synthesis)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>示例

```qsharp
IntegerBits(23, 5); // [0, 1, 2, 4]
IntegerBits(10, 4); // [1, 3]
```