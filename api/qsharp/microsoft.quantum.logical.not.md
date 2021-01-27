---
uid: Microsoft.Quantum.Logical.Not
title: Not 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: bf09cac8d126371df6218b7e92d68a881b732dc8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849074"
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

```qsharp
let x = not value;
let x = Not(value);
```