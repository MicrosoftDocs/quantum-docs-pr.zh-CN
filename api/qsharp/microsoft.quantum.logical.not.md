---
uid: Microsoft.Quantum.Logical.Not
title: Not 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: f2db43f4a2ce83d8cad1d60aa8c481a33b0c7d44
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197443"
---
# <a name="not-function"></a>Not 函数

命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回值的布尔值求反。

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a>输入

### <a name="value--bool"></a>值： [Bool](xref:microsoft.quantum.lang-ref.bool)

要求反的值。



## <a name="output--bool"></a>输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值

`true` 当且仅当 `value` 为时 `false` 。

## <a name="remarks"></a>备注

以下项是等效的：

```Q#
let x = not value;
let x = Not(value);
```