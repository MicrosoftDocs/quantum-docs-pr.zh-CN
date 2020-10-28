---
uid: Microsoft.Quantum.Logical.Or
title: Or 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 98a416229386461b241d087b7ae95f078f8be70a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696640"
---
# <a name="or-function"></a>Or 函数

命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)

软件包 [](https://nuget.org/packages/)


返回两个值的布尔析取。

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>输入

### <a name="a--bool"></a>a： [Bool](xref:microsoft.quantum.lang-ref.bool)

要考虑的第一个值。


### <a name="b--bool"></a>b： [Bool](xref:microsoft.quantum.lang-ref.bool)

要考虑的第二个值。



## <a name="output--bool"></a>输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值

`true` 当且仅当 `a` 或 `b` 为时 `true` 。

## <a name="remarks"></a>注解

与 `or` 运算符不同，此函数不会进行短路，因此，这两个输入都是完全计算的。

最多短路行为，如下所示：

```Q#
let x = a or b;
let x = Or(a, b);
```