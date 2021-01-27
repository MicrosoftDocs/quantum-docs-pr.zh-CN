---
uid: Microsoft.Quantum.Canon.Compose
title: 撰写函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 73eab66e2e9a9af56d01db927eb7af38bb56a23e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840909"
---
# <a name="compose-function"></a>撰写函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回两个函数的组合。

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a>说明

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