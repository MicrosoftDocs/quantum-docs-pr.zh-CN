---
uid: Microsoft.Quantum.Math.ModulusI
title: ModulusI 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 7bad044db9e2229c85cb3909dc4802bceaee6382
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847288"
---
# <a name="modulusi-function"></a>ModulusI 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


计算模的规范 residue `value` `modulus` 。

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a>输入

### <a name="value--int"></a>值： [Int](xref:microsoft.quantum.lang-ref.int)

计算 residue 的值


### <a name="modulus--int"></a>取模： [Int](xref:microsoft.quantum.lang-ref.int)

Residues 所采用的模数必须为正数



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

0之间的整数 $r $， `modulus - 1` 这可 `value - r` 被模数整除

## <a name="remarks"></a>备注

此函数的行为与运算符 `%` 在 c # 和 Q # 中的行为方式有所不同，因为结果中始终是0到之间的一个非负整数 `modulus - 1` ，即使值为负。