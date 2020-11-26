---
uid: Microsoft.Quantum.Canon.Compose
title: 撰写函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: f8c6ad36220b48be1723c2d91cbf7c0a4947af14
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216755"
---
# <a name="compose-function"></a>撰写函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回两个函数的组合。

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a>描述

如果 $g $ $f 两个函数，则返回一个表示 $f \circ g $ 的新函数。

## <a name="input"></a>输入

### <a name="outer--u---v"></a>外部： "U->" V

要应用的第二个函数。


### <a name="inner--t---u"></a>内部：不 > "U

要应用的第一个函数。



## <a name="output--t---v"></a>输出：不 > "V

新函数 $h $，以便所有输入 $x $，$f (g (x) # A3 = h (x) $。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

要应用的第一个函数的输入类型。
### <a name="u"></a>' U

要应用的第一个函数的输出类型以及要应用的第二个函数的输入类型。
### <a name="v"></a>' V

要应用的第二个函数的输出类型。