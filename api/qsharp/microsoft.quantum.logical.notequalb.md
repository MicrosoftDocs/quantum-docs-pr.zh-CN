---
uid: Microsoft.Quantum.Logical.NotEqualB
title: NotEqualB 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 9f362b9e08f8a798bf7f7d9c323fee6576dccd9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814427"
---
# <a name="notequalb-function"></a>NotEqualB 函数

命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


当且仅当两个输入不相等时，返回 true。

```qsharp
function NotEqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>输入

### <a name="a--bool"></a>a： [Bool](xref:microsoft.quantum.lang-ref.bool)

要比较的第一个值。


### <a name="b--bool"></a>b： [Bool](xref:microsoft.quantum.lang-ref.bool)

要比较的第二个值。



## <a name="output--bool"></a>输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值

`true` 当且仅当不 `a` 等于时 `b` 。

## <a name="remarks"></a>备注

以下项是等效的：

```qsharp
let cond = a != b;
let cond = NotEqualB(a, b);
```