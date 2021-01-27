---
uid: Microsoft.Quantum.Logical.NotEqualC
title: NotEqualC 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualC
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 33049b09405529bd418ff8652b6cb0f11bf734f0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849070"
---
# <a name="notequalc-function"></a>NotEqualC 函数

命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


当且仅当两个输入不相等时，返回 true。

```qsharp
function NotEqualC (a : Microsoft.Quantum.Math.Complex, b : Microsoft.Quantum.Math.Complex) : Bool
```


## <a name="input"></a>输入

### <a name="a--complex"></a>答： [复杂](xref:Microsoft.Quantum.Math.Complex)

要比较的第一个值。


### <a name="b--complex"></a>b： [复杂](xref:Microsoft.Quantum.Math.Complex)

要比较的第二个值。



## <a name="output--bool"></a>输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值

`true` 当且仅当不 `a` 等于时 `b` 。