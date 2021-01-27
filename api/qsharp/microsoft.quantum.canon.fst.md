---
uid: Microsoft.Quantum.Canon.Fst
title: Fst 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: cd5746358c8323f8d2dbca44965fa5dbac0a84c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840515"
---
# <a name="fst-function"></a>Fst 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


给定一对，返回其第一个元素。

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a>输入

### <a name="pair--tu"></a>配对： ( ' U) 

具有两个元素的元组。



## <a name="output--t"></a>输出：不

`pair` 的第一个元素。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

对的第一个成员的类型。
### <a name="u"></a>' U

对的第二个成员的类型。