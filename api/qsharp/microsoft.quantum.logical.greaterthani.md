---
uid: Microsoft.Quantum.Logical.GreaterThanI
title: GreaterThanI 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanI
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 06cae04150f9f0164b06a4e3d4bb78242b41dc0b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197987"
---
# <a name="greaterthani-function"></a>GreaterThanI 函数

命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


当且仅当一个数字大于另一个数字时，返回 true。

```qsharp
function GreaterThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a>输入

### <a name="a--int"></a>a： [Int](xref:microsoft.quantum.lang-ref.int)

要比较的第一个值。


### <a name="b--int"></a>b： [Int](xref:microsoft.quantum.lang-ref.int)

要比较的第二个值。



## <a name="output--bool"></a>输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值

`true` 当且仅当 `a` 严格大于时 `b` 。

## <a name="remarks"></a>备注

以下项是等效的：

```Q#
let cond = a > b;
let cond = GreaterThanI(a, b);
```