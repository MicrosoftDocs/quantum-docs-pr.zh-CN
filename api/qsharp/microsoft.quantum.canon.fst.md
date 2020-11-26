---
uid: Microsoft.Quantum.Canon.Fst
title: Fst 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 634f11881a054df7fe79d889832ea6bd80a7394f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206929"
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