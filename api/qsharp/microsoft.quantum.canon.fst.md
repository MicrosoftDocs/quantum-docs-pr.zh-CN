---
uid: Microsoft.Quantum.Canon.Fst
title: Fst 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 88ff5e29de9eeefcc1e207f277c37c63cb0faade
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696056"
---
# <a name="fst-function"></a>Fst 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


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